# AI Spire (AI-SPIRE)

A browser-based roguelike deckbuilder inspired by *Slay the Spire*, where **Gemini generates new game content while you play**:

- **Card rewards** after battles (3 new cards per win)
- **Shop inventory** (cards + relics) when entering a Shop node
- **Elite/Boss relic drops** on Elite or Boss fights
- A **“Wish”** input in the reward screen that turns a free-form player prompt into a **single custom card**

The game runs entirely in the browser. If you don’t provide an API key, it falls back to built-in mock content so the game is still playable.
## How It Works (Neural + Symbolic)

- **Neural component (Gemini)** acts as a constrained “designer”: it returns **JSON** shaped by a schema (card name/type/rarity/cost/stats + `specialEffect` tokens; relic `effectType` tokens).
- **Symbolic component (TypeScript rules engine)** deterministically executes effects by parsing those tokens and updating player/enemy state (HP, block, statuses, deck/hand/discard/exhaust, relic triggers).
- **Safety/robustness** comes from schema shaping + sanitization/clamping + an allowlist of effect tokens; invalid outputs are dropped and the system falls back to mock content.

Key files:
- `App.tsx` — core game loop + combat engine + UI state machine
- `services/geminiService.ts` — Gemini prompting, JSON-schema outputs, sanitization, and mock fallbacks
- `types.ts` / `constants.ts` — shared contracts and starting/balance values
- `components/Card.tsx` — card rendering

## Gameplay Summary

- Map progression with nodes: **Monster**, **Elite**, **Shop**, **Rest**, and **Boss** (every 10 floors).
- Turn-based combat with **energy**, card piles, and keywords (**Exhaust**, **Ethereal**, **Innate**, **Retain**, **multi-hit**).
- Status effects as counters (examples): poison, burn, freeze, weak, vulnerable, frail, strength, dexterity, reflect, metallicize, regen.
- Relics trigger on events like `start_combat`, `turn_start`, `play_attack`, `end_combat`.

## Run Locally

**Prerequisites:** Node.js (18+ recommended)

1. Install dependencies: `npm install`
2. Create `.env.local` and set your Gemini key:
   - `GEMINI_API_KEY=...`
3. Start the dev server: `npm run dev`

Open `http://localhost:3000`

## Environment Variables / Security Note

- `GEMINI_API_KEY`: used client-side to call Gemini.

Because this project calls Gemini **directly from the browser**, any API key you include is visible to users. For a public deployment, use a server-side proxy or another key-management approach instead of shipping your key.

## Scripts

- `npm run dev` — start Vite dev server
- `npm run build` — production build to `dist/`
- `npm run preview` — preview the production build locally

## Repo Note

This repo also contains a nested `AI-SPIRE/` directory with a similar copy of the same app. The root project is runnable as-is; use one copy consistently.

## Disclaimer

Fan-inspired prototype; not affiliated with “Slay the Spire”.
