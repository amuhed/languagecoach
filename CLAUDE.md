# Language Coach

## Purpose
A voice and text conversation app that helps users improve their French, Italian, Spanish, or Portuguese through natural, intelligent conversation with Claude. Designed for educated adults who want to discuss real topics — current affairs, markets, medicine, women's sports, culture — not simplified textbook scenarios.

## Tech Stack
- **Single HTML file** with embedded JavaScript and CSS
- **Claude API** — conversation intelligence (model: claude-sonnet-4-6)
- **Web Speech API** — speech-to-text (Chrome built-in)
- **Browser Speech Synthesis** — text-to-speech
- **localStorage** — session memory and usage tracking
- No backend, no framework, no installation required

## Key Design Decisions
- **No API key in source** — user enters their Claude API key on first use; stored in localStorage
- **Single file architecture** — everything in `index.html` for zero-install portability
- **localStorage for persistence** — keyed by language (`languageCoach_[language]_profile`)
- **Dynamic system prompt** — built from stored user profile including past session summaries and recurring errors
- **CEFR levels A1–C1** — language complexity calibrated per level; ideas never simplified, only language
- **Corrections embedded in conversation** — no explicit lesson mode; errors restated naturally
- **End-of-session summary** — Claude switches to English, gives brief feedback, outputs structured JSON for localStorage update
- **Mobile-first design** — clean, minimal, conversation-centered

## Commands
- Open `index.html` in Chrome — no build step needed
- No tests, no dependencies, no package.json
