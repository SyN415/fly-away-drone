# Fly Away Drone

An open-sky drone time trial you can play in the browser. No install, no build step.

Race a quadcopter through glowing checkpoints across a coastal sky — towers, turbines, drifting balloons, bird flocks, and wind shear included. Three rounds. Start pad. Finish gate. Stars if you beat par clean.

## Play

**Live:** https://syn415.github.io/fly-away-drone/

**Local:** open `index.html` in Chrome, Firefox, or Edge. The page loads Three.js from a CDN.

If your browser blocks `file://`, run a tiny server from this folder:

```bash
python3 -m http.server 8080
```

Then visit `http://localhost:8080`.

## Controls

| Input | Action |
|---|---|
| W / ↑ | Thrust forward |
| S / ↓ | Thrust back |
| A / D or ← / → | Yaw |
| E / Space | Climb |
| Q / Ctrl / Z | Descend |
| Shift | Boost (drains battery fast) |
| C | Cycle camera (chase / FPV / orbit) |
| R | Respawn at last checkpoint (costs a life mid-round) |
| P / Esc | Pause |
| F | Fullscreen |
| M | Mute |
| Enter / click | Confirm menus |

## Rules

- Fly the **START** pad, then hit every **checkpoint ring in order**, then the **FINISH** gate.
- Three rounds: Harbor Lesson → Island Chain → Storm Corridor.
- 3 lives per round. A hard hit (fast impact, turbine blade, or water) costs a life and respawns you at the last checkpoint.
- Soft scrapes bounce you and cut score, but do not cost a life.
- Battery drains with thrust and boost. At 0% you can only descend.
- Beat the par time for 2 stars. Beat par with zero hits for 3 stars.
- Best times and total score save to `localStorage` (`flyaway_drone_v1`).

## Rounds

| Round | Course | Limit | Par | Flavor |
|---|---|---|---|---|
| 1 | Harbor Lesson | 90s | 52s | Wide rings, two radio towers, light wind |
| 2 | Island Chain | 105s | 68s | Turbines, balloons, wind shear |
| 3 | Storm Corridor | 120s | 82s | Tight rings, flocks, debris, turbine gauntlet |

## Stack

Single-file vanilla JavaScript + Three.js. Designed to run from `file://` or GitHub Pages.

See `DESIGN.md` for the full game design document (world, physics, scoring, obstacle spec, and v2 backlog).
