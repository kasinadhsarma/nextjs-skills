# nextjs-skills

A curated reference library of Next.js (App Router) architecture patterns, caching semantics, API/middleware guides, deployment references, and AI-agent skills — maintained under a strict **1,000-line-per-document** discipline so that every guide fits in a single LLM context window.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Next.js](https://img.shields.io/badge/Next.js-15.x%20%7C%2016.x-000000?logo=next.js)](https://nextjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript)](https://www.typescriptlang.org)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

---

## What's Inside

| Document | Purpose | Lines |
|---|---|---|
| [App Router Fundamentals](docs/App%20Router%20Fundamentals.md) | File conventions, layouts, Server/Client Components, loading/error states, route groups, parallel & intercepting routes | ~150 |
| [Hooks, use client, and use server](docs/Hooks%2C%20use%20client%2C%20and%20use%20server.md) | Directive mechanics, prop/return-value serialization rules, `useActionState`/`useFormStatus`/`useOptimistic`/`use()` | ~260 |
| [Data Fetching And Caching](docs/Data%20Fetching%20And%20Caching.md) | `fetch` caching (14 vs 15 default flip), ISR, `revalidatePath`/`revalidateTag`, Server Actions, streaming with Suspense — **pre-16 model** | ~155 |
| [Cache Components And Partial Prerendering (Next.js 16)](docs/Cache%20Components%20And%20Partial%20Prerendering%20%28Next.js%2016%29.md) | `'use cache'`/`cacheLife`/`cacheTag`/`updateTag`, migration map from route segment configs, component-level static/dynamic spectrum | ~170 |
| [API Routes And Middleware](docs/API%20Routes%20And%20Middleware.md) | Route handlers, `middleware.ts`, Edge vs Node runtime, auth patterns | ~140 |
| [Deployment And Config](docs/Deployment%20And%20Config.md) | `next.config.ts`, env vars, image/font optimization, Vercel and Firebase App Hosting deploys | ~130 |
| [Tailwind Patterns Architecture](docs/Tailwind%20Patterns%20Architecture.md) | Tailwind v4 + `lib/responsive/patterns/` folder, two-layer page/component convention, migration gotchas | ~140 |
| [Payments Security (Razorpay + UCP)](docs/Payments%20Security%20%28Razorpay%20%2B%20UCP%29.md) | Server-side price computation, HMAC signature verification, signed webhooks, paise/rupee unit boundaries | ~150 |
| [Authentication Patterns (Firebase)](docs/Authentication%20Patterns%20%28Firebase%29.md) | Firebase client SDK, `AuthProvider` context, server-side `verifyIdToken` + UID-match ownership check | ~140 |
| [Profile & Account Patterns](docs/Profile%20%26%20Account%20Patterns.md) | Deterministic profile doc ID, idempotent creation, addresses/orders sub-resources — **includes an unresolved IDOR finding** | ~140 |
| [Authentication (NextAuth / Auth.js)](docs/Authentication%20%28NextAuth%20Auth.js%29.md) | v4 vs v5, Edge-safe split config, session strategies, callbacks, middleware route protection | ~170 |
| [Testing Strategies](docs/Testing%20Strategies.md) | What's unit-testable (Client Components, Server Actions) vs what needs Playwright E2E, Vitest setup | ~160 |
| [Performance Profiling And Bundle Analysis](docs/Performance%20Profiling%20And%20Bundle%20Analysis.md) | `@next/bundle-analyzer`, fixing misplaced `"use client"` boundaries, `next/dynamic`, reading `next build` output | ~150 |
| [Internationalization](docs/Internationalization.md) | `[locale]` segment + middleware pattern, `next-intl` setup, static generation per locale | ~160 |
| [Next.js Primitive Picker Skill](docs/skills.md) | Agent skill: decision tree for Server/Client Component, Server Action, Route Handler, or Middleware | ~180 |

---

## Who This Is For

- **Next.js developers** who want App Router architecture, caching, and deployment references in one place
- **AI coding agents** (Claude Code, Windsurf, Copilot) that need well-structured, file-scoped context to generate accurate code
- **Team leads** building internal style guides or onboarding material

---

## How to Use

### As a reading reference

Each document is self-contained with Mermaid diagrams, working code examples, and decision tables. Read them top-to-bottom or jump to a section.

### With AI coding agents

Every document is under 1,000 lines — intentionally. This means an agent can load an entire guide into its context window in a single read and reason about the full content without retrieval fragmentation.

**Recommended workflow with Claude Code:**
1. Open the relevant guide alongside your project
2. Reference it in your prompt: *"Following the primitive picker skill, should this be a Server Action or a Route Handler?"*
3. Run `/compact` after long sessions to flush accumulated context

### As an agent skill

The [primitive picker skill](docs/skills.md) is structured as a Claude Code skill with YAML frontmatter triggers. Install it under `~/.claude/skills/nextjs-primitive-picker/SKILL.md` (copy `docs/skills.md`) to have it activate automatically when a user is deciding between Server/Client Components, Server Actions, Route Handlers, or Middleware.

---

## Repository Structure

```
nextjs-skills/
├── docs/
│   ├── App Router Fundamentals.md
│   ├── Hooks, use client, and use server.md
│   ├── Data Fetching And Caching.md
│   ├── Cache Components And Partial Prerendering (Next.js 16).md
│   ├── API Routes And Middleware.md
│   ├── Deployment And Config.md
│   ├── Tailwind Patterns Architecture.md
│   ├── Payments Security (Razorpay + UCP).md
│   ├── Authentication Patterns (Firebase).md
│   ├── Profile & Account Patterns.md
│   ├── Authentication (NextAuth Auth.js).md
│   ├── Testing Strategies.md
│   ├── Performance Profiling And Bundle Analysis.md
│   ├── Internationalization.md
│   └── skills.md                          ← agent skill (primitive picker)
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   └── new_skill.md
│   └── pull_request_template.md
├── CONTRIBUTING.md
├── SECURITY.md
├── LICENSE
└── README.md
```

---

## Design Principles

1. **Under 1,000 lines per document** — every guide fits in a single LLM context window with room to spare
2. **Mermaid diagrams over images** — diagrams are text, version-controlled, and renderable in GitHub and any markdown viewer
3. **Working code, not pseudocode** — every snippet compiles and runs against current stable Next.js
4. **Agent-readable structure** — headings, tables, and code blocks are used consistently so agents can parse intent from structure
5. **No citation noise** — sources inform the content; they don't clutter it
6. **Version-aware** — caching and typing semantics changed between Next.js 14 and 15, and again with Cache Components in Next.js 16; every doc that's affected calls this out explicitly rather than assuming one version

---

## Coverage Roadmap

| Topic | Status |
|---|---|
| App Router fundamentals | Done |
| Data fetching & caching (ISR, Server Actions, streaming) | Done |
| API routes & middleware | Done |
| Deployment & config (Vercel, Firebase App Hosting) | Done |
| Tailwind v4 + responsive patterns architecture | Done |
| Payments security (Razorpay + UCP signing/verification) | Done |
| Authentication patterns (Firebase Auth + ID token verification) | Done |
| Profile & account patterns (deterministic IDs, sub-resource auth) | Done |
| Next.js primitive picker (agent skill) | Done |
| NextAuth/Auth.js deep dive | Done |
| Testing strategies (Playwright, Vitest with App Router) | Done |
| Performance profiling & bundle analysis | Done |
| Internationalization (i18n routing) | Done |
| Cache Components & Partial Prerendering (Next.js 16) | Done |
| Hooks, `use client`, and `use server` deep dive | Done |
| SEO (metadata, sitemaps, JSON-LD) | Planned |
| Content Security Policy | Planned |
| Multi-tenant / Multi-zones architecture | Planned |

Want to add a topic? See [CONTRIBUTING.md](CONTRIBUTING.md). Topic list is cross-checked against the [official Next.js guides index](https://nextjs.org/docs/app/guides) to catch gaps.

---

## Contributing

Pull requests are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guide — including how to add a new skill, update existing docs, and the review process.

---

## Security

Found a vulnerability or error in the guidance? See [SECURITY.md](SECURITY.md) for the responsible disclosure process.

---

## License

MIT — see [LICENSE](LICENSE). Copyright © 2026 kasinadhsarma.
