# Acceptance Criteria (MVP)

## Auth
- A user can sign up and log in successfully
- Logging out returns user to auth screen
- A profile row is created for each new user (or on first login)

## Map
- Map loads without crashing
- Events within the selected radius appear as pins
- Tapping a pin opens an event preview
- Tapping preview opens event details

## Events
- Host can create an event with required fields
- Event appears on map after creation
- Event details show title, time, location, host, and description

## RSVP
- Logged-in user can RSVP to a free event
- RSVP state is reflected on the event details screen
- User can view their RSVPs (simple list)

## Security (Baseline)
- Users cannot edit/delete events they don’t own
- Users cannot read RSVPs that aren’t theirs (unless host read is added)
- Reports can be created by logged-in users
