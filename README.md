# Language Coach

A voice and text conversation app for practicing French, Italian, Spanish, or Portuguese with Claude as your conversation partner.

Designed for educated adults who want to discuss real topics — current affairs, markets, medicine, women's sports, culture — at their level.

## Use it online

**[languagecoach.vercel.app](https://languagecoach.vercel.app)**

Open the link, choose your language and level, and start talking. No API key or account needed.

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
- **Voice input** — speak using your microphone (Chrome and Android)
- **Voice output** — hear Claude's responses via browser speech synthesis
- **Interrupt anytime** — click mic or start typing to stop Claude mid-sentence
- **Subtle corrections** — grammar and vocabulary errors corrected naturally within conversation
- **Session memory** — picks up where you left off, tracks recurring errors
- **End-of-session feedback** — brief English summary of patterns to watch and things you did well
- **No setup for users** — hosted version proxies the API, no key needed

## Browser Support

| Feature | Chrome desktop | Chrome Android | iOS Safari |
|---|---|---|---|
| Conversation | Yes | Yes | Yes |
| Text input | Yes | Yes | Yes |
| Voice input (mic) | Yes | Yes | No |
| Voice output | Yes | Yes | Partial |

Voice input requires Chrome due to Web Speech API support. On iOS, the app works in text-only mode.

## Privacy

- No login, no account, no analytics, no tracking
- Conversation data stays in your browser's localStorage
- Hosted version routes through a Vercel proxy — no API keys stored in the browser
- Local version: your API key is stored only in localStorage

## Deploy your own

1. Fork this repo
2. Import to [Vercel](https://vercel.com)
3. Add environment variable: `ANTHROPIC_API_KEY` = your key from [Anthropic](https://console.anthropic.com/)
4. Deploy

Set a monthly spending limit at [console.anthropic.com/settings/limits](https://console.anthropic.com/settings/limits) to control costs.
