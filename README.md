# Fixora Stage 2 Prototype

Front-end only prototype for **Fixora**, a UK marketplace where users browse and book trusted tradespeople with an Uber Eats-style flow.

## Tech stack
- Next.js 14 (App Router)
- TypeScript
- Tailwind CSS
- shadcn/ui primitives
- lucide-react icons
- Framer Motion
- Sonner toasts

## Core product direction
This version shifts from estimate-first to **browse-and-select first**:
1. Choose service category
2. Browse/filter local tradespeople
3. Open provider profile
4. Book via multi-step flow

It also supports an alternate path:
- **Get matched fast** modal recommends top 3 providers using local matching logic

## What is implemented
- Sticky header with desktop nav + mobile menu drawer
- Neo-brutalist hero with dual CTAs
- Interactive service selector bar with active state
- Marketplace browse section:
  - category filtering
  - availability filtering (Available now / Today / Schedule later)
  - rating filters (4.0+ / 4.5+)
  - ETA filters (under 30 / under 60)
  - callout fee ordering (low/high)
  - verified / insured / emergency toggles
  - postcode/location search
  - working sort dropdown
  - mobile filter drawer
- Tradesperson cards with:
  - trust badges
  - save/favourite toggle
  - view profile
  - book now
- Tradesperson profile side panel with:
  - tabs (Overview / Services / Reviews / Availability)
  - time slot selection
  - save toggle
  - booking CTA
- Booking flow modal (front-end only):
  - Step 1: job details + urgency + optional photo preview
  - Step 2: property details
  - Step 3: confirmation summary
  - local validation + generated booking reference + success state
- Get matched fast modal:
  - category/postcode/urgency/description
  - local ranking logic returning 3 providers
  - continue to profile or booking
- Trust section with accordion details
- Social proof carousel
- Tradesperson join section + application modal (validated, success state)
- FAQ accordion
- Footer with interactive links and back-to-top

## Local-state only guarantees
- No backend
- No API calls
- No auth
- No payments
- No database
- No third-party integrations

All flows are simulated with React state and mock data.

## Project structure
- `app/page.tsx`: main composition and state orchestration
- `data/marketplace-data.ts`: seeded provider and section mock content
- `lib/marketplace-types.ts`: marketplace domain types
- `lib/marketplace-logic.ts`: filter/sort/match/reference logic
- `components/layout/`: header/footer
- `components/sections/`: hero + informational/conversion sections
- `components/marketplace/`: selector/filter/cards/browse section
- `components/modals/`: profile sheet, booking flow, match flow, trades apply

## Run locally
```bash
npm install
npm run dev
```

If PowerShell blocks `npm.ps1`, use:
```bash
cmd /c npm install
cmd /c npm run dev
```

## Notes
- This is intentionally a prototype with production-style UX interactions.
- All pricing, ETA, and matching outputs are mock logic for front-end demo purposes.
