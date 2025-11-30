```md
# RepForge Backend

The backend for RepForge is implemented using **Next.js server actions and API routes**, plus **Supabase** for database, auth, and storage.

There is no separate Express server in V1. Backend logic lives inside the Next.js app.

---

## 🧠 Responsibilities

The backend is responsible for:

- Authentication (via Supabase)
- CRUD operations for:
  - Clients
  - Notes
  - Calls / recordings
  - Scores
  - Follow-ups
- AI integration flows:
  - Sending data to AI (OpenAI / Anthropic)
  - Transcription via Whisper or similar
  - Updating summaries and scores
- “Today” view logic:
  - Selecting which clients are due/overdue
  - Combining urgency, risk, and opportunity signals

---

## 🗂 API Structure (Planned)

Expected route areas (under `app/api/...` in the Next.js app):

- `/api/clients` – create, read, update clients
- `/api/notes` – attach notes to clients
- `/api/calls` – upload metadata for call recordings
- `/api/transcribe` – trigger transcription for an uploaded recording
- `/api/ai/summarize` – generate notes + summaries
- `/api/ai/score` – generate scores based on state and data
- `/api/today` – compute the “Today” prioritized list

Exact implementation details can be refined by the developer as long as behavior matches the blueprint.

---

## 🗄 Supabase Data Model (High-Level)

Expected tables:

- `users`
- `clients`
- `calls`
- `notes`
- `scores`
- `followups`

With row-level security (RLS) so that:

- Agents only see their own data (V1)
- Admin/agency views can be added later

---

## 🔊 Audio & Transcription Flow

For call recording uploads:

1. Frontend uploads audio (MP3/M4A/WAV) → stored in Supabase Storage.  
2. Backend receives a reference to the recording.  
3. Backend sends audio or URL to **transcription API** (Whisper, etc.).  
4. Backend sends transcript + existing client data to the **AI analysis** endpoint.  
5. AI returns:
   - Clean notes
   - Updated fields (suggestions)
   - Updated scores
   - Follow-up recommendation  
6. Backend stores updated notes/scores and returns to frontend.

---

## 🤖 AI Logic (Integration Point)

The backend will:

- Format prompts for AI models
- Ensure status-based logic is applied:
  - Uncontacted, Callback, Sold
- Combine:
  - Structured client data
  - Manual notes
  - Transcript (if available)

The actual scoring logic and field extraction rules are described in the `ai/` docs.

---

This README serves as a high-level guide for backend architecture and expectations.
