# Research front 1 — Indonesian family context

**Status:** done (desk research, 2026-10-10) · **Gates:** Q7 platform, Q6 core signal,
classification taxonomy, Q10 differentiation

> **Evidence-quality note.** National child-specific data in Indonesia is thin. Many figures
> below reach us through secondary outlets (GoodStats, Databoks, news) rather than the primary
> BPS/APJII/KPAI documents, and some primary sites could not be opened from this environment.
> Each claim is tagged: **[primary]** official publication read or quoted directly,
> **[secondary]** official figure reported by media/aggregator, **[weak]** small/local sample,
> poll, or unclear method, **[dated]** data collected more than ~3 years ago.

## Headline findings

1. **Children go online on phones, almost never on computers.** Among students aged 5–23,
   **85.8% use a mobile phone, 83.8% use the internet, but only 19.8% have used a
   computer/laptop** — and at elementary level computer use is about **5%** (BPS Education
   Statistics 2025, March 2025) [secondary][1]. Only **18.5% of households** own a computer
   (BPS Telecommunication Statistics 2024) [primary][2].
2. **The phone is almost always Android.** StatCounter puts Android at ~77% of Indonesian mobile
   web traffic in mid-2026 (iOS ~23%) [secondary][3]. Traffic share over-weights iOS, so device
   share is likely higher; the mid-range brands that dominate Indonesia (Oppo, Samsung, Xiaomi,
   Vivo) are all Android.
3. **Young children share their parents' phone; ownership arrives late in primary school.** A
   Java study found personal-smartphone ownership rising from **8.7% in grade 1 to 82% in
   grade 6**, with most younger pupils using a parent's phone [weak][4]. A junior-high sample
   reported 71.3% own / 17.1% parent's / 11.6% shared [weak][5]. Device use starts very early:
   **58% of 5–6-year-olds** use a phone (BPS Susenas 2024) [secondary][6].
4. **Time goes into apps, not the browser.** No Indonesian app-vs-browser split was found
   (gap). What does exist points to in-app use: video (YouTube, TikTok), games (Roblox is in the
   top-5 games accessed by Indonesian gamers [secondary][7]; Mobile Legends, Free Fire), and
   chat (WhatsApp/Facebook Messenger were the main channels for online sexual abuse in the
   Disrupting Harm study [primary][dated][8]).
5. **Regulation now restricts under-16s on major platforms.** **PP Tunas (PP 17/2025)**, with
   implementing rule Permenkomdigi 9/2026, took effect **28 March 2026**: platforms must
   deactivate accounts of under-16s on listed "high-risk" services — **YouTube, TikTok,
   Facebook, Instagram, Threads, X, Bigo Live, Roblox** [secondary][9][10]. ~4.7 M child
   accounts were deactivated by mid-2026, mostly TikTok; Meta is lagging; experts expect
   workarounds via **shared family accounts** and parents' logins [secondary][10][11].
   *(Detailed applicability to this app goes to front 4.)*
6. **Screen-time figures are high but unreliable.** Officials cite **~7.5 h/day** (Komdigi) and
   **up to 11 h/day** for under-17s (KemenPPPA internal study, Oct 2025), with no published
   method [weak][12]. A 2022 KPAI survey found 25.4% of children use devices >5 h/day outside
   study [secondary][dated][13]. **IDAI** (Indonesian Paediatric Society) recommends **≤90 min/day
   for ages 6–12 and ≤2 h/day for 12–18** [secondary][14] — a usable local reference band.

## Online harms prevalent in Indonesia (feeds the classification taxonomy)

| Harm | Indonesian evidence | Quality |
|---|---|---|
| **Judi online** (online gambling) | ~2% of players were under 10 (~80,000 children) in 2024; ~200,000 under-19s exposed; Q1 2025 deposits by 10–16-year-olds > Rp2.2 bn; often via **parents' accounts** and gambling ads inside children's games [15][16] | secondary |
| **Pornography** | KPAI (May 2026): ~5 million children have accessed porn; 2,031 complaints in 2025 [17] | secondary |
| **Online sexual exploitation / grooming** | 2% of internet-using 12–17s abused online in a year (~500k); offenders mostly known to the child; WhatsApp/FB/Messenger [8]. Grooming via game chat (Roblox, Mobile Legends) is the 2025–26 focus; KPAI asked for Roblox to be blocked; face-verification for Roblox being prepared [18][19] | primary-dated / secondary |
| **Cyberbullying** | 45% of 2,777 youths aged 14–24 report experiencing it (UNICEF U-Report poll, ~2019); 45% of 3,077 secondary students (CfDS 2021) [20] | weak, dated |
| **Violent content** | 26% of children accessed violent content via games, YouTube, TikTok (KPAI ~2022) [13] | secondary, dated |
| **Scams / pinjol** (illegal online loans) | No child-specific data found. Pinjol is linked to judi online among adults (3.8 M gamblers with loans) [16] | gap |

