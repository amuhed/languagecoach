# Language Coach

A voice and text conversation app for practicing French, Italian, Spanish, or Portuguese with Claude as your conversation partner.

Designed for educated adults who want to discuss real topics — current affairs, markets, medicine, women's sports, culture — at their level.

## Use it online

**[amuhed.github.io/languagecoach](https://amuhed.github.io/languagecoach)**

Open the link in Chrome, enter your Claude API key, and start talking.

## Run locally

If you prefer to run it on your own machine:

1. Clone the repo
2. Serve over localhost (needed for microphone permissions):
   ```
   python3 -m http.server 8000
   ```
3. Open **http://localhost:8000** in Chrome
4. Enter your [Claude API key](https://console.anthropic.com/) when prompted
5. Choose your language and level, start talking

## Features

- **Natural conversation** — Claude adapts to your CEFR level (A1–C1) and follows your lead on topics
- **Voice input** — speak using your microphone via Web Speech API
- **Voice output** — hear Claude's responses via browser speech synthesis
- **Subtle corrections** — grammar and vocabulary errors corrected naturally within conversation
- **Session memory** — picks up where you left off, tracks recurring errors
- **End-of-session feedback** — brief English summary of patterns to watch and things you did well

## Requirements

- Google Chrome (for Web Speech API support)
- A Claude API key from [Anthropic](https://console.anthropic.com/)

## Privacy

- Your API key is stored only in your browser's localStorage
- No data is sent anywhere except the Claude API
- No analytics, no tracking, no accounts
