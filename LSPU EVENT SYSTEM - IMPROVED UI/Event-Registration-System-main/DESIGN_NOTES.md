# Premium front-end redesign: notes

Only `static/style.css`, `static/app.js` (new) and everything in `templates/` changed.
`app.py`, `services/`, `tests/`, `requirements.txt` and `README.md` are byte-for-byte unchanged.
The fonts (DM Sans, Manrope) and the colour palette are the project's originals.

## What moved
- Role navigation in the header (Admin: Overview, Attendance, Directory. Professor: Roster, Attendance. Student: Events).
- Change password and Log out now live in an account menu.
- Event photos (already uploaded by admins) now appear on event cards, the event page, the landing spotlight and admin rows.
- The registration form sits in a sticky "Reserve your seat" panel beside the event details.
- Admin event actions: Registrations / Expenses / Edit stay visible; Pin, Archive and Delete are in a "more" menu.
- Deleting uses a confirmation dialog instead of the browser pop-up.

## Fixed while redesigning (placement, not behaviour)
- `professor.html` never linked the CSV export that `app.py` provides. The "Export CSV" button is now on the roster page.
- The admin stat "System status: Running" was static text. It is now "Happening now", a real count of ongoing events.
- `professor.html` listed "Archived Event Attendance" from a `past_events` variable that `app.py` never passes, so it was always empty. It now shows only if that variable is provided.

## Things to know (not changed, because they live in the backend)
- `accounts.html` and `account_form.html` have no matching routes in `app.py` (there is no `accounts` or account-edit route),
  so they are unreachable. They were restyled but cannot be opened. The README still mentions admin account editing.
- Admins can no longer create accounts; accounts are made by self-registration.
- OTP codes are printed in the Flask terminal (development only).
- Times are shown as stored (server time or UTC, depending on the field).
