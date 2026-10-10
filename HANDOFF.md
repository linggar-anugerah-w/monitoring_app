# Handoff — Child Online-Safety App (prototype)

> **Read this first.** This project is a **child online-safety tool for parents**.
> Its governing principle is **child safeness through transparency**, not surveillance.
> Every design and implementation decision must be checked against the guardrails below
> *before* it is built. If a requested feature conflicts with them, stop and raise it —
> do not build it.

## Non-negotiable guardrails (do not cross without the user explicitly re-deciding, and even then flag it)

1. **Transparent, never covert.** The app is visible on the child's device and the child
   knows it is running. We do **not** build hidden/concealed monitoring, silent capture,
   stealth modes, or anything designed to evade the child's awareness. Covert monitoring of a
   person (including a minor by a parent) is "stalkerware": banned by Google Play and the
   Apple App Store, legally risky, and — per child-safety research — actively harmful to the
   parent–child trust the product is meant to protect.
2. **Minimum necessary data.** Collect the *least* data that serves the safety goal. The core
   signal is **"which sites/domains were visited, and how safe is each for this child"** — not
   the child's private content (messages, photos, keystrokes).
3. **Age-appropriate & relationship-first.** The product's thesis is a safeguard the child is
   *in on*. Features should strengthen the parent–child relationship (co-viewable reports,
   conversation prompts), not replace it with spying.
4. **Lawful by jurisdiction.** Primary market assumed to be **Indonesia** (UU PDP + child
   online-protection rules), with global app-store policies applying wherever distributed.
   Confirm legal specifics before shipping anything that collects a minor's data.

## What the product is

A tool that lets a **parent** keep a **child (under 17)** safer online. On a schedule it records
which sites/apps the child used and classifies each for age-appropriateness, then sends the
parent a **daily email digest** and a **monthly report (PDF)** summarising screen time and how
often the child accessed given apps/sites/categories. The app encourages parents to disclose it
to the child around age 11 so the child understands it as a safeguard.

## Decisions so far

### Settled
- **Audience:** a single parent monitoring their own child.
- **Child:** under 17; age derived from **birth year only**.
- **Posture:** **transparent / known to child** (covert capture is rejected and out of scope).
- **Commercial model:** **personal/family project, free** — not a commercial product.
- **Distribution:** **own family only** for now (not published to a store); public free
  distribution possibly later.
- **Platform tension (to resolve via research):** `PRD.md` assumes an **Android** child app;
  this file's earlier recommendation was a **desktop browser extension**. Research front 1
  (family context) + 5 (technical) decide Q7.
- **Product direction (Q1):** the **transparent, on-device, co-viewable** middle path — richer
  signals than bare domains (app/site usage, categories, screen-time) but **no covert capture and
  no silent screen video**. The GitHub Issue #1 "Parental Phone Monitor" PRD (covert, continuous
  screen recording) is **rejected and realigned** — see `PRD.md`.
- **Status:** early **prototype**; the user intends to consult child-safety experts to make it
  more of a safeguard than a monitor.

### Recommended but NOT yet confirmed by the user
- **Core signal (v1):** browser-based — report visited domains and classify each — instead of
  screen capture. *(Pending user confirmation; see open Q6.)*
- **Platform (v1):** desktop/laptop browser extension (Chrome/Edge) + small backend for reports.
  *(Pending; see open Q7.)*
- **Differentiation:** "transparent, trust-building, built for Indonesian families" as the
  headline; smart classification and good reporting as supporting features. *(Pending Q10.)*

### Explicitly rejected / shelved
- Covert screenshots "without the child knowing" — **rejected** (guardrail 1).
- Screenshot/image capture as the primary signal — **shelved** in favour of domain + safety
  classification (revisit later only with expert input and transparently).

## Immediate next step: field research (scope settled via grilling rounds 1–2; awaiting go)

### Research scope decisions
- **Purpose:** research is **decision-driving**. Every front ends with a "therefore we decide X"
  memo against specific open questions (Q6 core signal, Q7 platform, Q10 differentiation,
  classification source, data retention). Q6/Q7 stay provisional until research returns.
- **Distribution:** **own family only** for now (self-installed, not published to a store).
  Public free distribution is a possible later step, so store/PSE compliance is researched only
  as a light "before you publish" checklist.
