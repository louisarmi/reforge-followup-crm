# Contributing to RepForge

Thank you for your interest in contributing to RepForge, an AI-powered follow-up CRM for insurance agents.

This document explains how developers should work in this repository and keep things consistent.

---

## 📘 Before You Start

Please read:

- README.md  
- MILESTONES.md  
- docs/V1_BLUEPRINT.md  

You should be comfortable with:

- Next.js (App Router + React + TypeScript)  
- Supabase (Auth + Postgres + Storage)  
- Working with AI APIs (OpenAI, Anthropic, Whisper, etc.)  

---

## 🧱 Project Structure (High-Level)

repforge-followup-crm/  
• README.md  
• MILESTONES.md  
• CONTRIBUTING.md  
• LICENSE  
• .env.example  
• .gitignore  
• docs/  
• frontend/  
• backend/  
• ai/  

---

## 🔀 Branch & PR Workflow

- Create a new branch for each feature or fix:
  - `feature/live-scoring`
  - `feature/today-view`
  - `fix/score-calculation`
  - `docs/update-blueprint`

- Keep pull requests **focused**:
  - One feature per PR
  - Or one bug fix per PR
  - No giant mixed changes

---

## 🧹 Code Style

- Use **TypeScript**.
- Use a formatter like **Prettier**.
- Keep naming consistent:
  - Components → `ClientCard.tsx`, `Sidebar.tsx`
  - Hooks → `useClientScores.ts`
  - Utilities → `scoreClient.ts`
  - API routes → `route.ts` files in `app/api/...`

---

## 📝 Commit Messages

Use clear, descriptive messages, e.g.:

- `feat: add client card grid layout`
- `feat: implement AI scoring for callbacks`
- `fix: correct follow-up date calculation`
- `docs: update V1 blueprint`
- `chore: clean up env example`

Avoid vague messages like `update`, `misc`, or `fix stuff`.

---

## 🔐 Environment Variables

- Do **not** commit `.env` files.
- Only `.env.example` should be updated to reflect new config keys.
- Never commit:
  - API keys
  - Supabase keys
  - Service role keys
  - Stripe secrets
  - Any credentials

---

## 🧪 Running Locally (Expected)

In the frontend app (once created under `frontend/`):

1. Install dependencies  
   `npm install`
2. Run dev server  
   `npm run dev`

You must configure:

- Supabase project + keys  
- Database tables (clients, calls, scores, etc.)  
- AI provider keys (OpenAI / Anthropic / Whisper)  

---

## ✔ Pull Requests

A good PR should include:

- What changed  
- Why it changed  
- How to test it  
- Confirmation that no secrets/keys are included  

PRs that introduce secrets, break the structure, or are too large/unfocused may be rejected or requested to be split.

---

## 💬 Questions

For questions, discuss via:

- GitHub Issues  
- Private communication with the project owner (off-platform)

Thank you for helping improve RepForge.
