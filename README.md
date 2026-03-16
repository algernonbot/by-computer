# by-computer

> A design agency, run by agents.

**by-computer** is an AI-powered creative platform where specialized agents handle design, video, and document work. You describe what you need — the agents produce it.

---

## What it does

Instead of hiring designers or learning tools, you dispatch agents:

| Category | What they make |
|----------|----------------|
| **Design** | Ads, logos, social media posts |
| **Video** | Video content, animations |
| **Office** | Presentations, reports, documents |

Every output is stored in your history, tied to the agent and inputs that created it.

---

## Stack

- **Framework** — Next.js 15 (App Router)
- **Auth & Database** — Supabase
- **Payments** — Stripe
- **UI** — Tailwind CSS + Radix UI
- **Testing** — Jest + React Testing Library
- **Language** — TypeScript

---

## Getting started

### Prerequisites

- Node.js 18+
- A Supabase project
- A Stripe account (for billing)

### Install

```bash
npm install
```

### Configure environment

Copy the example env file and fill in your values:

```bash
cp .env.local.example .env.local
```

Required variables:

```env
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key
```

Stripe (for billing):

```env
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret
```

Optional (for Google OAuth):

```env
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
```

### Set up the database

Run the schema against your Supabase project:

```bash
# via Supabase dashboard → SQL editor, paste contents of:
supabase/schema.sql
```

### Run locally

```bash
npm run dev
```

App is at [http://localhost:3000](http://localhost:3000).

---

## Project structure

```
src/
├── __tests__/               # Jest test suites
├── app/
│   ├── (authenticated)/     # Protected routes (dashboard, agents, history, outputs)
│   ├── auth/                # Sign-in, sign-up, OAuth callback
│   └── page.tsx             # Landing page
├── components/              # Reusable UI components
├── hooks/                   # Auth context
├── lib/                     # Supabase client, auth utilities, agent helpers
├── middleware.ts            # Auth middleware
└── types/                   # Shared TypeScript types
```

---

## Plans

| Plan | Access |
|------|--------|
| `free` | Limited agent runs (14-day trial) |
| `design` | Full access to Design agents |
| `all-access` | Design + Video + Office agents |

---

## Development

```bash
npm run dev       # Start dev server
npm run build     # Production build
npm run lint      # ESLint
npm test          # Jest tests
```

---

## License

Private. All rights reserved.
