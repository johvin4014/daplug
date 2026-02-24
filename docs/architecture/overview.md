# Architecture Overview (MVP)

## Proposed MVP Stack
- Mobile: Expo (React Native)
- Backend: Supabase (Postgres + Auth + Storage)
- Maps: Mapbox
- Payments: Stripe (Phase 2)

## High-level Flow
Mobile App -> Supabase (Auth/DB/Storage)
Mobile App -> Mapbox (map tiles/geocoding)

## Data Entities (draft)
- users (profile)
- events
- rsvps
- reports
