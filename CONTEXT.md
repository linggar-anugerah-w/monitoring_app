# Context & Glossary

The shared vocabulary for this project. Keep this a glossary only — no implementation details.

## Guiding principle

**Child safeness through transparency.** This is a safeguard the child is aware of, not covert
surveillance. See `HANDOFF.md` for the full guardrails.

## Terms

- **Parent** — the adult who sets up the app and receives reports. The only human user of the app
  in v1.
- **Child** — the person whose online activity is kept safer. Under 17. Age is derived from
  **birth year only**. Not a user of the app's dashboard, but is *aware* the app exists
  (disclosure encouraged around age 11).
- **Transparent monitoring** — the app is visible on the child's device and the child knows it
  runs. The opposite — **covert monitoring** ("stalkerware") — is out of scope and will not be
  built.
- **Visit** — a record that the child accessed a given site/domain or app at a point in time. The
  core signal of the product.
- **Safety classification** — a judgment of how age-appropriate a visited site/app is for this
  child. Target latency is on the order of seconds.
- **Daily digest** — an email to the parent summarising the day's activity.
- **Monthly report** — a monthly email with a **PDF** attachment summarising screen time and how
  often the child accessed given apps/sites/categories.
- **Screen time** — how long the child spent on the device / on given apps or sites, aggregated
  for reporting.
- **Safeguard (vs. monitor)** — the product's intended identity: it should help protect and start
  conversations, not merely report on the child. To be sharpened with child-safety experts.
- **Co-viewable** — the child can see the same activity and classifications the parent sees
  (from `PRD.md`). Whether this helps is an open research question.
- **Harm category** — a kind of online risk the safety classification flags (e.g. judi online /
  online gambling, pornography, cyberbullying, grooming, scams, pinjol / illegal online loans).
  The taxonomy should reflect harms prevalent in Indonesia, not only US-centric categories.
- **Own-family use** — the current distribution model: the parent installs the app for their own
  child; it is not published to an app store.