## How parents mediate today

- **Rules are rare.** ~79% of children's device use has no parental rules and most parents do
  not accompany use (KPAI ~2022) [secondary][dated][13].
- **Restrictive mediation dominates; technical tools are least used.** Indonesian studies
  consistently rank restrictive rules first, then monitoring/co-use, then active discussion,
  with **parental-control software least used and mostly by digitally literate parents** [21].
  Adolescents in one Jakarta-area sample said ~25% of parents use technical mediation
  [weak][dated][21].
- **Parents want limits.** 84% of Indonesian parents back a social-media minimum age; only 18%
  fully prohibit social media; **TikTok is seen as most dangerous (58%)** (YouGov, Feb 2025)
  [secondary][22].
- **Use of TRUST+/ISP filters by families:** no data found → carried to front 2.

## By age band (where data allows)

| Band | What the data suggests |
|---|---|
| **6–9** | Mostly a **parent's or shared phone**; video and games dominate; personal ownership rare in early grades [4][6] |
| **10–12** | Personal phone becomes the norm by grade 6 (~82% in Java sample) [4]; games with chat (Roblox) become a grooming vector [18] |
| **13–16** | Own Android phone; social media despite the PP Tunas under-16 restriction (via workarounds); highest reported screen time; cyberbullying and sexual exploitation evidence concentrates here [8][10][12] |

## Gaps (not found in desk research)

- National app-vs-browser time split for Indonesian children.
- Average age of first personal phone (only a local study).
- Age-band-specific device data from BPS/APJII (APJII samples only 13+).
- Family use of TRUST+/ISP filters or parental-control apps (national figure).

## Decisions this informs

1. **Q7 — platform: Android first.** A desktop browser extension would reach roughly one in
   five students and about one in twenty elementary pupils, missing most usage. Recommend
   **Android child app as v1** (consistent with `PRD.md`); **drop or park the browser extension**.
   *Front 5 must still confirm Android capture is feasible within Google Play / sideload limits.*
2. **Q6 — core signal must be app-level, not only domains.** Most time is in YouTube, TikTok,
   games and WhatsApp, which have no visited domain to classify. The core signal should be
   **foreground app + duration**, with browser domains as a secondary signal.
3. **New open question — shared devices.** Young children often use a parent's phone. Installing
   a child app on a shared phone would also record the parent. Needs a decision: support only
   the child's own device, or use Android's separate user/profile per child. *(Added to
   HANDOFF as Q11.)*
4. **Classification taxonomy must be Indonesian.** Categories should include **judi online,
   pornography, sexual-exploitation/grooming risk (stranger chat in games/social apps),
   violence, cyberbullying-prone social apps**, plus a flag for **PP Tunas-restricted platforms**
   when the child is under 16 (shown as information for the parent–child conversation, not as
   enforcement).
5. **Report reference band:** use **IDAI screen-time guidance** (≤90 min ages 6–12, ≤2 h
   ages 12–18) rather than US norms.
6. **Q10 — differentiation:** technical tools are least used and favoured by digitally literate
   parents → the app must be **simple, in Bahasa Indonesia, and conversation-led** (rules and
   talking, not just blocking). Supports the "relationship-first + local fit" recommendation.
7. **For own-family use, the decisive fact is your own child's device** — see question to the
   user in `HANDOFF.md`.

## Sources

