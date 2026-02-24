# Database Schema v0 (MVP Draft)

## profiles
Represents the user profile linked to auth.users.
- id (uuid, pk) -> matches auth.users.id
- username (text, unique)
- display_name (text)
- avatar_url (text, nullable)
- is_host (boolean, default false)
- created_at (timestamp)

## events
Public events shown on the map.
- id (uuid, pk)
- host_id (uuid, fk -> profiles.id)
- title (text)
- description (text)
- category (text)
- start_time (timestamp)
- end_time (timestamp, nullable)
- address (text)
- latitude (numeric)
- longitude (numeric)
- image_url (text, nullable)
- is_public (boolean, default true)
- created_at (timestamp)

## rsvps
Tracks who is attending free events (MVP).
- id (uuid, pk)
- event_id (uuid, fk -> events.id)
- user_id (uuid, fk -> profiles.id)
- status (text)  # going | not_going (optional)
- created_at (timestamp)

## reports
Simple moderation report (MVP).
- id (uuid, pk)
- reporter_id (uuid, fk -> profiles.id)
- event_id (uuid, fk -> events.id, nullable)
- reported_user_id (uuid, fk -> profiles.id, nullable)
- reason (text)
- details (text, nullable)
- created_at (timestamp)

## Notes
- events are readable by everyone if is_public = true
- only the host can edit/delete their own events
- a user can only see/manage their own RSVPs
