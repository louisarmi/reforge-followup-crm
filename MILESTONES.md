# RepForge V1 – Milestones

## Milestone 1 – Project Setup (2–3 days)
- Create Next.js project (App Router, TypeScript)
- Connect Supabase (Auth + Postgres)
- Set up basic layout shell (left menu, empty client list)
- Deploy initial app to Vercel

Deliverable: running skeleton app with login and empty dashboard.

---

## Milestone 2 – Client Model & Basic CRM (5–7 days)
- Create DB tables for:
  - users
  - clients
  - interactions (notes, calls)
- Implement:
  - Add client form (manual fields)
  - Client list (grid/list on the right)
  - Client profile view (read/write)
- Filter views for:
  - All clients
  - Uncontacted
  - Callbacks
  - Sold

Deliverable: working CRM with manual data entry, no AI yet.

---

## Milestone 3 – AI Notes & Scoring (Manual Mode) (5–7 days)
- Add free-text notes input to client profile
- Add “Update AI Summary & Scores” button
- AI consumes:
  - Client fields
  - Notes
- AI outputs:
  - Summary text
  - Scores based on status:
    - Uncontacted: contact likelihood, lead quality, urgency
    - Callback: sale likelihood, appointment strength, urgency
    - Sold: retention risk, upsell opportunity, important-date urgency
- Display scores on client cards and client profile

Deliverable: AI works using **only manual input** (no audio yet).

---

## Milestone 4 – Call Recording Upload & Enrichment (7–10 days)
- Add “Upload Call Recording” feature for a client
- Save audio file to storage (Supabase)
- Transcribe call with Whisper/OpenAI
- AI:
  - Extracts missing client fields (age, state, budget, etc.)
  - Updates notes
  - Updates scores
  - Updates next follow-up date + reason

Deliverable: agent can upload audio, and AI enriches the client automatically.

---

## Milestone 5 – “Today” Priority View & Polish (5–7 days)
- Implement “Today” view:
  - Sorted list of clients who need attention today
  - Based on:
    - upcoming draft dates
    - upcoming start dates
    - overdue callbacks
    - high-risk clients
- Basic analytics panel (total clients, callbacks, at-risk, etc.)
- UI/UX polish, bug fixes
- Prepare for production handover

Deliverable: fully usable V1 with daily workflow and AI follow-up brain.
