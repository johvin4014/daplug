# Supabase RLS Policy Plan (MVP)

## Goals
- Public can read public events
- Only hosts can create events
- Only event owner (host) can update/delete their own events
- Users can RSVP to events
- Users can only view/manage their own RSVPs
- Users can create reports; only admins can read reports (later)

> NOTE: This is a planning doc. Implementation can be added later as SQL.

---

## profiles
### Reads
- Users can read public profile fields (optional)
### Writes
- Users can insert/update ONLY their own profile

Policy ideas:
- INSERT: auth.uid() = id
- UPDATE: auth.uid() = id

---

## events
### Reads
- Anyone can read events where is_public = true
- (Optional later) logged-in users can read private events they are invited to

### Writes
- INSERT: auth.uid() = host_id
- UPDATE: auth.uid() = host_id
- DELETE: auth.uid() = host_id

---

## rsvps
### Reads
- Users can read ONLY their own RSVPs
- (Optional) Hosts can read RSVPs for events they own

### Writes
- INSERT: auth.uid() = user_id
- UPDATE: auth.uid() = user_id
- DELETE: auth.uid() = user_id

---

## reports
### Reads
- Default: no public reads
- Admin-only reads (later role/claim)

### Writes
- INSERT: auth.uid() = reporter_id
- UPDATE/DELETE: none (or admin-only)

---

## Storage (Images)
Buckets:
- event-images (public read)
- avatars (public read)
Rules:
- Only logged-in users can upload
- Only owner can overwrite/delete their own uploads (best-effort)

---

## Future Hardening (Post-MVP)
- API layer for stricter rate limiting
- Device/IP-based throttling
- Anti-spam checks for event creation
