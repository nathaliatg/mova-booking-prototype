# MOVA — class booking prototype

> Move well. Feel better.

A frontend-only prototype for a small boutique studio (MOVA) that wants members to book classes online, and the owner to manage the schedule without a spreadsheet. Built for the follow-up "lead check" interview after the client requirements meeting.

## Run it

No install, no build. Everything is in `index.html`.

- **Just open it:** double-click `index.html` (needs internet once: the UI library and fonts load from a CDN).
- **Or serve it:** `npx serve .` and open the printed URL.
- **Deploy it:** drag this folder onto [Netlify Drop](https://app.netlify.com/drop), or import the repo into Vercel / GitHub Pages. It is a static site, so no settings are needed.

Data lives in memory: refresh the page to restart the demo. Add `#admin` to the URL to open the admin view directly.

## What the client asked for → what's here

| Client need (from the meeting) | In the prototype |
|---|---|
| Members book instead of calling / DMing | **Member view:** weekly schedule, filter by class type, book in one tap (with undo), cancel, "My bookings" |
| Overbooking, no live view of capacity | Every class shows live capacity: spots booked, spots left, full |
| Cancellations lose the spot at the last minute | **Waitlist with auto-refill:** a cancellation books the next person in line and notifies them |
| Manage everything without the spreadsheet | **Admin view:** KPIs, "needs attention", live activity feed, schedule, create / cancel classes, change capacity, roster and waitlist per class |
| Still takes phone and DM bookings | Admin can add or remove members on their behalf, and **add brand-new members** (Members tab, or straight from a class) |

## Suggested demo flow (5 min)

1. **Member view:** browse the week, book a class, see the toast and the capacity update.
2. Open **My bookings:** Ana is #1 on the waitlist for tomorrow's Mat Pilates.
3. **Demo tools → Simulate a cancellation:** someone drops out, Ana is booked automatically, the bell lights up.
4. Switch to **Admin view:** "Refilled this week" went up, the activity feed shows what happened.
5. Open a class (**Manage**): raise capacity and watch the waitlist get seated; add a member by phone, including someone new to the studio.
6. **Demo tools → Requirements & open questions:** walk through assumptions and what to confirm with the client.

## Scope trade-offs

Built: the core booking loop, waitlist, and owner dashboard. Skipped on purpose: real auth, payments and memberships, real notifications, recurring schedules, reporting. They appear as open questions in the app.

## Tech

Single static file. Preact + htm loaded from jsDelivr (no JSX compiler, no bundler), Fraunces and Figtree from Google Fonts. Built with Claude Code. Throwaway code by design.
