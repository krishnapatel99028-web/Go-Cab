# Go CAB – Shared Airport Rides

Share airport cabs after landing. Split the fare. Save money.

## Features (MVP)

- **Passenger flow**
  - Phone OTP login / signup (mock OTP: `123456`)
  - Select Airport → Terminal → Destination → Preferred time
  - Automatic matching (±45 min, same destination, max 4 pax)
  - Women-only option
  - Fixed popular destination fares
  - Pay after ride (Razorpay ready – keys to be added)

- **Driver flow**
  - Separate role on signup
  - Dashboard of open matched groups
  - Accept ride → get passenger contacts

- **Tech**
  - Next.js 15 (App Router) + TypeScript
  - Tailwind CSS
  - NextAuth v5 (Credentials + mock Phone OTP)
  - Prisma + Neon Postgres
  - Vercel-ready

## Quick Start

1. **Clone & install**
   ```bash
   cd go-cab
   npm install
   ```

2. **Neon Database**
   - Create a free project at https://neon.tech
   - Copy the connection string
   - Put it in `.env.local` as `DATABASE_URL`

3. **Environment**
   ```bash
   cp .env.example .env.local
   # Edit DATABASE_URL and AUTH_SECRET
   ```

4. **Database setup**
   ```bash
   npx prisma generate
   npx prisma db push
   npx tsx prisma/seed.ts
   ```

5. **Run**
   ```bash
   npm run dev
   ```
   Open http://localhost:3000

## Demo Credentials

- OTP for any phone: **123456**
- Signup as Passenger or Driver

## Popular Destinations (seeded)

- Mumbai (BOM): Thane ₹1000, Andheri ₹600, Bandra ₹700, Navi Mumbai ₹900, ...
- Delhi, Bangalore also seeded

## Deploy to Vercel

1. Push to GitHub
2. Import project in Vercel
3. Add environment variables (`DATABASE_URL`, `AUTH_SECRET`, `AUTH_URL`)
4. Deploy

## Next Steps (post-MVP)

- Real SMS OTP (MSG91 / Twilio)
- Razorpay payment after ride completion
- Admin panel for destinations & fares
- Push / WhatsApp notifications
- Google Maps distance (optional)

---

Built with ❤️ for smarter airport transfers.
