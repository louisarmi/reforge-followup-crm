# RepForge Frontend

This folder will contain the main **Next.js** application for RepForge.

RepForge is an AI-powered follow-up CRM for insurance agents. The frontend is a desktop-first web app where agents can:

- See a **daily “Today” list** of who to call and why  
- Browse their **clients, callbacks, and leads**  
- Open **client sheets** and edit them while on the phone  
- Trigger **AI updates** for scores, summaries, and follow-ups  
- Upload **call recordings** to enrich client profiles (optional)

---

## 🔧 Responsibilities

The frontend is responsible for:

- Authentication UI (login/signup)
- Layout with:
  - Left sidebar menu (Today, All Contacts, Leads, Callbacks, Clients, High Risk, High Opportunity, Birthdays, Analytics)
  - Right side: client cards grid or list
- Client card UI (name, status, key scores, short AI summary)
- Client profile UI:
  - Client sheet fields (identity, policy, health, notes, dates)
  - Notes and history
  - AI summary and scores
  - Buttons for:
    - “Update AI” (re-score + re-summarize)
    - “Upload Recording” (hooks into backend)
- Today view:
  - Ordered list of priority clients for the day
- Basic analytics view (count of clients, leads, callbacks, etc.)

---

## 📦 Planned Tech Stack

- Next.js (App Router)
- React
- TypeScript
- Tailwind CSS
- Supabase client for auth & data
- Fetch calls to AI + backend endpoints

---

## 🧪 Local Development (Expected)

Once implemented:

```bash
cd frontend
npm install
npm run dev
The app will expect environment variables defined in the root .env / .env.local.
