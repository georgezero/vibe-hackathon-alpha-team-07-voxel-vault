# Architecture — Voxel Vault Co

## Overview

2D canvas with isometric projection. Voxel grid is a 3D array rendered in painter's order.

## File Structure

```
voxel-vault/
├── index.html          # Entry point — minimal shell, loads src/main.js
├── src/
│   ├── main.js         # All game logic (~300 lines)
│   └── style.css       # Canvas centering and page styles
├── docs/
│   ├── architecture.md # This file
│   ├── prompts.md      # Prompt strategy used during development
│   └── limitations.md  # Known issues and future work
├── sample-data/
│   └── game-states.json # Example game state snapshots for testing
├── vibe.json           # Hackathon submission manifest
├── package.json        # Vite dev server only
├── .env.example        # Environment variable template
├── AGENTS.md           # AI agent instructions
├── LICENSE             # MIT
└── README.md           # Project overview
```

## Game Loop

```
requestAnimationFrame
  └─ update(deltaTime)
       ├─ handleInput()
       ├─ updateEntities()
       ├─ checkCollisions()
       └─ updateScore()
  └─ draw()
       ├─ clearCanvas()
       ├─ drawBackground()
       ├─ drawEntities()
       └─ drawHUD()
```

## State Model

All mutable state is in a single `state` object:

```js
const state = {
  phase: 'start' | 'playing' | 'gameover',
  score: 0,
  highScore: 0,
  player: { x, y, ... },
  entities: [],
  particles: [],
  frame: 0,
}
```

## Rendering

Canvas is 800×500. Coordinate origin is top-left. All drawing is immediate-mode — no retained geometry.

## Input

Keyboard events captured on `window`. State is stored in `keys` object (key → boolean). Processed each frame in `handleInput()`.

## Scoring

Score increments on positive game events. High score persisted to `localStorage`.
