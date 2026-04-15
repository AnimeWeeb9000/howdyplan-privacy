# Privacy Policy — HowdyPlan

_Effective date: 2026-04-15_

HowdyPlan is a Chrome extension that helps Texas A&M students build class schedules. This policy explains exactly what it collects, where that data lives, and how to get it deleted.

## Who we are

HowdyPlan is built and operated by **Enoch Poon**, a Texas A&M student, as an individual project. It is free, has no ads, no analytics SDKs, and no investors asking for data.

- **Contact:** enochpoon11@gmail.com _(or use the "Report a bug" button in the extension if the inbox is slow)_
- **Not affiliated with Texas A&M University.** HowdyPlan is an independent student-built tool. "Aggie" and "TAMU" references describe the student audience, not an institutional endorsement.
- **Developer:** Enoch Poon (individual, not a company)

## What we collect

The extension stores the following data on a server operated by the developer:

| Field | Source | Why we need it |
|---|---|---|
| Email address | You enter it during onboarding | Keys your profile so you can reinstall without re-entering everything |
| Major | You pick from a list | Computes remaining degree requirements |
| Display name of your major, major status (declared/pre-ETAM/target), campus (College Station or Galveston) | You pick during onboarding | Drives degree-plan matching, honors/campus filtering, and the subtitle in the side panel |
| Completed courses (+ self-reported grades) | You enter them during onboarding | Filters out classes you've already finished |
| Schedule preferences | You configure in the side panel | Drives the optimizer (time of day, days off, blocked times, transit buffer, per-course honors preference, min professor rating) |
| CollegeScheduler session cookie (`.AspNet.Cookies`) | Captured when you visit `tamu.collegescheduler.com` | Sent to our server so we can refresh live section / seat data on your behalf |
| Anonymous client ID (`X-Client-Id`) | Auto-generated — SHA-256 of your email for signed-in users, or a random per-install token for guests | Rate-limits heavy endpoints per-user instead of per-IP, and powers the "X Aggies planning" counter in the footer |
| Extension debug logs (errors + warnings) | The extension's `/api/debug/log` endpoint, only when something breaks | Helps us fix bugs. We never send normal browsing activity — only caught exceptions and a few tagged user-triggered events |

We do **not** collect: your TAMU password, SSO credentials, browsing history, pages you visit, or anything outside `tamu.collegescheduler.com`.

## Where it's stored

- **Primary database:** PostgreSQL running on a home server in Houston, TX, operated by the developer.
- **Transport:** HTTPS via a Cloudflare Tunnel. Cloudflare routes encrypted traffic only — it does not inspect or store request bodies.
- **Backups:** Nightly snapshots to a personal laptop over a private VPN. Retained 14 days on the server and 30 days on the laptop.
- **Not in:** any cloud database, analytics platform, ad network, error-tracking SaaS, CDN beyond Cloudflare's tunnel, or third-party hosting provider.

## How we use it

Your data is used for two things:

1. **Make the extension work for you** — your major, completed courses, and preferences feed the schedule optimizer. Your CollegeScheduler session cookie lets our server refresh live section data on your behalf.
2. **Aggregate analysis and personal machine-learning research** — the developer (Enoch Poon) retains your profile data and may use it in aggregate for personal ML experiments and learning projects. Nothing is ever published, shared, sold, or connected back to you personally in any external output. If you don't want your data used this way, delete it anytime (instructions below).

We never sell, rent, share, or transfer your data to advertisers, data brokers, or anyone else.

## Third parties

Only two third parties ever touch your data, and each is narrowly scoped:

- **CollegeScheduler.com** — we proxy requests through our server to refresh live sections using your session cookie. Traffic goes from our server back to CollegeScheduler's own domain; no new party sees it.
- **Cloudflare Tunnel** — transport only. Cloudflare terminates the TLS tunnel that exposes the home server to the internet. It does not decrypt or store request bodies.

## Retention

- **Profile data** (email, major, completed courses, preferences): kept indefinitely for the uses above, or until you delete it. You can delete it any time via the **Delete my data** link at the bottom of the side panel.
- **Session cookie:** overwritten each time the extension captures a fresh one; removed from the server when you purge or when it expires upstream.
- **Bug reports:** kept for 90 days, then deleted.
- **Server logs:** request logs are kept 30 days and contain only email + endpoint + timestamp (no bodies).

## Your rights

You can:

- **See what we have on you** — email the contact address above and ask. We'll reply with your full record within a week.
- **Delete everything** — open the side panel, scroll to the very bottom of the footer, and click **Delete my data**. Your profile, completed courses, preferences, campus/major details, session cookie, seat-watch entries, and bug reports tied to your email are removed from the database immediately and from backups within 30 days (as old backups roll off). Extension debug logs are aggregated and not tied to your email, so they remain until their 90-day retention expires.
- **Correct anything** — just update it in the extension; the server syncs on save.

If the in-extension purge fails for any reason, email the contact address and we'll handle it manually within a week.

## No ads. No analytics. No selling.

There are no ad networks, no tracking pixels, no Google Analytics, no Sentry, no Mixpanel, no affiliate links. The extension has no revenue model. Nothing is sold.

## Children's privacy

HowdyPlan is intended for TAMU students (18+). We do not knowingly collect data from anyone under 13.

## Changes to this policy

If this policy changes materially, the effective date at the top will update and the extension will show a one-time banner prompting you to review it.

## Contact

Questions, deletion requests, or anything else: **enochpoon11@gmail.com**

_(If that address bounces while it's being set up, open the extension's side panel and use "Report a bug" — same inbox, different path.)_
