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

## Immediate next step the user asked for: field research (grilling scope agreed, launch pending)

Fan out research across four fronts, in priority order:
1. **Competitive landscape** — Bark, Qustodio, Google Family Link, Apple Screen Time, Canopy,
   Aura, etc.: features, pricing, and *where they fail parents/kids* (the gaps to fill).
2. **Child-safety & developmental evidence** — AAP, eSafety commissioners, academic studies on
   monitoring-vs-trust, age-appropriateness, what actually keeps kids safer.
3. **Legal & privacy** — minors' data consent, lawful collection, app-store policy (both stores
   ban covert monitoring), Indonesia-specific rules.
4. **Technical / classification** — site-safety classification methods (category DBs, ML, APIs),
   accuracy, latency (~seconds target), cost.

Then bring findings back and turn them into product decisions.

## Open questions awaiting the user (design-tree frontier)
- **Q6** Confirm core signal: browser-based domain + classification (recommended) vs. network vs.
  screenshots.
- **Q7** Confirm v1 platform (browser extension recommended; Android/iOS later — iOS is heavily
  restricted).
- **Q9** Confirm jurisdiction (Indonesia assumed).
- **Q10** Confirm the differentiation axis (relationship-first + local fit recommended).
- Later (blocked on Q6/Q7): daily/monthly report format + PDF; screen-time tracking;
  classification source; data retention.

## Project state
- Repo is otherwise empty (only `LICENSE` and a stub `README.md`). No code yet.
- Glossary of terms: see `CONTEXT.md`.
- Working branch: `claude/ecstatic-wright-rhpvb3`.
