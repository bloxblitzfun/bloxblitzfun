<div align="center">

# ⚡ BLOX BLITZ 🟥

### Build. Battle. Own.

**A fast voxel real-time strategy game on Solana.**
Pick a faction, mine Cryo, raise an army, and blitz the enemy HQ in minutes — with cosmetics and a season economy that are truly yours.

<br/>

[![Chain](https://img.shields.io/badge/Chain-Solana-9945FF?style=for-the-badge&logo=solana&logoColor=white)](https://solana.com)
[![Token](https://img.shields.io/badge/Token-%24BLOX-E11D2A?style=for-the-badge)](https://bloxblitz.fun)
[![Launch](https://img.shields.io/badge/Launch-PumpFun%20100%25%20Fair-00C853?style=for-the-badge)](https://pump.fun)
[![Engine](https://img.shields.io/badge/Engine-Three.js-000000?style=for-the-badge&logo=three.js&logoColor=white)](https://threejs.org)
[![Status](https://img.shields.io/badge/Status-Playable%20MVP-2563EB?style=for-the-badge)]()

<br/>

🎮 **[Play](https://bloxblitz.fun)** · 🐦 **[@bloxblitz_](https://x.com/bloxblitz_)** · 💬 **[Telegram](https://t.me/blox_blitz)** · 📝 **[Medium](https://medium.com/@bloxblitz_)**

</div>

---

## What is Blox Blitz

Blox Blitz is a snappy, browser-native voxel RTS where matches last minutes instead of an hour. You gather one resource, command six unit types in a clean rock-paper-scissors meta, and race to crush the enemy HQ through the fog of war. Skill decides every match. The cosmetics you earn are owned, tradeable assets settled in **$BLOX** — never stat boosts.

It is a real game first. The token rides on top of a product that already exists and plays.

**Why it is different:**

- 🧠 **Strategy depth, condensed** — one resource, six units, three factions. Easy to learn, hard to master.
- 🚫 **Zero pay-to-win** — every cosmetic is visual only. A free player has the exact same combat power.
- 💎 **Cosmetics you truly own** — a CS:GO-style economy of trails, auras, emblems and banners you can trade for $BLOX.
- 🌐 **Web-native & instant** — no install, plays in the browser, short matches built for shareable clips.
- 🏆 **A live ladder & market** — season points and a player-priced marketplace drive real demand.
- ✅ **Shipped, not promised** — a working 3D voxel RTS plus a full-stack backend already run today.

---

## Core Mechanics

| System | What it does |
|---|---|
| 💎 **Cryo economy** | Single resource. Workers mine it; build a Depot near far veins to cut travel time. |
| ⚔️ **RPS army** | Rifleman › Rocket › Tank › Rifleman, plus a Cavalry raider and static Turrets. |
| 🛡️ **3 factions** | Vanguard (rush), Bastion (turtle), Syndicate (economy) — distinct stat identities. |
| 🌫️ **Fog of war** | Enemy base spawns at a random position every match; scout to find it. |
| 🗺️ **80×80 voxel map** | 4 elevation tiers, river + bridge chokepoints, A* pathfinding around terrain. |
| 🏅 **Two currencies** | Points (free, earned) unlock most cosmetics; $BLOX powers the tradeable market. |
| 🏆 **Season ladder** | Server-authoritative rewards; leaderboard resets every 14 days. |

---

## The Battle Loop

```
   ┌────────────┐     ┌────────────┐     ┌────────────┐     ┌────────────┐
   │ 1. FACTION │ ──▶ │ 2. GATHER  │ ──▶ │ 3. BUILD   │ ──▶ │ 4. TRAIN   │
   │ HQ+workers │     │ mine Cryo  │     │ barracks / │     │ RPS army + │
   │ + Cryo     │     │ build Depot│     │ turret /HQ │     │ cavalry    │
   └────────────┘     └────────────┘     └────────────┘     └─────┬──────┘
                                                                  │
        ┌─────────────────────────────────────────────────────────┘
        ▼
   ┌────────────┐     ┌────────────┐     ┌──────────────────────────────┐
   │ 5. SCOUT   │ ──▶ │ 6. ATTACK  │ ──▶ │  WIN → season points + $BLOX │
   │ pierce fog │     │ push enemy │     │  → own & trade cosmetics →   │
   │ find base  │     │ HQ to win  │     │  climb the ladder, run it back│
   └────────────┘     └────────────┘     └──────────────────────────────┘
```

---

## Repository Layout

| Path | Contents |
|---|---|
| [`prototype/server/`](../prototype/server) | Node + Express + WebSocket backend — wallet sign-in, cloud profile, leaderboard / season, server-authoritative marketplace. |
| [`prototype/`](../prototype) | Three.js voxel RTS client (no build step) — renderer, A* pathfinding, fog of war, cosmetics, procedural audio. Served statically by the Node process. |
| [`BLUEPRINT.md`](../BLUEPRINT.md) | Full product blueprint — positioning, mechanics, tokenomics, roadmap. |
| [`Readme/`](.) | This documentation. |

> One Node process serves both the Three.js client and the API. No separate frontend server.

---

## Tech Stack

| Layer | Technology |
|---|---|
| **Renderer** | Three.js — isometric ortho camera, InstancedMesh voxel terrain, procedural cube pipeline |
| **Game logic** | A* pathfinding, per-block movement, fog of war, RPS combat, faction modifiers |
| **Backend** | Node.js + Express + native WebSocket (`ws`) |
| **Auth** | Solana wallet sign-in — nonce + `tweetnacl` signature verification |
| **Database** | Cloud Postgres (isolated `bloxblitz` schema, ACID transactions) |
| **Audio** | Procedural WebAudio music + SFX (no asset files) |
| **Chain** | Solana · $BLOX (SPL token, V2) · PumpFun fair launch |

---

## Quick Start

```bash
# 1. Clone
git clone https://github.com/bloxblitzfun/blox-blitz.git
cd blox-blitz/prototype/server

# 2. Configure DB credentials
cp .env.example .env        # fill PGHOST / PGUSER / PGPASSWORD ...

# 3. Install & run (Node 20.6+ for native --env-file)
npm install
node --env-file=.env server.js
```

Open **http://localhost:8787** — connect a wallet (or play as guest), pick a faction, and blitz.

> The server verifies its Postgres connection on boot and exits if it cannot reach the database. Make sure your `.env` points at a reachable Postgres instance before starting.

---

## Token at a Glance — $BLOX

| Property | Value |
|---|---|
| **Ticker** | $BLOX |
| **Chain** | Solana |
| **Total supply** | 1,000,000,000 |
| **Launch** | PumpFun — 100% fair launch |
| **Team allocation** | 0% — no pre-mine, no insider allocation |
| **Distribution** | 100% on the bonding curve |
| **Utility** | Marketplace currency · fee discounts by tier · token-gated season events · governance · buy-back & burn |

**Principle:** $BLOX trades looks, never power. The game is free and fair for everyone; the token layers an owned economy on top.

---

## Roadmap

| Phase | Focus | Highlights |
|---|---|---|
| **1 — Launch-Ready** | Now → 2 weeks | ✅ Voxel RTS loop, RPS units, factions, fog, A* · ✅ cosmetics + cloud profile + leaderboard + market · landing page · $BLOX fair launch |
| **2 — Multiplayer & Economy** | 1–2 months | Real-time PvP 1v1 (server-authoritative) · $BLOX as SPL token · on-chain marketplace · ranked MMR · buy-back & burn live |
| **3 — Depth** | 3–5 months | New units (Chopper, Bomber) · Factory + tech tree · FFA & 2v2 · wagered matches · battle pass · guilds |
| **4 — Ecosystem** | 6–12 months | Map editor + community maps · sponsored tournaments · mobile-friendly client · governance-driven balance |

---

## ⚠️ Scam Warning

Blox Blitz launches **only** through its official channels. Protect yourself:

- The **only** official links are listed at the top of this README (`bloxblitz.fun`, `@bloxblitz_`, `t.me/blox_blitz`).
- There is **no presale, no private allocation, and no airdrop DM.** $BLOX is a 100% fair launch on PumpFun.
- Anyone DMing you a "team contract", "presale spot", or "early access" link is a **scammer**. The team will never DM you first.
- Always verify the contract address (CA) against the pinned post on the official X and Telegram before trading.

> When in doubt, assume anything from a stranger is a scam.

---

## Reference Links

| Resource | Link |
|---|---|
| 🌐 Website | https://bloxblitz.fun |
| 🐦 X / Twitter | https://x.com/bloxblitz_ |
| 💬 Telegram | https://t.me/blox_blitz |
| 🤖 Telegram Bot | [@blox_blitz_bot](https://t.me/blox_blitz_bot) |
| 📝 Medium | https://medium.com/@bloxblitz_ |
| 🚀 Launch | PumpFun (100% fair launch) |

---

<div align="center">
<sub>

**Blox Blitz** — build a blocky base, command a voxel army, win in minutes.
Skill wins the match; the cosmetics you earn are yours to own and trade.

This repository and its documentation are provided for informational purposes only and do not constitute financial advice. $BLOX is a utility token for in-game cosmetics and access, not an investment. Always do your own research.

</sub>
</div>
