<p align="center">
  <img src="https://img.shields.io/badge/vanilla-JS-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="Vanilla JS"/>
  <img src="https://img.shields.io/badge/single-file-0f111a?style=for-the-badge" alt="Single File"/>
  <img src="https://img.shields.io/badge/no%20build-required-5b6aaf?style=for-the-badge" alt="No Build"/>
  <img src="https://img.shields.io/badge/lo--fi-vibes-a05bd2?style=for-the-badge" alt="Lo-Fi Vibes"/>
</p>

<h1 align="center">
  <br>
  Midnight Factory
  <br>
  <sub><sup>a factory game for the quiet hours</sup></sub>
</h1>

<p align="center">
  <em>Mine. Smelt. Assemble. Transcend.</em>
  <br>
  <em>A relaxing factory automation game with a dark glassmorphic aesthetic and procedural lo-fi soundtrack.</em>
</p>

---

## How to Play

```
Double-click midnight-factory.html
```

That's it. No server. No install. No dependencies. Just open and play.

---

## What is Midnight Factory?

A chill, browser-based factory game built entirely in a **single HTML file**. Place miners on ore deposits, connect them with conveyor belts, smelt raw materials into ingots, assemble complex components, and sell your products to grow your industrial empire — all while procedural lo-fi beats play in the background.

**Design pillars:** relaxing atmosphere, smooth item flow, clean dark UI, zero information overload.

### The Production Chain

```
                           Ore Deposits
          ┌────────────────────────────────────────┐
          │  iron  copper  coal  stone              │
          │  gold  crystal  silicon       (tier 3)  │
          │  titanium  nebula dust        (tier 5)  │
          └──────────────┬─────────────────────────┘
                         v
                    [ Furnace ]
                bars, ingots, wafers, refined coal
                         |
                         v
                   [ Assembler ]
          steel, wire, alloy, circuits, composite
                         |
                         v
             nano_chip — processor — energy_cell
                         |
                         v
                   [ Quantum Core ]
                         |
            titan_alloy + quantum_core → quantum_lattice
            nebula_crystal + energy_cell → plasma_coil
                         |
                         v
                   [ Synthesizer ]
          quantum_lattice + plasma_coil → singularity_shard
```

From humble iron ore to reality-bending Singularity Shards — the journey is yours to build.

---

## Features

- **Single-file architecture** — ~4900 lines of vanilla JS, HTML, and CSS in one file
- **Web Worker simulation** — game logic runs on a separate thread for smooth 60fps rendering
- **Procedural lo-fi music** — 6 unique tracks generated from oscillators, reverb, and tape wobble
- **Procedural SFX** — every sound effect is synthesized in real-time
- **Dark glassmorphic UI** — frosted glass panels, subtle glows, ambient dust motes
- **Day/night cycle** — gentle color temperature shifts over an 8-minute cycle
- **30 resources** — from raw ores to quantum cores and singularity shards
- **15 building types** — mines, belts (3 tiers), furnaces, assemblers, splitters, mergers, tunnels, labs, sellers, vein miners, ore synthesizers, and synthesizers
- **33 skill nodes** — 7 tiers of research unlocking new buildings, speed boosts, and trade bonuses, plus hidden prestige milestones
- **22 recipes** — 8 furnace, 13 assembler, and 1 synthesizer recipe covering the full production chain
- **Blueprint system** — copy, paste, and rotate sections of your factory
- **Undo system** — Ctrl+Z to revert placements and deletions
- **Milestones & prestige** — achievement-like goals from $500 to Transcendent Magnate, with secret bonuses for quantum core and singularity shard production
- **Adaptive quality** — automatically adjusts rendering detail to maintain smooth performance
- **Accessibility** — respects `prefers-reduced-motion` for users who need it
- **Auto-save** — progress is saved to localStorage every 5 seconds
- **Seeded world generation** — share your seed, share your world
- **Zero dependencies** — no frameworks, no bundlers, no build steps, no node_modules

---

## Controls

| Key | Action |
|-----|--------|
| `1` — `9`, `0`, `=` | Select building from build bar |
| `R` | Rotate building or blueprint |
| `X` | Delete tool |
| `C` | Blueprint: copy / paste mode |
| `Z` / `U` / `Ctrl+Z` | Undo |
| `H` | Home camera to spawn |
| `T` | Skill tree |
| `B` | Recipe book |
| `M` | Minimap |
| `S` | Stats panel |
| `?` | Keyboard shortcuts |
| `Esc` | Close all overlays |
| Scroll | Zoom in/out |
| Click + Drag | Pan camera |
| Right-click | Building info / belt upgrade |

---

## Architecture

Everything lives in a single HTML file with a two-thread architecture:

```
Main Thread                           Web Worker
───────────────────────────────────   ───────────────────────────────────
Renderer  — canvas 2D drawing         Simulation — all game logic
UI        — DOM panels, menus         State      — map, buildings, items
Game      — input + message bridge    Tick loop  — self-scheduling
SoundEngine — procedural SFX
LoFiGen   — procedural music
Config    — shared via JSON
```

The worker owns all authoritative state. The main thread holds a replica for rendering only. They communicate exclusively through `postMessage`, with items transferred as zero-copy `ArrayBuffer`s for maximum performance.

---

## Tech Stack

| What | How |
|------|-----|
| Language | Vanilla JavaScript (ES2020) |
| Rendering | Canvas 2D API |
| Threading | Web Worker (classic, blob URL) |
| Audio | Web Audio API (procedural synthesis) |
| Storage | localStorage |
| Fonts | Fira Code + Quicksand (Google Fonts) |
| Build system | None |
| Dependencies | None |

---

## License

This project is open source. Feel free to explore, learn from, and build upon it.

---

<p align="center">
  <sub>built with late-night coffee and quiet determination</sub>
</p>
