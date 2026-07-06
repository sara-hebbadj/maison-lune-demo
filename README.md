# Maison Lune Beauty Studio — Sliubar Concept Demo

A complete fictional Dubai salon demo built with Next.js App Router, TypeScript, Tailwind CSS, and Lucide icons. It demonstrates the full customer journey:

Discovery → service browsing → AI questions → booking → confirmation → business dashboard

## Demo disclaimer

Maison Lune Beauty Studio is a fictional concept created by Sliubar to demonstrate website, booking, AI assistant, automation, and dashboard capabilities. All names, data, appointments, reviews, and statistics are illustrative.

## Features

- Premium responsive salon website
- Complete service catalogue with category filtering
- Five-step booking flow with validation
- Specialist, calendar, and unavailable-slot states
- Browser-only booking persistence using `localStorage`
- Confirmation page with `.ics` calendar download and WhatsApp share CTA
- Controlled local AI assistant knowledge base with human handoff
- Responsive admin dashboard that automatically includes newly created demo bookings
- Illustrative metrics, enquiries, schedule, revenue, popular services, follow-ups, and activity
- SEO metadata and accessible semantic structure

## Tech stack

- Next.js 16 App Router
- React 19
- TypeScript
- Tailwind CSS 4
- Lucide React
- Local mock data and `localStorage`

## Local installation

```bash
npm install
npm run dev
```

Open `http://localhost:3000`.

## Production validation

```bash
npm run lint
npm run build
npm run start
```

## Deploy to Vercel

1. Push this project to a GitHub, GitLab, or Bitbucket repository.
2. Import the repository into Vercel.
3. Keep the detected framework as **Next.js**.
4. Use the default build command: `npm run build`.
5. Deploy. No environment variables or external services are required.

You can also use the Vercel CLI:

```bash
npm install -g vercel
vercel
```

## Local data behavior

Bookings are stored under browser `localStorage` keys:

- `maison-lune-demo-bookings`
- `maison-lune-last-booking`

No data is sent to a server. Clearing browser site data removes test bookings.

## Optional future enhancements

- Real authentication and role-based dashboard access
- Database-backed bookings and customer records
- Live staff availability and schedule conflict prevention
- Transactional email and WhatsApp templates
- Deposit or payment gateway integration
- CRM, loyalty, packages, memberships, and rebooking automation
- Production analytics and conversion tracking
- CMS-managed content, offers, and team profiles
- Approved maps and real salon contact integrations

Concept and system design by [Sliubar](https://sliubar.com).

## Architecture

- **Server-rendered route shells:** App Router pages provide route metadata and static content.
- **Client interaction islands:** Booking, service filtering, AI chat, contact form, and dashboard persistence are isolated client components.
- **Single source of truth:** `src/lib/data.ts` contains services, specialists, illustrative appointments, enquiries, and dashboard reporting data.
- **Browser persistence:** `src/lib/booking-storage.ts` provides guarded read/write helpers for the booking and dashboard connection.
- **Reusable presentation layer:** Shared buttons, containers, headings, cards, navigation, footer, and logo components keep spacing and styling consistent.

## Design system

The visual language uses a restrained salon palette:

- Warm ivory: `#f9f5f0`
- Paper white: `#fffdfb`
- Soft taupe: `#d8cbc2`
- Muted rose: `#b98d82`
- Espresso brown: `#3c2a24`
- Subtle gold: `#a98556`

Display typography uses a system serif stack for an editorial feel; interface typography uses a system sans-serif stack for reliability and fast loading. Components use generous spacing, 14–36px corner radii, restrained shadows, visible focus rings, and large touch targets.

## Project structure

```text
maison-lune-demo/
├── public/
├── src/
│   ├── app/
│   │   ├── about/page.tsx
│   │   ├── booking/
│   │   │   ├── confirmation/page.tsx
│   │   │   └── page.tsx
│   │   ├── contact/page.tsx
│   │   ├── dashboard/page.tsx
│   │   ├── services/page.tsx
│   │   ├── globals.css
│   │   ├── layout.tsx
│   │   └── page.tsx
│   ├── components/
│   │   ├── ai-assistant.tsx
│   │   ├── booking-confirmation.tsx
│   │   ├── booking-wizard.tsx
│   │   ├── contact-form.tsx
│   │   ├── dashboard.tsx
│   │   ├── logo.tsx
│   │   ├── service-card.tsx
│   │   ├── services-browser.tsx
│   │   ├── site-footer.tsx
│   │   ├── site-header.tsx
│   │   ├── site-shell.tsx
│   │   └── ui.tsx
│   └── lib/
│       ├── booking-storage.ts
│       ├── data.ts
│       └── types.ts
├── next.config.ts
├── package.json
├── postcss.config.mjs
├── tsconfig.json
└── README.md
```
