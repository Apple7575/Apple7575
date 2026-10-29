# DdakKok Web Frontend

[Korean project README](https://github.com/peanut-works/ddakkok-web/blob/main/README.md) · **English**

A presentation demo for **DdakKok (딱콕)**, an AI-assisted product safety service for caregivers of young children. The product concept compares ingredient information with child-specific allergy and health profiles and presents alerts and explanations.

This repository contains the **React web frontend**, not the complete backend or AI service. It integrates with an existing FastAPI backend and includes local mock-data behavior for demonstrations.

## Portfolio context

Sucheol Jang contributed to product/AI architecture and system integration and led frontend development for the DdakKok hackathon team. The team received the **Korea Chamber of Commerce and Industry Chairperson's Award** at the **2026 SSAFY × Kakao Tech AI Hackathon**.

These are team-project responsibilities and recognition; this repository is a presentation frontend, rather than evidence that every backend or AI component was implemented here.

## Stack

- React 18, TypeScript, Vite
- React Router
- CSS and the Pretendard font
- REST API integration with bearer-token authentication

## Run locally

Use a Node.js environment compatible with the repository's Vite 5 and TypeScript dependencies.

```bash
git clone https://github.com/peanut-works/ddakkok-web.git
cd ddakkok-web
npm ci
npm run dev
```

Use the local URL printed by Vite (normally port 5173; another port may be selected if busy).

Create a local `.env` file as needed:

```dotenv
VITE_API_URL=http://localhost:8000
VITE_WAITLIST_KEY=
```

`VITE_API_URL` is the backend base URL, without a trailing slash. Leave the waitlist key empty for a local-only demonstration. Vite environment variables are bundled into client-side code; do not put private server credentials in them.

Build and preview:

```bash
npm run build
npm run preview
```

The current build script removes `src/app` and `src/imports` if present before running TypeScript and Vite. Those paths are not present in the inspected repository tree; retain uncommitted work elsewhere before using that script.

## Demo walkthrough

1. Open the landing page.
2. Select **체험하기** (Try the demo).
3. Inspect the dashboard, classrooms, child profiles, and safety-check history.
4. Open a check to inspect per-child results, ingredients, and explanations.

The demo login attempts `POST /api/auth/demo`. A recognized network error activates bundled mock data; HTTP errors are not treated as offline success. Normal email login requires a working backend.

## Screens

| Route | Purpose |
| --- | --- |
| `/` | Product introduction and demo entry |
| `/login` | Teacher login |
| `/dashboard` | Recall, expiry, and caution summaries |
| `/children` | Classroom child list |
| `/children/:id` | Child profile and local edits |
| `/checks` | Safety-check history and status filter |
| `/checks/:id` | Ingredient details, per-child results, and explanations |

## Architecture and implementation evidence

- [API client](https://github.com/peanut-works/ddakkok-web/blob/main/src/lib/api.ts): typed requests, bearer headers, 401 session clearing, and mock-data fallback.
- [Local child overlay](https://github.com/peanut-works/ddakkok-web/blob/main/src/lib/localChildren.ts): additions and edits stored in browser localStorage and merged with server results.
- [Waitlist behavior](https://github.com/peanut-works/ddakkok-web/blob/main/src/lib/waitlist.ts): local persistence and optional external submission.
- [API specification](https://github.com/peanut-works/ddakkok-web/blob/main/api.yaml): backend interface reference.
- [Landing screenshot script](https://github.com/peanut-works/ddakkok-web/blob/main/scripts/shoot.mjs): visual inspection utility.

Child creation and edits in this presentation frontend are **local browser changes**, not server-persisted CRUD. Backend lookup and AI behavior are separate from that local overlay.

## Validation status and limits

- `npm run build` runs TypeScript build checks and the Vite production build.
- No `test` script is defined in the inspected `package.json`.
- Screenshot scripts exist, but they are visual utilities, not assertion-based automated tests. The landing script hardcodes a Windows Chrome path and defaults to port 5174.
- Documentation was checked against repository sources; no new build, automated test pass, clinical validation, or performance result is claimed by this guide.
- Mock check results demonstrate the UI, not live AI inference.
- The waitlist displays a seeded demo base count; it is **not a verified user or sign-up metric**. Local success does not prove external email delivery.
- Use synthetic child profiles when reviewing this demo.

## Optional landing assets

Place `scrub.mp4`, `teacher.jpg`, and `kids.jpg` in `public/assets/` to replace the corresponding placeholders. See the [Korean README](https://github.com/peanut-works/ddakkok-web/blob/main/README.md) for asset specifications and optional waitlist setup.
