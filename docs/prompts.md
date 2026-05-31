# Prompt Strategy — Voxel Vault Co

Key prompts and prompt patterns used during development with Claude Code.

## Bootstrap prompt

```
I'm building a browser-based HTML5 canvas game called "Voxel Vault".
Place and remove voxels to reconstruct 3D medical scans from memory. Inspired by DICOM 3D reconstruction. Score is based on volumetric accuracy vs. reference structure.

Stack: vanilla JS, HTML5 Canvas, Vite. No frameworks.

Start with:
1. A game loop using requestAnimationFrame
2. A state object containing all mutable game state
3. Input handling for keyboard events
4. A basic scoring system

Make it playable in under 200 lines.
```

## Iteration prompts

### Game feel
```
The game loop is working. Now improve the game feel:
- Add particle effects when the player scores
- Smooth movement interpolation
- Screen shake on collision
Keep under 50 additional lines.
```

### Difficulty curve
```
Add a difficulty progression system. Every 30 seconds,
increase spawn rate by 15% and speed by 10%.
Cap at 3x the starting values.
```

### Polish
```
Add a start screen and game over screen.
Start screen: show title, high score, "Press SPACE to start"
Game over: show final score, high score if beaten, "Press R to restart"
Do not use any HTML elements — draw everything on canvas.
```

## What worked

- Giving Claude the full game state object upfront made iteration much faster
- Asking for "under N lines" kept code compact and reviewable
- Describing the desired player feeling ("snappy", "satisfying") worked better than describing mechanics

## What didn't work

- Asking for "best practices" produced over-engineered code
- Requesting "add tests" before game was playable was premature
- Generic "refactor this" prompts needed more specific constraints
