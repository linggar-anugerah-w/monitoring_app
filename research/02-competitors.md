# Research front 2 — Competitive landscape (Indonesia + Google Family Link)

**Status:** done (desk research, 2026-10-10) · **Informs:** Q10 differentiation, Q6 core
signal, scope of v1 (what *not* to build)

> **Scope (grilling round 2):** Indonesian options only, plus **Google Family Link** as the
> de-facto Android baseline. Global paid products (Bark, Qustodio, etc.) deliberately excluded.
> Tags as in front 1: **[primary]**, **[secondary]**, **[weak]**, **[dated]**.

## The landscape at a glance

| Option | Type | Cost | What the parent sees | Child aware? | Status |
|---|---|---|---|---|---|
| **Google Family Link** | On-device (Android account supervision) | Free | Per-app screen time, app installs/approvals, location; can block sites in Chrome and set limits/Downtime/School Time | Yes — child's account is visibly supervised | Active, redesigned Feb 2025 [1] |
| **Telkomsel ProtekSi Kecil** | Network (mobile operator) | Rp15,000/month incl. 500 MB, up to 2 devices | Category filtering, internet time limits, report of **blocked sites the child tried to open** | Yes — child must approve by SMS | Launched Jan 2025 [2][3] |
| **Telkomsel Family Protect** (with Family Zone) | App on child's phone | Rp8,800–13,200/month (older pricing) | Site blocking, safe content, app-download blocking, screen time | Yes | Older offering; current status unclear [4] [dated] |
| **TRUST+ Positif / "Internet Positif"** (national DNS blocklist) | Network (all ISPs must apply it) | Free / mandatory | Nothing — block page only | Block page shown | Active since 2014 [5][6] |
| **Nawala** | Free filtering DNS | Free | Nothing — warning page only | Warning page shown | Active; one study found it blocked the most test sites of DNS options compared [7] [weak] |
| **IndiHome "Internet Positif"** | Home broadband filter (TRUST+-based) | Included | Nothing | Block page | Described in tips articles only [8] [weak] |
| **Indosat, XL/XLSMART** | — | — | No current parental-control product found; both said in Mar 2026 they would build or adapt features for PP Tunas [9] | — | Planned |
| **Kakatu** | Android kids' launcher (Indonesian) | Free + ~US$6/yr | Parent picks which apps child may open | Yes | Launched 2015; current status unknown [10] [dated] |

## What each category does well and where it fails

### 1. Network filters (TRUST+, Nawala, IndiHome, ProtekSi Kecil)
- **Good at:** blocking known-bad domains (porn, gambling) with no install; TRUST+ is mandatory
  for every ISP, so a baseline block already exists for every child in Indonesia [5].
