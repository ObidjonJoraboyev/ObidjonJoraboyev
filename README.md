# Obidjon Djurabayev

**Flutter Developer** — I ship mobile apps to **1M+ users** and I read the analytics afterwards.

Currently leading mobile development at [**Sahiy**](https://sahiy.uz), Uzbekistan's largest e-commerce
platform, across a 6-app portfolio on iOS and Android. I publish under the verified pub.dev publisher
[**leadme.uz**](https://pub.dev/publishers/leadme.uz/packages) — **three packages**, all at a
perfect **160/160 pub score**. On the side I'm building [**Leadme**](https://leadme.uz), an admission OS
for international-education agencies.

**Open to remote roles and relocation** — EU · UK · US · Dubai.

<p>
  <a href="https://www.linkedin.com/in/obidjon-joraboyev/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="https://pub.dev/publishers/leadme.uz/packages"><img src="https://img.shields.io/badge/pub.dev-0175C2?style=flat&logo=dart&logoColor=white" alt="pub.dev"></a>
  <a href="https://leadme.uz"><img src="https://img.shields.io/badge/Leadme-000000?style=flat&logo=safari&logoColor=white" alt="Leadme"></a>
  <a href="mailto:xboymirzayev07@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white" alt="Email"></a>
</p>

---

## What I actually do

Most mobile developers close tickets. I look at where users drop off, form a hypothesis, ship the fix, and
measure it. A sample of work at Sahiy that started as a metric, not a ticket:

### Retention — found an 80% cliff and built the recovery loop

Tracked user cohorts in **PostHog** and found **80% of new users never came back between day 1 and day 7**.
Built a local-notification scheduler firing at **day 1 and day 5**, each surfacing the feature people didn't
know existed: AI-powered **text and image search**. Extended the same scheduler into **cart-abandonment and
unpaid-order reminders**, driven entirely on-device — no extra backend load, no FCM round-trip.

### Checkout — removed the friction the funnel was hiding

- **Killed a mandatory field.** Analytics showed users struggling at address entry — including users who had
  picked up **at a physical Sahiy branch** and had no delivery address to give. Removed the requirement for
  that path and the step disappeared from the funnel.
- **Made the payment screen think.** Re-architected it to auto-select and re-rank payment methods against the
  user's actual state — active balance first, then a linked card, falling back to local gateways like Payme
  when neither exists. One less decision at the moment people hesitate most.

### Auth — deleted the password

Authentication drop-offs clustered around forgotten and failed passwords at sign-up and login. Collapsed both
flows into a **single passwordless OTP entry point** that registers or signs in from the same screen — the
user never has to know which one they're doing.

### Performance — stopped paying for requests nobody asked for

On the Product Detail Page, the app fired a heavy **AI image-search** request for similar items on every
open, whether or not anyone scrolled to see them. Rendered local assets first and deferred the API call until
the section actually enters the viewport. Server bandwidth dropped for the majority of sessions that never
scroll that far.

### Logistics — Yandex Maps routing, natively in Flutter

Built the courier dispatch and tracking utility **inside the Flutter app** rather than bolting on a web view.
Integrated the **Yandex Maps API** on the mobile frontend to render vector routing polylines to client
drop-offs, with live distance metrics and **multi-modal ETAs** (on foot vs. by car).

### Home-screen widgets

Native OS widgets that show **live order status** on the user's home screen, with quick-action buttons that
deep-link straight into the relevant screen — order tracking without opening the app.

---

## Shipped

| Product | Scale | What I did |
|---|---|---|
| **[Sahiy Market](https://play.google.com/store/apps/details?id=uz.sahiy.market)** | 1M+ downloads · 4.0★ | UI/UX redesign → **+35% engagement**; migrated FCM to local notifications → **−40% backend load** |
| **Sahiy Seller** | 500+ active sellers · 4.3★ | Built from scratch on BLoC; **−60% API calls**, load time **3.2s → 0.9s** |
| **Sahiy Courier + Express** | Internal fleet | Logistics suite — Yandex Maps routing, dispatch, delivery tracking |
| **Uget** | Payments platform | Full redesign — **+30% satisfaction**, onboarding 5 → 3 steps, **2× QR speed**, rating **4.1★ → 4.6★** |
| **AmirbekSunnyTrade** | Solar energy | Offline-first monitoring dashboards (Hive) for unstable-connectivity regions |
| **Bozormedia** | 50K+ users | News & media platform — content feed, notifications, admin flows |

**Track record:** 25+ production releases across 6 apps · **99.5% crash-free rate** · reusable architecture
that cut feature delivery time ~50%.

Also rebuilt Sahiy's **deep-linking system** for deterministic routing across cold-start, background, and
terminated states — fixing race conditions where rapid sequential notifications overrode each other — and a
pipeline turning raw, inconsistent transaction-time location data into a structured format trusted across
business systems.

---

## My packages on pub.dev

All three at **160/160 pub points** — full static analysis, docs, platform support, and up-to-date deps.

| Package | What it does | Stats |
|---|---|---|
| **[`photo_opener`](https://pub.dev/packages/photo_opener)** | Telegram-style full-screen image viewer — pinch-zoom, swipe between images, thumbnails, swipe-down to dismiss. Network, asset, and file images. | **21 likes** · 33 releases · 160/160 |
| **[`auto_shimmer`](https://pub.dev/packages/auto_shimmer)** | Theme-aware shimmer & skeleton loading wrapper. Drop-in loading states with zero boilerplate. | 160/160 |
| **[`hashed_image`](https://pub.dev/packages/hashed_image)** | Network image with a BlurHash placeholder — progressive loading with no layout shift. | 160/160 |

```yaml
dependencies:
  photo_opener: ^0.3.2
  auto_shimmer: ^0.1.2
  hashed_image: ^0.0.3
```

---

## [Leadme](https://leadme.uz) — founder

**An admission OS** for international-education consulting agencies and their students. It replaces the
WhatsApp + Excel + Google Drive mess with one platform: document center, application pipeline
(Collecting → Submitted → Under review → Result), CRM, team roles, contextual chat, and deadline tracking —
plus an AI layer that auto-replies to Instagram, Telegram, and site inquiries in **Uzbek and Russian** and
re-engages leads at 3 / 14 / 42-day intervals.

Built after living the problem myself while applying to foreign universities. **MVP shipped** — in early
production with real agencies and students onboarding. I run product direction, the mobile and full-stack
build, and GTM.

---

## Tech

**Mobile** Flutter · Dart · iOS & Android native integration · Platform Channels · Home-screen widgets
**Architecture** BLoC · Cubit · Clean Architecture · MVVM · Provider · GetX
**Backend & data** REST · GraphQL · WebSocket · Dio · Firebase (Auth, FCM, Firestore, Analytics, Crashlytics)
**Storage** Hive · SQLite · Secure Storage · offline-first
**Product analytics** PostHog — cohort analysis, funnels, retention, event instrumentation
**Maps & location** Yandex Maps API · Google Maps · routing, polylines, multi-modal ETA
**DevOps** Git · GitHub Actions · Codemagic · Xcode · Android Studio

---

## About me

- 🇺🇿 Tashkent, Uzbekistan — open to relocation
- 🗣️ English **IELTS 7.0** · Uzbek native · Russian conversational
- 🎓 **Stanford Online** — Algorithms · **DeepLearning.AI** — Machine Learning · **SAT 1480**
- 🏆 **1st place** — Najot Ta'lim Hackathon
- 🎯 Admitted to CS Bachelor's at **Birmingham**, **Minnesota**, and **Penn State** — declined to keep
  building in production

## Get in touch

📧 **xboymirzayev07@gmail.com** ·
💼 **[LinkedIn](https://www.linkedin.com/in/obidjon-joraboyev/)** ·
📦 **[pub.dev](https://pub.dev/packages/photo_opener)** ·
🌐 **[leadme.uz](https://leadme.uz)** ·
🔗 **[Linktree](https://linktr.ee/jurabaev)**
