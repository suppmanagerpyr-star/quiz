# Three Pyramids Smart Booking & Operations Platform (demo build)

Phase 1: data foundation + bilingual (EN/AR, RTL) public site.
All data is fictional. No WhatsApp, email or payment integrations are connected.

## Run locally (Node.js 20+)

    npm install
    npm run setup      # creates data/app.db and loads demo data
    npm run dev        # http://localhost:3000  (redirects to /en, Arabic at /ar)

## Demo staff accounts (used from phase 3)
admin@demo.test, owner@demo.test, ops@demo.test, airport@demo.test,
reception@demo.test, staff@demo.test. Shared password: Demo@12345

## Structure
- src/db/schema.ts       tables: requests, quotations, roles, users, fleet, services, statuses, settings, activity log, notifications
- src/db/seed.ts         fictional demo data (14 requests across all statuses and priorities)
- src/lib/i18n.ts        EN/AR text; service, fleet and company content comes from the database
- src/lib/permissions.ts permission keys and default roles (editable data, not hardcoded checks)
- src/lib/priority.ts    red under 24h, orange under 48h; thresholds live in the settings table
- src/app/[lang]/        homepage, about, services, fleet, contact, book (form arrives in phase 2)

Photos are placeholders (src/components/ImageSlot.tsx). Replace with real fleet and airport photography.