- **Commercial model:** **personal/family project, free.** No pricing / willingness-to-pay
  research. Classification must use **free/open sources** (no paid category APIs).
- **Method:** **desk research only** (web sources). No parent interviews or expert-contact list
  in this pass.
- **Execution:** **sequential, one front at a time, in the main session** (no parallel
  sub-agents), so the user can review/steer between fronts.
- **Sources:** Indonesian- and English-language sources. Every claim cited; official sources
  (government, AAP, eSafety, peer-reviewed) outrank blogs; sources older than ~3 years flagged
  as dated.
- **Depth:** ~2–4 pages and 10–20 cited sources per front, each ending in a "decisions this
  informs" section; `SUMMARY.md` at most one page.
- **Output:** `research/` folder in the repo — one markdown file per front, plus
  `research/SUMMARY.md` that feeds back into this file.

### Research fronts (run in this order)
1. **Indonesian family context** (`research/01-family-context.md`; gates Q7) — answer, by age
   band (6–9, 10–12, 13–16) where data allows:
   1. device mix (Android / iOS / laptop);
   2. own vs. shared family device;
   3. age of first phone;
   4. top apps and app-vs-browser share of time;
   5. typical daily screen time;
   6. the most prevalent online harms in Indonesia (judi online, pornography, cyberbullying,
      grooming, scams, pinjol) — feeds the classification taxonomy;
   7. how Indonesian parents mediate today, incl. use of TRUST+/ISP filters.
2. **Competitive landscape** (`research/02-competitors.md`) — **Indonesian options only**
   (ISP parental controls e.g. Telkomsel/IndiHome, TRUST+/Internet Positif, Nawala and similar
   DNS filters) **plus Google Family Link** as the de-facto Android baseline: features and *where
   they fail parents/kids*.
3. **Child-safety & developmental evidence** (`research/03-child-safety-evidence.md`):
   1. effects of monitoring on safety and trust, and whether transparency changes them;
   2. evidence for/against **disclosure at ~age 11** (an untested assumption);
   3. age-appropriate autonomy and how oversight should taper by age;
   4. which report formats lead parents to helpful action (conversation prompts, co-viewing);
   5. effects of **co-viewable** reports (the PRD's model; an untested assumption).
4. **Legal & privacy** (`research/04-legal-privacy.md`; settles Q9) — for **own-family use**:
   UU PDP duties when processing one's own child's data, PP Tunas / PP 17/2025 applicability.
   **Light "before you publish" checklist:** PSE registration, individual vs. entity, Google
   Play / App Store parental-control policy. **Reference skim:** GDPR / COPPA / UK AADC for good
   practice.
5. **Technical / classification** (`research/05-technical.md`) — covers **both** an Android
   child app (UsageStatsManager, AccessibilityService for browser domain, local VPN/DNS) **and**
   a desktop browser extension, incl. Google Play restrictions on Accessibility/VPN use.
   Classification candidates: open category lists (e.g. UT1 Toulouse), TRUST+ list, free family
   DNS, app content ratings (for apps with no domain), small on-device model. Ranked by:
   **(i) privacy** (does the child's browsing leave the device to a third party?),
   (ii) Indonesian site/app coverage, (iii) accuracy, (iv) latency (~seconds), (v) offline use.

Then bring findings back and turn them into product decisions.

## Open questions awaiting the user (design-tree frontier)
- **Q6** Confirm core signal: browser-based domain + classification (recommended) vs. network vs.
  screenshots.
- **Q7** Confirm v1 platform (browser extension recommended; Android/iOS later — iOS is heavily
  restricted).
- **Q9** Jurisdiction — *settled for research:* Indonesia, own-family use; publish-time
  compliance (PSE, app stores) as a light checklist; GDPR/COPPA/UK AADC as reference only.
- **Q10** Confirm the differentiation axis (relationship-first + local fit recommended).
- Later (blocked on Q6/Q7): daily/monthly report format + PDF; screen-time tracking;
  classification source; data retention.

## Project state
- Aligned PRD now lives in `PRD.md` (child-safety / transparency-first; realigns Issue #1).
- Glossary of terms: see `CONTEXT.md`.
- No code yet.
- Working branch: `claude/ecstatic-wright-rhpvb3`.
