# AGENTS.md — Voxel Vault Co

AI coding agent runbook. Everything an agent needs to understand, run, modify, and extend this project.

## Overview

Place and remove voxels to reconstruct 3D medical scans from memory. Inspired by DICOM 3D reconstruction. Score is based on volumetric accuracy vs. reference structure.

Tech stack: HTML5 Canvas, Vanilla JS (ES modules), Vite.

## Install

```bash
npm install
```

No external runtime dependencies. Vite is dev-only.

## Run

```bash
npm run dev
```

App runs at http://localhost:5173. Hot reload via Vite HMR.

## Build

```bash
npm run build
# Output: dist/
```

## Test

No automated tests currently. Open the app and play through one complete game cycle to verify.

Manual checklist:
- Game starts on page load
- Score increments correctly
- Game over state triggers
- Restart works without page reload

## Architecture

See [docs/architecture.md](docs/architecture.md) for full design.

Key files:
- `index.html` — entry point, loads `src/main.js`
- `src/main.js` — all game logic
- `src/style.css` — global styles

## Common Tasks

### Add a new enemy type
1. Define enemy properties in `src/main.js` under `ENEMY_TYPES`
2. Add spawn logic in `spawnWave()`
3. Add rendering in `drawEnemies()`

### Change difficulty
Modify `GAME_CONFIG` constants at the top of `src/main.js`.

### Add a new level
Extend the `LEVELS` array in `src/main.js`.

## Debugging

- Open browser DevTools → Console for error logs
- Game state is logged to console on each frame in debug mode
- Set `DEBUG = true` at the top of `src/main.js` to enable verbose logging

## Key Invariants

- All game state lives in the `state` object — never use module-level mutable variables outside of it
- `requestAnimationFrame` is the only timer — do not use `setTimeout` for game loop
- Canvas is always cleared before each frame draw

## Known Limitations

Isometric projection only. Full 3D rotation not yet implemented.
