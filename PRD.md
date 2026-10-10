# PRD: Child Online-Safety App (transparent, co-viewable)

**status:** draft — aligned to `HANDOFF.md` guardrails
**supersedes:** GitHub Issue #1 "PRD: Parental Phone Monitor" (realigned; see note below)
**governing principle:** child safeness through **transparency**, not surveillance

> This PRD must satisfy every guardrail in `HANDOFF.md`. The earlier "Parental Phone
> Monitor" draft described covert, silent, maximal-capture monitoring — the exact
> "stalkerware" the project rejected. That draft is realigned here, not extended.

## Problem Statement

Children under 17 are online across many apps and sites, some age-inappropriate or unsafe.
Parents want to help keep them safer, but the common tools are framed as *covert surveillance*,
which both app stores ban and which — per child-safety research — erodes the parent–child trust
that actually keeps kids safe. There is a gap for a tool that is **openly known to the child**,
collects the **minimum necessary** signal, and turns it into **shared understanding and
conversation** rather than secret reports.

## Solution

A two-app system the child **knows about and can see**:

- **Child app** (Android, visible): records *which apps/sites were used, for how long,* and a
  *safety classification* of each for this child's age. It shows a **persistent, non-dismissable
  indicator** that it is running, and a **child-facing view** showing the child the same activity
  and classifications the parent sees ("co-viewable").
- **Parent app** (same Flutter codebase, parent flavor): shows the activity timeline, screen-time,
  and classifications for the paired child's device; receives a **daily email digest** and a
  **monthly PDF report**.
- **Backend** (Go + SQLite): auth, device pairing, activity/classification storage, reporting.

**What it does NOT do** (guardrail 1 & 2): no silent/stealth operation, no continuous screen
video, no screenshots, no reading of message/photo/keystroke content, no hidden persistence
designed to evade the child's awareness.

## User Stories

**Parent**
1. Register with email+password and log in securely (JWT).
2. Generate a pairing code to link my child's device to my account.
3. Set my child's **birth year** so classifications are age-appropriate.
4. See a timeline of which apps/sites my child used today, with start/end times and screen-time.
5. See a **safety classification** (and category) for each app/site, for this child's age.
6. Receive a **daily email digest** and a **monthly PDF report** summarising screen-time and how
   often each app/site/category was accessed.
7. Get **conversation prompts** alongside flagged activity, so the data starts a talk rather than
   a punishment.

**Child (device, aware)**
8. See a **persistent, visible indicator** that the safety app is running (never hidden).
9. Open a **child-facing view** and see the *same* activity and classifications my parent sees.
10. Be told, at setup/disclosure, what is recorded and what is **not** (no messages, photos,
    keystrokes, or screen video).

**Backend**
11. Authenticate users via JWT.
12. Store device-pairing relationships so a parent sees only their own child's data.
13. Store app/site usage + screen-time + classification, and serve a timeline for the apps.
14. Generate daily digest and monthly report data.

## Implementation Decisions

**Working assumptions still open in grilling** (do not treat as final): platform = **Android**
(Q2); child-aware model = **co-viewable** (Q3); reporting = daily email + monthly PDF, dashboard
first (Q4); jurisdiction = **Indonesia** (Q5); differentiation = relationship-first + local fit
(Q6).

**Module layout:**

```
/child_app      — Flutter, child flavor (visible, co-viewable)
/parent_app     — Flutter, parent flavor
/backend        — Golang
```

**API contract:**

```
POST   /api/register              { email, password }
POST   /api/login                 { email, password } -> { token }
POST   /api/pair/start            { token } -> { pairing_code }
POST   /api/pair/claim            { token, pairing_code, device_name, birth_year }
POST   /api/activity/log          { token, device_id, events: [{type, app, url?, category?, ts_start, ts_end}] }
GET    /api/timeline              { token, device_id, date } -> { activities, screen_time, classifications }
GET    /api/child/timeline        { device_token, date } -> { activities, classifications }   // co-viewable, child-facing
GET    /api/report/monthly        { token, device_id, month } -> { pdf }
```

**SQLite schema:**

```sql
CREATE TABLE users (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  email TEXT UNIQUE NOT NULL,
  password_hash TEXT NOT NULL,
  created_at TEXT NOT NULL DEFAULT (datetime('now'))
);

CREATE TABLE devices (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  user_id INTEGER NOT NULL REFERENCES users(id),
  name TEXT NOT NULL,
  birth_year INTEGER,
  pairing_code TEXT UNIQUE,
  paired_at TEXT
);

CREATE TABLE activity_logs (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  device_id INTEGER NOT NULL REFERENCES devices(id),
  type TEXT NOT NULL CHECK(type IN ('app_usage', 'url_visit')),
  app_name TEXT,
  app_package TEXT,
  url TEXT,
  category TEXT,
  started_at TEXT NOT NULL,
  ended_at TEXT NOT NULL
);

CREATE TABLE classifications (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  device_id INTEGER NOT NULL REFERENCES devices(id),
  target TEXT NOT NULL,               -- domain or app package
  category TEXT,
  safety_rating TEXT,                 -- e.g. ok / caution / not-age-appropriate
  rated_for_birth_year INTEGER,
  classified_at TEXT NOT NULL DEFAULT (datetime('now'))
);
```

**Key dependencies:**
- Flutter: `flutter_foreground_task` (visible persistent notification), `http`,
  `flutter_secure_storage`
- Go: `github.com/mattn/go-sqlite3`, `github.com/golang-jwt/jwt/v5`, `golang.org/x/crypto/bcrypt`

**Pairing flow:** Parent app calls `/api/pair/start` → backend returns 6-char code (valid 15 min).
Child enters code in the (visible) pairing screen → `/api/pair/claim` with birth year → linked.

**Transparency mechanics (guardrail 1):** the child app runs as a **foreground service with a
persistent, non-dismissable notification**. Setup includes a disclosure screen. The child-facing
view is reachable from the app at any time.

**Activity capture:** foreground app + screen-time via Android `UsageStatsManager` /
`AccessibilityService` for foreground app changes and in-browser domain (domain only, not page
content). **No** screen recording, **no** screenshots, **no** message/keystroke capture.

**Classification:** category + age-appropriateness lookup (category DB / API), target latency
~seconds. Source still open in grilling.

## Testing Decisions

- **Good test:** tests external behavior (timeline returns data + classification after upload),
  not internals.
- **Go backend:** `net/http/httptest` with in-memory SQLite; table-driven tests.
- **Flutter:** widget tests for parent + child screens; integration test for pairing flow.
- **Transparency test:** assert the persistent indicator is present and the child-facing view
  returns the same data served to the parent.

## Out of Scope

- iOS support
- Web parent dashboard
- **Covert/silent/stealth operation of any kind** (guardrail 1)
- **Continuous screen recording, screenshots, image capture** (guardrail 2)
- GPS, SMS, call logging, keystroke capture, message/photo content
- Cloud storage provider integration
- Push notifications (beyond the required foreground-service notification)

## Note on Issue #1

The original Issue #1 ("Parental Phone Monitor") specified silent recording, continuous
MediaProjection screen video, URL-bar scraping, and ADB Device-Owner stealth persistence. Those
conflict with the non-negotiable guardrails in `HANDOFF.md` and are **not** carried forward. This
PRD replaces that direction with the transparent, co-viewable, minimum-necessary design above.
