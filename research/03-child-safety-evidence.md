# Research front 3 — Child-safety & developmental evidence

**Status:** done (desk research, 2026-10-10) · **Informs:** guardrails, disclosure timing,
age-based design, report & digest design, co-viewable model, Q10

> **Evidence-quality note.** Most studies here are **correlational, self-reported and from
> Western samples** (US, Europe). No randomised trial of a parental-monitoring app was found.
> Several primary sites (ICO, OHCHR) could not be opened from this environment, so their
> wording is taken from reputable secondary summaries and should be re-checked before quoting.
> Tags: **[primary]**, **[secondary]**, **[weak]**, **[dated]**.

## Q1 — Does monitoring help or hurt safety and trust? Does transparency change that?

- **Heavy control goes with *more* online risk, not less.** In 215 US parent–teen pairs,
  greater parental control via monitoring apps was associated with **more** online risk;
  authoritarian (low-autonomy) parents were the most likely to use such apps, and already-
  victimised teens were more likely to be monitored (Ghosh et al., CHI 2018) [1]
  [primary-abstract][dated]. Correlational: monitoring may be a *response* to risk.
- **Children dislike control-style apps.** 736 child-written Play Store reviews of 37 apps
  (ages 8–19) described them as overly restrictive and privacy-invasive, damaging their
  relationship with parents (Ghosh et al., CHI 2018) [2] [primary-abstract][dated].
- **Parents learn most from what children choose to tell them.** In 1,186 Swedish 14-year-olds,
  children's spontaneous disclosure explained more of parents' knowledge — and of good
  adjustment — than parents' tracking did (Stattin & Kerr 2000), replicated in a more diverse
  US sample, though contested [3] [primary-abstract][dated].
- **Covert snooping costs trust; overt asking does not in the same way.** Snooping is a
  distinct strategy that strongly violates privacy expectations (Hawk et al. 2016); perceived
  intrusive monitoring predicted lower value-internalisation and, later, more secrecy in a
  3-year study of 448 adolescents [4] [secondary]. Causal direction is not settled.
- **Talking beats restricting for reducing *harm*.** Across 25,142 European 9–16-year-olds,
  **active mediation** (talking, sitting nearby, encouraging exploration) was linked to lower
  risk and, importantly, **lower harm**, plus more skills; restrictive mediation cut risk but also
  opportunities and skills (EU Kids Online) [5] [primary][dated]. Livingstone et al. (2017,
  6,400 parents of 6–14s): "restrictive" mediation suits low-skill families and young children;
  "enabling" mediation suits skilled ones [5] [primary].
- **Expert bodies agree.** The AAP's Center of Excellence recommends **family safety plans that
  build teen self-regulation and include the child in rule-setting** over control apps, noting
  restrictive tools make it harder for teens to develop autonomy [6] [primary]. eSafety (AU):
  no control tool is 100% effective; build an open, trusting relationship and co-view [7]
  [secondary].

**Answer:** Monitoring alone does not make children safer and can hurt trust, especially when
covert or heavily controlling. **Transparency removes the worst harm (secret snooping) but is
not enough on its own** — benefit comes from what monitoring is *used for*: conversation and
helping the child build self-regulation.

## Q2 — Is "disclose at ~age 11" supported?

**No.** No research sets an age for telling a child about monitoring; vendor advice is to tell
them *before* installing [8] [weak]. The child-rights and design standards point to
**disclosure from the start, at every age**:

- **UN CRC General Comment No. 25 (2021), para 76:** surveillance of children should respect
  their privacy and **not be conducted routinely, indiscriminately or without the child's
  knowledge** (for very young children, the parent's), with a right to object where possible
  [9] [secondary — verify against CRC/C/GC/25].
- **UK Age Appropriate Design Code, standard 11 (Parental controls):** give the child
  **age-appropriate information** about parental controls, and where a parent can monitor
  activity, provide an **obvious sign to the child when monitoring is taking place** [10]
  [secondary — verify against ico.org.uk].

**Answer:** Replace "encourage disclosure around age 11" with **"the child is told from day one,
in words that fit their age, and sees an obvious sign while it runs"** — which `PRD.md`'s
persistent indicator already does.

## Q3 — How much autonomy at each age, and how should oversight taper?

- GC 25 frames children's rights around **evolving capacities** — oversight should shrink as
  capacity grows [9] [secondary].
- AAP: give teens **increasing independence as they show readiness** [6] [primary].
- Livingstone et al.: closer, more restrictive oversight fits **younger, less-skilled** children;
  enabling mediation fits **older, skilled** ones [5] [primary].
- No study gives exact age cut-offs. A **proposal** consistent with the above (needs user
  decision, Q15):

| Band | Parent sees | Child's role |
|---|---|---|
| **6–9** | App/site detail + classification | Co-use; parent explains reports together |
| **10–12** | Detail + classification, flagged items highlighted | Child sees same report; agrees family rules |
| **13–16** | **Categories and flags, less item-level detail**; screen time | Child reviews own report first; self-set goals |

## Q4 — Which reports lead parents to helpful action?

- **Evidence is thin.** Apps are built for control: of features in 75 Android safety apps,
  **89% supported parental control and 11% teen self-regulation**; only ~2% were educational
  (Wisniewski et al., CSCW 2017) [11] [primary-abstract][dated].
- When 217 parents got a **serious risk alert** (self-harm) from a monitoring app, the most
  common responses were **talking with the child** and supporting coping — but parents also
  reported guilt, confusion and nervousness; alert accuracy was unvalidated (Burke et al., JMIR
  2025) [12] [primary].
- AAP recommends a **Family Media Plan**, selective co-viewing and **ongoing conversations** [6]
  [primary].

**Answer:** No study tests digest designs directly. The evidence supports reports that
(a) **point to a conversation, not a punishment**, (b) give parents **words to use**, (c) are
**careful with alarming flags** (false alarms cause distress), and (d) tie back to a
**family plan the child helped make**.

## Q5 — Does a co-viewable report help?

- **Promising, barely tested.** The COoPS lab study (19 parent–teen pairs) let parents and teens
  see each other's apps and permissions and give feedback; **both valued the shared view**, and
  teens could hide individual apps (Akter et al., CSCW 2022) [13] [secondary]. Researchers in
  this field now argue for moving **beyond parental control toward collaborative and
  community-based approaches** [14] [primary].
- No long-term or outcome study of co-viewable monitoring was found.

**Answer:** Fits all the evidence above (transparency, disclosure, active mediation) but is
**unproven**. Keep it, and treat it as something to evaluate in the family.

## Indonesian context

Restrictive mediation dominates in Indonesia and parenting is often authority-oriented
(front 1; [15] [weak]). Livingstone's finding that **restrictive mediation fits low-skill
families and young children** means the app should not condemn rules — it should **add
conversation on top of rules**, especially for older children. One 2025 study of 15 parents
and 30 adolescents found Indonesian parents already mix restrictive and enabling strategies
[15] [primary-abstract].

## Decisions this informs

1. **Guardrail update (Q14, new):** change "disclose around age 11" to **"told from day one,
   age-appropriate explanation, obvious sign while running"** (GC 25 para 76; UK AADC std 11).
   Update `HANDOFF.md`, `CONTEXT.md` and `PRD.md` once the user confirms.
2. **Age-tapered reporting (Q15, new):** adopt the 6–9 / 10–12 / 13–16 table above — less
   item-level detail for teens, more child self-review.
3. **Digest design:** every flagged item comes with a **conversation prompt**; tone is
   supportive, not alarming; flags must be conservative to avoid false alarms.
4. **Family plan:** consider a simple **family agreement** (AAP Family Media Plan-style) the
   child helps set, which reports refer back to. *(Candidate v1 feature.)*
5. **Co-viewable stays**, labelled as experimental; consider letting teens keep a small
   private zone (as COoPS did).
6. **Q10:** strongly supports "relationship-first / insight + conversation" over control.

## Sources

1. Ghosh et al., "A Matter of Control or Safety? Examining Parental Use of Technical Monitoring Apps on Teens' Mobile Devices," CHI 2018 — https://pure.psu.edu/en/publications/a-matter-of-control-or-safety-examining-parental-use-of-technical/
2. Ghosh et al., "Safety vs. Surveillance: What Children Have to Say about Mobile Apps for Parental Control," CHI 2018 — https://epublications.marquette.edu/mscs_fac/618
3. Stattin & Kerr, "Parental Monitoring: A Reinterpretation," *Child Development* 71(4), 2000 — https://pubmed.ncbi.nlm.nih.gov/10830980 ; follow-up evidence — https://pmc.ncbi.nlm.nih.gov/articles/PMC2682426
4. Hawk, Becht & Branje, "Snooping as a distinct parental monitoring strategy," 2016 — https://metatoc.com/papers/53369-snooping-as-a-distinct-parental-monitoring-strategy-comparisons-with-overt-solicitation-and-control ; Journal of Child and Family Studies (2021) — https://link.springer.com/article/10.1007/s10826-021-02114-y
5. Livingstone et al., "Maximizing opportunities and minimizing risks for children online: the role of digital skills in emerging strategies of parental mediation," *Journal of Communication*, 2017 — https://eprints.lse.ac.uk/68612/ ; Dürager & Livingstone, "How can parents support children's internet safety?" EU Kids Online, 2012 — https://eprints.lse.ac.uk/42872/
6. AAP Center of Excellence on Social Media and Youth Mental Health, "Parental controls & digital monitoring" — https://aap.org/en/patient-care/media-and-children/center-of-excellence-on-social-media-and-youth-mental-health/qa-portal/qa-portal-library/qa-portal-library-questions/parental-controls--digital-monitoring ; AAP 5Cs for older teens — https://downloads.aap.org/AAP/PDF/CoE_5Cs_Older_Teens.pdf
7. eSafety Commissioner, "Australia shares global online safety advice for parents and carers" — https://esafety.gov.au/about-us/newsroom/australia-shares-global-online-safety-advice-parents-and-carers-covid-19 ; eSafety parental controls via Student Wellbeing Hub — https://studentwellbeinghub.edu.au/resources/esafety-parents-parental-controls/
8. Qustodio, "Talking to your kids about parental controls" (vendor) — https://qustodio.com/en/blog/talking-to-your-kids-about-parental-controls-3-quick-tips
9. UN CRC, General Comment No. 25 (2021) — summaries: https://dig.watch/updates/un-committee-child-rights-issues-recommendations-protect-childrens-rights-digital ; https://edri.org/our-work/companies-are-now-allowed-to-scan-your-private-communications/ ; official text: CRC/C/GC/25 (OHCHR)
10. ICO Age Appropriate Design Code — summaries: https://www.hsfkramer.com/notes/data/2020-01/the-ico-publishes-its-age-appropriate-design-code-of-practice-for-online-services ; https://scl.org/?p=4711
11. Wisniewski et al., "Parental Control vs. Teen Self-Regulation: Is There a Middle Ground for Mobile Online Safety?" CSCW 2017 — https://stars.library.ucf.edu/scopus2015/7430 ; Penn State news — https://www.psu.edu/news/research/story/online-security-apps-focus-parental-control-not-teen-self-regulation
12. Burke et al., "Exploring parents' immediate reactions to digital suicide risk alerts," JMIR 2025 — https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12629623/
13. Akter et al., "From Parental Control to Joint Family Oversight," CSCW 2022 (DOI 10.1145/3512904), as summarised in — https://arxiv.org/pdf/2503.22995
14. "Moving Beyond Parental Control toward Community-based Approaches to Adolescent Online Safety" (2025) — https://arxiv.org/html/2503.22995v3
15. "Parental mediation strategies for social media use: a thematic analysis" (Indonesia), *Behaviour & Information Technology* 2025 — https://cris.maastrichtuniversity.nl/en/publications/parental-mediation-strategies-for-social-media-use-a-thematic-ana/ ; Aceh study — https://journal.uinsgd.ac.id/index.php/cjik/article/view/53320
