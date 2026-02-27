<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=24,30,35&height=170&section=header&text=Analytics%20Dashboard&fontSize=52&fontAlignY=35&animation=twinkling&fontColor=ffffff&desc=Privacy-Focused%20Web%20Analytics%20%7C%20Self-Hosted%20Umami%20Instance&descAlignY=55&descSize=18" width="100%" />

[![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)](.)
[![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white)](.)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)](.)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](.)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

**Self-hosted web analytics for my portfolio and projects. No cookies. No tracking. GDPR compliant.**

</div>

---

## Why This Exists

Google Analytics is overkill and privacy-invasive for personal projects. Umami gives me everything I need — pageviews, referrers, device breakdowns, and real-time visitors — without sending any data to third parties.

This is my self-hosted instance, deployed via Docker, tracking traffic across my portfolio and project sites.

---

## What This Tracks

| Metric | Description |
|--------|-------------|
| **Pageviews** | Which pages get the most traffic |
| **Referrers** | Where visitors come from |
| **Devices** | Desktop vs mobile vs tablet breakdown |
| **Countries** | Geographic distribution of visitors |
| **Real-time** | Live visitor count and current pages |
| **Events** | Custom event tracking (clicks, downloads) |

---

## Architecture

```
┌──────────────────────────────────────────────────────────────┐
│                    Self-Hosted Analytics                       │
│                                                               │
│   ┌──────────────┐    ┌──────────────┐    ┌──────────────┐  │
│   │  Tracked     │───→│  Umami       │───→│  PostgreSQL  │  │
│   │  Websites    │    │  Next.js App │    │  Database    │  │
│   │  (portfolio, │    │  (dashboard) │    │  (Prisma)    │  │
│   │   projects)  │    │              │    │              │  │
│   └──────────────┘    └──────────────┘    └──────────────┘  │
│                                                               │
│   ┌──────────────────────────────────────────────────────┐   │
│   │  Deployed via Docker | No cookies | GDPR compliant   │   │
│   └──────────────────────────────────────────────────────┘   │
│                                                               │
└──────────────────────────────────────────────────────────────┘
```

---

## Quick Start

```bash
git clone https://github.com/ajay-automates/analytics.git
cd analytics

# Docker (recommended)
docker-compose up -d

# Or manual
pnpm install
pnpm run build
pnpm start
```

### Environment Variables

```env
DATABASE_URL=postgresql://user:pass@localhost:5432/umami
```

---

## Key Design Decisions

| Decision | Rationale |
|----------|-----------|
| **Umami over Plausible** | Open-source, self-hosted, simpler deployment |
| **PostgreSQL over MySQL** | Better JSON support, Prisma compatibility |
| **Docker deployment** | One command to run, easy to update |
| **No cookies** | GDPR compliant out of the box, no consent banners |

---

## Tech Stack

`Next.js` `Prisma` `PostgreSQL` `Docker` `pnpm` `TypeScript`

---

## Credits

Based on [Umami](https://github.com/umami-software/umami) — the open-source, privacy-focused analytics platform.

---

<div align="center">

**Deployed by [Ajay Kumar Reddy Nelavetla](https://github.com/ajay-automates)** · February 2026

*Know your traffic. Respect your users.*

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=24,30,35&height=100&section=footer" width="100%" />

</div>
