# CalTrack 🍛

A phone-first calorie and nutrition tracker built for Sri Lankan food, with AI photo scanning and a weight-gain focus.

## Features
- **📸 Photo scanning**: snap your plate and Claude lists every item (rice by variety, curries, sambols, papadam…) with calories, protein, carbs, fat, fibre, sugar and sodium. You can change each portion or remove items before logging.
- **🍚 Sri Lankan food database**: 140+ foods (red/white/samba/keeri samba rice, rice & curry plates, kottu, hoppers, string hoppers, pittu, dhal, polos, wade, kiribath, watalappan and more). Works offline, no key needed.
- **🎯 Goals**: gain fast / gain / lean bulk / maintain / lose. Calorie and macro targets come from the Mifflin-St Jeor formula plus your activity level. You can set a custom target.
- **💪 Weight-gain tools**: one-tap calorie boosters, evening "kcal to go" nudges, a gain playbook, and a projected date to reach your goal weight.
- **📈 Progress**: weight trend chart, 7-day calorie chart, days on target, protein average, logging streak.
- Water tracker, favourites, recent foods, custom foods, quick add, past-day editing, dark/light theme, data export/import.
- Installable PWA. Your data stays on your phone.

## Use it on your phone
1. Host it. GitHub Pages is easiest: repo **Settings → Pages → Source: GitHub Actions**. The included workflow deploys on every push. Any static host (Netlify, Cloudflare Pages, Vercel) also works, since there's no build step.
2. Open the URL on your phone:
   - **iPhone (Safari):** Share → *Add to Home Screen*
   - **Android (Chrome):** ⋮ → *Install app*
3. To turn on photo scanning, create an API key at [console.anthropic.com](https://console.anthropic.com/settings/keys) and paste it in **Profile → AI photo scanning**. The key is stored only on your device and is only sent to Anthropic's API.

Run locally: `python3 -m http.server` and open http://localhost:8000.

## Tech
Plain HTML/CSS/JS in `index.html` with no build step. `vendor/anthropic-sdk.js` is `@anthropic-ai/sdk@1.2.0` bundled for the browser. Scans use the `claude-opus-5-5` model with structured JSON output and server-side refusal fallback. `sw.js` provides offline caching.

Nutrition values are estimates, not medical advice.
