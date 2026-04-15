# Privacy Policy — HowdyPlan

_Effective date: 2026-04-15_

HowdyPlan is a Chrome extension that helps Texas A&M students build class schedules. This policy explains exactly what it collects, where that data lives, and how to get it deleted.

## Who we are

HowdyPlan is built and operated by **Enoch Poon**, a Texas A&M student, as an individual project. It is free, has no ads, no analytics SDKs, and no investors asking for data.

- **Contact:** enoch@howdyplan.com _(or use the "Report a bug" button in the extension if the inbox is slow)_
- **Not affiliated with Texas A&M University.** HowdyPlan is an independent student-built tool. "Aggie" and "TAMU" references describe the student audience, not an institutional endorsement.
- **Developer:** Enoch Poon (individual, not a company)

## What we collect

The extension stores the following data on a server operated by the developer:

| Field | Source | Why we need it |
|---|---|---|
| Email address | You enter it during onboarding | Keys your profile so you can reinstall without re-entering everything |
| Major | You pick from a list | Computes remaining degree requirements |
| Completed courses (+ self-reported grades) | You enter them during onboarding | Filters out classes you've already finished |
| Schedule preferences | You configure in the side panel | Drives the optimizer (time of day, days off, blocked times, min professor rating) |
| CollegeScheduler session cookie (`.AspNet.Cookies`) | Captured when you visit `tamu.collegescheduler.com` | Sent to our server so we can refresh live section / seat data on your behalf |
| Watched CRNs | You add them from the side panel | Lets the server poll for open seats and alert you |

We do **not** collect: your TAMU password, SSO credentials, browsing history, pages you visit, or anything outside `tamu.collegescheduler.com`.

## Where it's stored

- **Primary database:** PostgreSQL running on a home server in Houston, TX, operated by the developer.
- **Transport:** HTTPS via a Cloudflare Tunnel. Cloudflare routes encrypted traffic only — it does not inspect or store request bodies.
- **Backups:** Nightly snapshots to a personal laptop over a private VPN. Retained 14 days on the server and 30 days on the laptop.
- **Not in:** any cloud database, analytics platform, ad network, error-tracking SaaS, CDN beyond Cloudflare's tunnel, or third-party hosting provider.

## How we use it

Your data is used only to make the extension work for you:

1. **Personalize schedule optimization** — take your major, completed courses, and preferences into account when ranking schedules.
2. **Refresh live section data** — use your CollegeScheduler session cookie to request current seat counts from `tamu.collegescheduler.com` on your behalf.
3. **Poll watched classes** — check your watched CRNs on a periodic interval for open seats.
4. **Send seat-open alerts** — when a watched class opens up, post a notification to a Discord webhook (either a shared alerts channel or a per-user webhook you configure).

We never sell, rent, share, or transfer your data to advertisers, data brokers, or anyone else.

## Third parties

Only three third parties ever touch your data, and each is narrowly scoped:

- **CollegeScheduler.com** — we proxy requests through our server to refresh live sections using your session cookie. Traffic goes from our server back to CollegeScheduler's own domain; no new party sees it.
- **Cloudflare Tunnel** — transport only. Cloudflare terminates the TLS tunnel that exposes the home server to the internet. It does not decrypt or store request bodies.
- **Discord** — the destination for seat-open alerts via webhook. Discord sees only the short alert message (course code, CRN, open seats). It never sees your profile, cookies, or preferences.

## Retention

- **Profile data** (email, major, completed courses, preferences, watched CRNs): kept until you delete it. You can wipe it yourself any time via **Admin mode → Purge my data** in the side panel.
- **Session cookie:** overwritten each time the extension captures a fresh one; removed from the server when you purge or when it expires upstream.
- **Bug reports:** kept for 90 days, then deleted.
- **Server logs:** request logs are kept 30 days and contain only email + endpoint + timestamp (no bodies).

## Your rights

You can:

- **See what we have on you** — email the contact address above and ask. We'll reply with your full record within a week.
- **Delete everything** — open the side panel, flip to Admin mode, click **Purge my data**. Your profile, completed courses, preferences, watched CRNs, session cookie, and bug reports tied to your email are removed from the database immediately and from backups within 30 days (as old backups roll off).
- **Correct anything** — just update it in the extension; the server syncs on save.

If the in-extension purge fails for any reason, email the contact address and we'll handle it manually within a week.

## No ads. No analytics. No selling.

There are no ad networks, no tracking pixels, no Google Analytics, no Sentry, no Mixpanel, no affiliate links. The extension has no revenue model. Nothing is sold.

## Children's privacy

HowdyPlan is intended for TAMU students (18+). We do not knowingly collect data from anyone under 13.

## Changes to this policy

If this policy changes materially, the effective date at the top will update and the extension will show a one-time banner prompting you to review it.

## Contact

Questions, deletion requests, or anything else: **enoch@howdyplan.com**

_(If that address bounces while it's being set up, open the extension's side panel and use "Report a bug" — same inbox, different path.)_
