# Voxel Vault Co — Voxel Vault

> Place and remove voxels to reconstruct 3D medical scans from memory. Inspired by DICOM 3D reconstruction. Score is based on volumetric accuracy vs. reference structure.

**Demo:** [https://georgezero.github.io/vibe-hackathon-alpha-team-07-voxel-vault](https://georgezero.github.io/vibe-hackathon-alpha-team-07-voxel-vault)
**Hackathon:** Vibe Hackathon 2025 · Team 07
**License:** MIT

## Team

- **Cameron Thomas** — 3D + Graphics
- **Drew Jackson** — AI Integration

## Installation

```bash
npm install
```

## Run

```bash
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

Or open `index.html` directly — no build step required for the base game.

## Build for Production

```bash
npm run build
```

Output goes to `dist/`.

## How to Play

Click cells to toggle voxels — match the target structure for maximum score.

## Architecture

See [docs/architecture.md](docs/architecture.md) for full design notes.

## Agent Development Notes

See [AGENTS.md](AGENTS.md) for instructions on working with this repo using AI coding agents.

See [docs/prompts.md](docs/prompts.md) for the key prompts used during development.

## Known Limitations

Isometric projection only. Full 3D rotation not yet implemented.

## Sample Data

See [sample-data/](sample-data/) for example game states and test fixtures.
