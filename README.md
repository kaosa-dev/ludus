<h1 align="center">Ludus</h1>

<p align="center">
  <b>Online gladiator management and arena game.</b><br>
  Run a gladiator school, manage your roster, send fighters into the arena against real opponents.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/status-in%20development-EEFF00?style=flat-square&labelColor=0d1117" alt="In development">
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/Phaser%203-8E44AD?style=flat-square&logo=phaser&logoColor=white" alt="Phaser 3">
  <img src="https://img.shields.io/badge/Colyseus-2D3748?style=flat-square&logo=colyseus&logoColor=white" alt="Colyseus">
</p>

---

## The rule the whole game is built on

**The client never decides an outcome.** Every fight, every payout, every balance change is resolved
on the server. The browser receives the result and plays it back.

That rule shapes the codebase:

```
packages/
  core/     pure TypeScript — combat, economy, RNG, balance. No engine, no Node, no DB.
  server/   Node + Express + Prisma — the authority. Imports core.
  client/   Phaser 3 + Vite — presentation only. Animates the state the server sends.
```

Because `core` has no dependencies on rendering or I/O, the same combat code runs on the server
for real and in unit tests — and there's exactly one implementation to keep honest.

## Multiplayer

- **Real-time PvP matchmaking** over Colyseus
- **NPC fallback** — if no opponent is found within 9 seconds, the match resolves against an NPC,
  so nobody waits in an empty queue

## Stack

`TypeScript` `Phaser 3` `Vite` `Node` `Express` `Prisma` `Colyseus` `Vitest` `Docker`

## Follow

- Developer — [@ilterisgunay](https://x.com/ilterisgunay)
- Ideas or questions — [open an issue](../../issues/new)

<sub>This repository is the public home for news and feedback. Game source is private.</sub>