- **Fails at:**
  - **No insight.** Apart from ProtekSi Kecil's blocked-site report, the parent learns nothing
    about what the child actually does. Nothing starts a conversation.
  - **Blind to in-app content.** A domain filter cannot tell a harmful YouTube/TikTok video or
    a Roblox chat from a harmless one — and front 1 showed that is where children spend their
    time.
  - **Over- and under-blocking.** TRUST+ has a history of blocking legitimate sites (Vimeo,
    Reddit) and mixing IPs/URLs/FQDNs in its list [6][11] [dated]; judi online sites still reach
    ~80,000 under-10s despite millions of blocks (front 1).
  - **Easily bypassed** with a different DNS or a VPN [6] [dated].
  - **Network-bound.** ProtekSi Kecil works on the Telkomsel number; home Wi-Fi follows a
    different filter (or none). *(Inferred from it being a SIM-level service; not confirmed in
    Telkomsel's FAQ, which could not be opened.)*

### 2. Google Family Link (the baseline to beat)
- **Good at:** free, built into Android, transparent to the child, and strong on **control**:
  per-app limits, Downtime, **School Time** (Feb 2025), app-install approval, Chrome site
  blocking, location [1]. Google cites it as its parental-control answer to PP Tunas, and child
  accounts require parent consent at creation [12].
- **Fails at (relative to this project's thesis):**
  - **Shows time, not meaning.** Reports say *how long* in each app; nothing says whether
    activity was **age-appropriate** or matches an Indonesian harm (judi online, grooming-prone
    chat, etc.).
  - **Little web visibility on phones.** Parents can block sites in Chrome, but seeing the
    child's browsing history appears limited to Chromebooks / Chrome Sync; on Android this is
    not clearly available [13] [weak — unverified on Google's own help pages].
  - **Control-first, not conversation-first.** No conversation prompts, no co-viewing framing,
    no guidance on what to *say*.
  - **No Indonesian framing.** No IDAI screen-time bands, no PP Tunas platform awareness.
  - **Platform-policy risk.** Until Jan 2026 Google emailed children approaching 13 that they
    could end supervision themselves; after backlash, teens 13–18 now need parent approval to
    stop supervision [14][15]. A parent's tooling can change under them.

### 3. Local apps (Kakatu, Family Protect)
- Earlier Indonesian attempts were **launcher- or filter-based** control apps; neither shows
  current activity in 2025–26 searches. Telkomsel's own research found **86% of 1,000 surveyed
  parents interested in parental controls** [2] — interest is high, but **use stays low** (front
  1: technical mediation is the least-used approach).

## The gap this project can fill

No option in scope turns a child's **app and site activity into age-appropriate, Indonesian-
context meaning plus a prompt for a conversation**, visible to the child as well. All of them
are either **blockers** (network filters) or **time/limit controllers** (Family Link). That gap
matches the project's "safeguard, not monitor" thesis exactly.

## Decisions this informs

1. **Q10 — differentiation: confirmed direction.** Lead with *"understand and talk"*, not
   *"block and limit"*: per-app/site **safety classification against Indonesian harms**,
   **daily digest with conversation prompts**, and **co-viewable** reports. Supporting:
   Bahasa Indonesia, IDAI bands, PP Tunas awareness.
2. **New open question Q13 — complement Family Link instead of rebuilding it.** Family Link
   already does limits, Downtime, School Time, app approvals and Chrome blocking for free. v1
   could **leave enforcement to Family Link (and TRUST+/Nawala for DNS blocking)** and build
   only the insight + conversation layer. That shrinks v1 a lot. *(Recommended; needs user
   decision.)*
3. **Q6 — core signal:** reinforces front 1 — **per-app usage is the signal competitors
   already capture; the differentiator is classifying it.** Browser domains add value mainly
   because Family Link shows little web history on phones.
4. **Do not rely on network filters as the data source.** They see only domains, only on one
   network, and are easily bypassed.

## Sources

1. TechCrunch, "Google expands Family Link parental controls with screen time tools, approved contacts and more" (Feb 2025) — https://techcrunch.com/2025/02/12/google-expands-family-link-parental-controls-with-screen-time-tools-approved-contacts-and-more
2. CNN Indonesia, "Telkomsel rilis fitur buat ortu, bisa lindungi anak di ruang digital" (Jan 2025) — https://www.cnnindonesia.com/teknologi/20250120145438-213-1189262/telkomsel-rilis-fitur-buat-ortu-bisa-lindungi-anak-di-ruang-digital
3. Telkomsel, "ProtekSi Kecil: Telkomsel's new solution to help parents protect their children online" — https://www.telkomsel.com/en/about-us/news/proteksi-kecil-telkomsels-new-solution-help-parents-protect-their-children-online ; detikInet — https://inet.detik.com/telecommunication/d-7736163/dear-orang-tua-telkomsel-punya-solusi-internet-aman-dan-sehat-bagi-buah-hati
4. Telkomsel, "Layanan Family Protect hadirkan akses internet aman bagi keluarga" — https://www.telkomsel.com/about-us/news/layanan-family-protect-hadirkan-akses-internet-aman-bagi-keluarga
5. Makarim & Taira S., "Internet content censorship strengthened" (Permenkominfo 19/2014, TRUST+ obligations) — https://makarim.com/news/internet-content-censorship-strengthened
6. detikInet, "Lubang filter internet Trust+ Positif diungkap" — https://inet.detik.com/law-and-policy/d-2909864/lubang-filter-internet-trust-positif-diungkap ; "Ini aturan main DNS nasional ala Kominfo" — https://inet.detik.com/law-and-policy/d-2909489/ini-aturan-main-dns-nasional-ala-kominfo
7. "DNS filtering: a clean and positive internet environment in UIN Ar-Raniry Banda Aceh" — https://jurnal.ar-raniry.ac.id/index.php/cyberspace/article/view/2502
8. Gizmologi, "Tips Internet Positif: 9 langkah lindungi anak dari paparan konten negatif" — https://gizmologi.id/tips/internet-positif-lindungi-anak/
9. Selular.ID, "Operator seluler klaim layanannya sudah disesuaikan untuk penerapan PP Tunas" (Mar 2026) — https://selular.id/2026/03/operator-seluler-klaim-layanannya-sudah-disesuaikan-untuk-penerapan-pp-tunas/
10. Selular.ID, "Kakatu mungkinkan orang tua kelola aplikasi untuk anak-anak" (2015) — https://selular.id/2015/10/kakatumungkinkan-orang-tua-kelola-aplikasi-untuk-anak-anak/ ; CB Insights, Kakatu — https://www.cbinsights.com/company/kakatu/
11. DailySocial, "Government official confirms Google Public DNS blocking" (2014) — https://dailysocial.id/post/government-official-confirms-google-public-dns-blocking
12. CNA Indonesia, "Komdigi, Google, YouTube, PP Tunas, perlindungan anak" — https://www.cna.id/indonesia/komdigi-google-youtube-pp-tunas-perlindungan-anak-46091 ; Bisnis, "Komdigi dorong PP Tunas, Google pastikan keamanan anak prioritas utama" — https://teknologi.bisnis.com/read/20250514/101/1876651/komdigi-dorong-pp-tunas-google-pastikan-keamanan-anak-prioritas-utama
13. Google, Family Link disclosure for parents — https://families.google.com/familylink/privacy/ ; Android Central, "Google Family Link updated with more features on Chrome OS" — https://www.androidcentral.com/google-family-link-updated-more-features-chrome-os
14. Al Jazeera, "Child rights org says Google undermines parental control of child accounts" (Jan 2026) — https://www.aljazeera.com/economy/2026/1/14/child-rights-org-says-google-undermines-parental-control-of-child-accounts
15. Bitdefender, "Google backtracks on teen parental controls after public backlash" — https://www.bitdefender.com/en-us/blog/hotforsecurity/google-backtracks-on-teen-parental-controls-after-public-backlash
