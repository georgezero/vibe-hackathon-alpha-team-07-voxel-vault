# Sample Data — Voxel Vault Co

This directory contains example game states for testing and demonstration.

## game-states.json

Pre-built game state snapshots that can be loaded for testing specific scenarios:

- `fresh_start` — initial game state
- `mid_game` — 60 seconds in, score around 500
- `near_death` — player at minimum health/lives
- `high_score_run` — state that typically leads to high scores

## Usage

```js
// In browser console during development
import states from '../sample-data/game-states.json';
Object.assign(state, states.mid_game);
```

## Notes

All sample data uses synthetic values. No real patient data or personally identifiable information.
