# RepForge – AI Follow-Up CRM for Insurance Agents

RepForge is an AI-powered **follow-up CRM** built for insurance agents.

Agents use RepForge to:

- Store their **book of business**, callbacks, and leads
- Fill out **client sheets while on the phone**
- Get **live AI-scored priority** (who to call, when, and why)
- Get **clean AI notes** and summaries from calls and manual input
- Upload **call recordings** for deeper AI analysis (optional)

RepForge is NOT a dialer. It works **alongside any dialer** as the agent’s personal follow-up brain.

---

## 🔑 Core V1 Features

### 1. Client Sheets (Manual + AI-Enriched)
For each client or lead, agents can:

- Fill out a structured client sheet:
  - Name, phone, email, state, age/DOB
  - Policy type, carrier, premium, start date, draft date
  - Lead source, goals, objections
  - Health notes, risk notes
- Type free-form notes while on the call
- Optionally upload a **call recording** to let AI:
  - Transcribe the call
  - Extract missing details
  - Clean and structure notes

If there is **no recording**, AI still uses the agent’s manual input to:
- Generate summaries
- Suggest follow-up timing
- Score the client

---

### 2. Live Scoring While on the Phone

As the agent types notes and updates fields on the client sheet, AI can be triggered to:

- Refresh scores in real time or on button click
- Update:
  - Sale likelihood (for callbacks)
  - Contact likelihood (for uncontacted leads)
  - Retention / chargeback risk (for sold clients)
  - Upsell opportunity
  - Follow-up urgency

This gives the agent **live feedback** on who is most important to follow up with and how.

---

### 3. Status-Based Scoring (Three States)

Each contact lives in one of three states:

1. **Uncontacted Lead**  
   - Scores for: contact likelihood, lead quality, urgency.

2. **Callback / In-Progress**  
   - Scores for: sale likelihood, appointment strength, objection difficulty, urgency.

3. **Sold Client**  
   - Scores for: retention/chargeback risk, upsell opportunity, relationship strength, important-date urgency (start date, draft date, birthdays, etc.).

AI uses both **structured fields** and **notes/transcripts** to compute these.

---

### 4. Left Menu + Client Card Grid

The main app layout:

- **Left side:** menu with:
  - Today
  - All Contacts
  - Uncontacted Leads
  - Callbacks / Follow-Ups
  - Sold Clients
  - High Risk (chargeback/lapse)
  - High Opportunity (upsell)
  - Birthdays
  - Analytics

- **Right side:** scrollable **grid or list of client cards**. Each card shows:
  - Name + avatar (initial-based in V1)
  - Status badge (Uncontacted / Callback / Client)
  - Policy type + carrier + premium
  - Next follow-up date + reason
  - 1–3 key scores (depending on status)
  - Short AI summary (1–2 lines)

Clicking a card opens the full client profile.

---

### 5. Client Profile View

When viewing a client:

- Header:
  - Name
  - Avatar
  - Status
  - Key dates (start, draft, birthday)
  - Key scores
- Sections:
  - Overview (AI summary of the relationship)
  - Notes (AI notes + manual notes)
  - Timeline (past interactions)
  - Policies (carrier, premium, status)
  - Scores
  - Files/recordings (optional)

Agents can edit fields, add new notes, and trigger AI to refresh scores and summaries.

---

## 🧩 Tech Stack (Preferred)

- **Frontend:** Next.js (App Router), TypeScript, Tailwind
- **Backend:** Next.js API routes / server actions
- **Database & Auth:** Supabase (Postgres + Auth)
- **Storage:** Supabase Storage (for audio)
- **AI:** OpenAI / Whisper / Claude
- **Hosting:** Vercel

---

## 📄 Documentation

- `README.md` – high-level overview
- `MILESTONES.md` – development phases
- `docs/V1_BLUEPRINT.md` – detailed behavior and flows

---

## 🧑‍💼 Contact

This repository is for the RepForge V1 build.

For questions, please coordinate through the project owner off-platform.
