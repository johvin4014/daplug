# Security Basics (MVP)

## Principles
- Least privilege access
- Default deny on database tables
- Validate all inputs
- Log key actions

## Supabase (planned)
- Row Level Security (RLS) enabled on all tables
- Policies:
  - Users can read public events
  - Hosts can create events
  - Hosts can update/delete ONLY their events
  - Users can RSVP to events
  - Users can only see their own RSVPs

## Abuse Prevention (MVP)
- Basic rate limiting (later in API layer if needed)
- Report system for events/users
