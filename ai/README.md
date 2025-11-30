# RepForge AI – Scoring, Notes, and Analysis

This folder documents how the AI layer in RepForge should behave.

RepForge uses AI to:

- Clean and summarize agent notes
- Analyze call transcripts (when available)
- Score clients differently based on their status
- Recommend follow-up timing and reasons
- Suggest what to say next time

---

## 🧩 Overview of the AI Pipeline

For each client, AI can be triggered in two main ways:

1. **Manual Mode** – Agent fills client sheet and notes (no recording required).  
2. **Recording Mode** – Agent uploads a call recording and AI transcribes and enriches.

Both modes feed into the same scoring and summary logic, but with more confidence when a transcript is present.

---

## 📄 Inputs to AI

The AI receives:

- Client status:
  - `uncontacted`
  - `callback`
  - `client` (sold)
- Structured client fields:
  - Name, age/DOB, state
  - Policy type, carrier, premium, start date, draft date
  - Lead source, goals, objections
  - Health notes and risk flags
- Notes:
  - Agent-typed free text
  - Historical notes/summary if needed
- Transcript (optional):
  - Full text of a call, when uploaded

---

## 🧠 Outputs from AI

The AI must generate:

1. **Summary**
   - 3–6 bullet points describing:
     - Who the client is
     - What they want
     - What was discussed last time
     - Any concerns or objections

2. **Scores** (0–100 range)
   - For **Uncontacted Lead**:
     - `contact_likelihood`
     - `lead_quality`
     - `attempt_urgency`
   - For **Callback / In-Progress**:
     - `sale_likelihood`
     - `followup_urgency`
     - `appointment_strength`
     - `objection_difficulty`
   - For **Sold Client**:
     - `retention_risk`
     - `chargeback_risk`
     - `upsell_opportunity`
     - `relationship_strength`
     - `important_date_urgency`

3. **Next Follow-Up Recommendation**
   - Suggested follow-up date (e.g. “in 2 days”, “in 1 month”)
   - Short reason (e.g. “Confirm draft details”, “Check comfort after first payment”)

4. **Suggested Script / Angle**
   - A short paragraph or 3–5 bullets:
     - How to open the call
     - Main angle to focus on (reassurance, urgency, upsell, saving the policy, etc.)

---

## 🧪 Manual Mode vs Recording Mode

### Manual Mode
- Input: structured data + agent notes.
- No transcript.
- AI **must not invent details** — only work from what’s provided.
- Good for:
  - Agents who don’t record calls
  - Quick in-call updates
- Scores are generated from information, not tone.

### Recording Mode
- Input: structured data + transcript + notes (optional).
- AI can use:
  - Tone indicators in the transcript
  - Phrases that show doubt, excitement, or urgency
- Better for:
  - Estimating chargeback risk
  - Appointment strength
  - Relationship strength

---

## 🧷 Status-Aware Logic

The AI must always be aware of **status**:

- **Uncontacted**:
  - Focus on whether they seem worth pursuing and when.
- **Callback**:
  - Focus on closability, objection type, how soon to follow up.
- **Client (Sold)**:
  - Focus on retention, satisfaction, and opportunities.

---

## 🏗 Implementation Notes

- The actual prompts can be stored as templates (JSON or text) and adjusted during development.
- Models:
  - GPT-4-class or Claude 3.5 for analysis and scoring
  - Whisper (or equivalent) for transcription

This folder defines how the AI is expected to think so developers can implement consistent and predictable behavior.
