# Language Coach

## Purpose
A voice and text conversation app that helps users improve their French, Italian, Spanish, or Portuguese through natural, intelligent conversation with Claude. Designed for educated adults who want to discuss real topics — current affairs, markets, medicine, women's sports, culture — not simplified textbook scenarios.

## Tech Stack
- **Single HTML file** (`index.html`) with embedded JavaScript and CSS
- **Claude API** — conversation intelligence (model: claude-sonnet-4-6)
- **Vercel serverless function** (`api/chat.js`) — proxies Claude API requests so users don't need their own API key
- **Web Speech API** — speech-to-text (Chrome/Android only; not supported on iOS)
- **Browser Speech Synthesis** — text-to-speech with preferred native voices per language
- **localStorage** — session memory and usage tracking

## Deployment
- **Hosted version:** [languagecoach.vercel.app](https://languagecoach.vercel.app) — deployed via Vercel, no API key needed for users
- **GitHub Pages:** [amuhed.github.io/languagecoach](https://amuhed.github.io/languagecoach) — static, users need own API key
- **Local dev:** `python3 -m http.server 8000` then open `http://localhost:8000` in Chrome

## Key Design Decisions
- **Vercel proxy** — `api/chat.js` holds the API key server-side via `ANTHROPIC_API_KEY` env var; users on the hosted version need no setup
- **Direct API fallback** — when running locally or on GitHub Pages, users enter their own API key (stored in localStorage)
- **Single file architecture** — all UI in `index.html` for portability
- **localStorage for persistence** — keyed by language (`languageCoach_[language]_profile`)
- **Dynamic system prompt** — built from stored user profile including past session summaries and recurring errors
- **CEFR levels A1–C1** — language complexity calibrated per level; ideas never simplified, only language
- **Corrections embedded in conversation** — no explicit lesson mode; errors restated naturally
- **End-of-session summary** — Claude switches to English, gives brief feedback, outputs structured JSON for localStorage update
- **Voice selection** — caches preferred female native voices per language per session; blocks macOS novelty voices (Grandma, Rocko, etc.)
- **Speech interrupt** — user can stop Claude speaking by clicking mic, typing, or starting a new message

## Known Limitations
- **iOS Safari** — Web Speech API (mic input) is not supported. Text input works fine. Speech synthesis is partial.
- **Voice quality varies by OS** — macOS has good premium voices (downloadable via System Settings > Accessibility > Spoken Content > Manage Voices). Other platforms use whatever the browser provides.
- **Next step:** Capacitor wrapper planned to provide native speech on iOS

## Commands
- No build step, no dependencies, no package.json
- Open `index.html` in Chrome for local use
- Deploy to Vercel by connecting the GitHub repo and setting `ANTHROPIC_API_KEY` env var
