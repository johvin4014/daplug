# ADR 0001: MVP Stack

## Status
Accepted

## Context
DaPlug needs a fast MVP that proves product value: auth, events, map pins, RSVP, and basic host tools. The stack should be quick to ship and simple to maintain.

## Decision
Use Supabase for MVP backend:
- Supabase Auth for authentication
- Supabase Postgres for data
- Supabase Storage for images (event flyers, avatars)

Use Expo (React Native) for the mobile app and Mapbox for mapping.

## Consequences
### Pros
- Very fast MVP development
- Built-in auth, database, storage
- Row Level Security supports strong access control

### Cons / Risks
- Some advanced rate limiting and complex logic may require an API layer later
- Potential future migration work if moving to AWS

## Follow-ups
- Define RLS policies for profiles/events/rsvps/reports
- Define naming conventions and data validation rules