1. Databoks, "Data on Indonesian students using mobile phones, laptops and the internet in 2025" (citing BPS Statistik Pendidikan 2025) — https://databoks.katadata.co.id/en/technology-telecommunications/statistics/69251fd00425f/data-on-indonesian-students-using-mobile-phones-laptops-and-the-internet-in-2025
2. BPS, *Statistik Telekomunikasi Indonesia 2024* (released 29 Aug 2025) — https://www.bps.go.id/id/publication/2025/08/29/beaa2be400eda6ce6c636ef8/statistik-telekomunikasi-indonesia-2024.html
3. StatCounter, Mobile OS market share Indonesia — https://gs.statcounter.com/os-market-share/mobile/indonesia
4. Jurnal Kwangsan (Kemdikbud), smartphone ownership among primary pupils in Java — https://majalahvisi.kemdikbud.go.id/index.php/jurnalkwangsan/article/download/1156/pdf
5. "Pemanfaatan Parental App untuk Pengawasan Anak … SMP Negeri 21 Surakarta" — https://journals.usm.ac.id/index.php/dmstik/article/view/7242
6. GoodStats, "6% anak di bawah usia 1 tahun sudah gunakan HP" (BPS 2024) — https://data.goodstats.id/statistic/6-anak-di-bawah-usia-1-tahun-sudah-gunakan-hp-Jan9u
7. detikInet, "Roblox masuk top 5 game online paling sering diakses gamer RI" — https://inet.detik.com/games-news/d-8051488/roblox-masuk-top-5-game-online-paling-sering-diakses-gamer-ri
8. UNICEF Indonesia, Disrupting Harm press release (2022) — https://www.unicef.org/indonesia/press-releases/56-cent-online-child-sexual-exploitation-and-abuse-indonesia-goes-undisclosed-and
9. Bernama, "Indonesia bans social media use for under-16s as PP Tunas takes effect" — https://www.bernama.com/en/world/news.php?id=2538414
10. Tempo, "Indonesia bans social media accounts for children under 16" — https://en.tempo.co/read/2091062/indonesia-bans-social-media-accounts-for-children-under-16
11. Biometric Update, "Indonesia presses Meta to accelerate under-16 account deactivation" (Sep 2026) — https://www.biometricupdate.com/202609/indonesia-presses-meta-to-accelerate-under-16-account-deactivation
12. NU Online, "Anak Indonesia habiskan 11 jam sehari main gawai" (KemenPPPA) — https://nu.or.id/nasional/anak-indonesia-habiskan-11-jam-sehari-main-gawai-perlu-tiga-langkah-intervensi-Qy0SX ; Warta Ekonomi, "Komdigi ungkap screen time anak Indonesia capai 7,5 jam" — https://wartaekonomi.co.id/read616710/komdigi-ungkap-screen-time-anak-indonesia-capai-75-jam
13. Medcom, "Survei KPAI: 26% anak mengakses konten kekerasan melalui gawai" — https://www.medcom.id/nasional/peristiwa/yKXPMeOK-survei-kpai-26-anak-mengakses-konten-kekerasan-melalui-gawai
14. Investortrust, "Dampak buruk screen time berlebihan bagi anak" (IDAI guidance) — https://investortrust.id/lifestyle/35600/dear-ayah-dan-bunda-ini-dampak-buruk-screen-time-berlebihan-bagi-anak
15. NU Online, "Menkomdigi laporkan 80 ribu anak usia di bawah 10 tahun terpapar judi online" — https://nu.or.id/nasional/menkomdigi-laporkan-80-ribu-anak-usia-di-bawah-10-tahun-terpapar-judi-online-Z8M4D ; Bisnis, "Praktik judi online sudah menyusup ke gim online anak-anak" — https://teknologi.bisnis.com/read/20240726/84/1785830/praktik-judi-online-sudah-menyusup-ke-gim-online-anak-anak
16. NU Online, "3,4 juta situs diblokir, perputaran judol tembus Rp286 triliun" — https://nu.or.id/nasional/3-4-juta-situs-diblokir-perputaran-judol-tembus-rp286-triliun-hingga-papar-200-ribu-anak-indonesia-RJlVj
17. Bisnis, "KPAI: PP Tunas redam kekhawatiran orang tua" (May 2026) — https://teknologi.bisnis.com/read/20260504/101/1971241/kpai-pp-tunas-redam-kekhawatiran-orang-tua-terhadap-keamanan-anak-di-medsos
18. detikNews, "KPAI: pemerintah harus blokir game Roblox jika abaikan hak anak" — https://news.detik.com/berita/d-8055100/kpai-pemerintah-harus-blokir-game-roblox-jika-abaikan-hak-anak
19. Bisnis, "Pemerintah bakal pasang kamera verifikasi di Roblox" (Jan 2026) — https://teknologi.bisnis.com/read/20260107/84/1942453/siap-siap-pemerintah-bakal-pasang-kamera-verifikasi-di-roblox
20. The Jakarta Post, "Online hell: cyberbullying in Indonesia remains vicious and rampant" (2022) — https://www.thejakartapost.com/culture/2022/08/09/online-hell-cyberbullying-in-indonesia-remains-vicious-and-rampant
21. "Digital literacy and parental mediation strategies … in Aceh" (2026) — https://journal.uinsgd.ac.id/index.php/cjik/article/view/53320 ; Paramitha & Purwanti, parental mediation and problematic internet use (2020) — https://journal.untar.ac.id/index.php/provitae/article/view/7733/5182
22. YouGov, "Indonesians support government's proposal to regulate social media usage for children" (2025) — https://business.yougov.com/content/51591-indonesians-support-governments-proposal-to-regulate-social-media-usage-for-children-but-are-divided-on-its-effectiveness
