# JARVIS Web

A responsive, installable-style web JARVIS dashboard inspired by the supplied Stark Industries HUD screenshot.

## Included
- Responsive cyan/black HUD interface with reactor visualization, system tiles, message log and voice controls
- Browser speech recognition (where supported)
- OpenAI Responses API chat through a Node backend
- Fish Audio TTS through the Node backend
- Automatic MP3 saving in the browser after each generated reply
- Manual "Save last audio" button
- API keys stored only in backend environment variables

## Run locally
Requirements: Node.js 20+

```bash
cd server
cp .env.example .env
# Edit .env and add your keys
npm install
npm start
```

Open `http://localhost:8787`.

## Environment
- `OPENAI_API_KEY` — required for AI responses
- `FISH_API_KEY` — required for Fish Audio speech
- `FISH_REFERENCE_ID` — optional voice reference ID for a male voice you are licensed to use
- `OPENAI_MODEL` — defaults to `gpt-6-astra` in this starter; set this to a model available to your OpenAI account
- `FISH_MODEL` — defaults to `s2.1-pro`

## Deploy publicly
Deploy this folder to a Node-capable host (for example Render, Railway, Fly.io, or your own server). Add environment variables in the host dashboard, then open the HTTPS URL. This project does not create a public deployment or obtain API credentials on your behalf.

Before public use, add authentication, rate limiting, HTTPS, and usage monitoring. The included CORS setting is permissive for easy local testing; restrict it to your deployed domain in production.

## Browser notes
Speech recognition support varies by browser. Chrome on Android and desktop is generally the best target. If speech recognition is unavailable, type in the message box. Audio is saved through the browser download mechanism; some browsers may ask where to save it.
