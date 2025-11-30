# RepForge V1 – Detailed Blueprint

RepForge is an **AI-powered follow-up CRM** for insurance agents.

Agents input their **sold clients, callbacks, and leads**, and RepForge tells them:

- Who to call today
- Why to call them
- When to call them
- What to say
- What happened last time

RepForge supports both:
- **Manual client sheets** (typed by agent)
- **Call recording uploads** (AI transcribes and enriches)

---

## 1. Client States

Each client is tagged as:

1. **Uncontacted Lead**
2. **Callback / In-Progress**
3. **Sold Client**

The AI changes its scoring logic based on this state.

---

## 2. Client Sheet

Core fields:

- Name, phone, email, state, age/DOB
- Status: Uncontacted / Callback / Client
- Policy info (for clients):
  - Type (FE/Term/IUL/Annuity/etc.)
  - Carrier
  - Coverage amount
  - Monthly premium
  - Start date
  - Draft date
- Health notes
- Lead source
- Objections
- Goals
- Custom notes

Agents can:

- Fill this out manually
- Add/edit notes
- Attach call recordings

---

## 3. Two Input Modes

### A. Manual Mode

Agent fills the client sheet + types notes.

AI will:

- Generate a short client summary
- Suggest next follow-up date and reason
- Score the client based on status:
  - Uncontacted: contact likelihood, lead quality, urgency
  - Callback: sale likelihood, appointment strength, urgency
  - Sold: retention risk, upsell opportunity, important-date urgency

### B. Recording Mode

Agent uploads a call recording for a client.

System will:

- Transcribe the call
- Extract missing fields (age, state, budget, etc.)
- Clean and structure notes
- Update scores with more confidence (sentiment and tone)
- Update next follow-up date and reason

Agent can review and confirm suggested changes.

---

## 4. Live Scoring While on Call

While the agent is on the phone and typing:

- They can quickly update fields and notes
- A button (e.g. “Refresh AI Scores”) triggers:
  - Updated summary
  - Updated scores
  - Updated follow-up recommendation

The UI should be fast enough that an agent can:
- Type notes during the conversation
- Hit refresh
- Immediately see updated scores and next actions

---

## 5. Main Layout

### Left Menu

- Today
- All Contacts
- Uncontacted Leads
- Callbacks / Follow-Ups
- Sold Clients
- High Risk
- High Opportunity
- Birthdays / Events
- Analytics

### Right Content

- For list views:
  - Scrollable grid or list of **client cards**
- For profile view:
  - Full client info panel

---

## 6. Client Cards

Each card shows:

- Name + avatar (initial-based in V1)
- Status (Lead / Callback / Client)
- Policy summary (if client)
- Next follow-up date + reason
- 1–3 key scores (based on state)
- 1–2 line AI summary

Click opens full client profile.

---

## 7. Today View

Combines:

- Draft date alerts
- Start date alerts
- Scheduled callbacks
- Overdue follow-ups
- High-risk clients

Sorted by importance based on AI scoring and time sensitivity.

---

## 8. Tech Notes (High-Level)

- Email/password auth (via Supabase)
- Single organization per user (V1)
- Agents only see their own data (V1)
- Admin/agency view can be added later

---

This blueprint should guide the full V1 build and be kept up-to-date as the product evolves.
