# Gargantua

An interactive black hole simulation inspired by *Interstellar* — built as a single, self-contained HTML file. No installation, no server, no dependencies. Just open it in a browser.

![Gargantua simulation](screenshot.png)

---

## What it is

A real-time WebGL simulation of Gargantua, the supermassive black hole from *Interstellar*. The physics, the numbers, and the story told inside the event horizon are as accurate as a real-time renderer allows.

**What you can do:**
- Orbit the black hole freely and explore it from any angle
- Hover over regions to learn the physics behind what you're seeing
- Launch the approach sequence and fall toward the event horizon
- Cross the horizon and experience a 6-panel story sequence told from inside
- Enter Dreaming mode — a purple-pink nebula with shooting stars and ambient audio

---

## Features

**Rendering**
- Gravitational lensing shader — light bends around the shadow in real time
- Relativistic Doppler beaming — the approaching side of the disk is brighter and bluer
- UnrealBloom post-processing for the photon ring and accretion disk glow
- Einstein aberration pass — the outside universe collapses to a shrinking ring as you fall in
- Back-of-disk lensing arc — secondary image visible when viewing from above or below

**Approach sequence**
- Spiral flight path from orbit to the event horizon (~111 seconds at 1×)
- Live HUD: proper time, coordinate time, time dilation factor, distance to horizon, Earth elapsed time
- Milestone panels at photon sphere, ISCO, Doppler zone, and lensing region
- Playback controls: pause, rewind, ½× slow, 4× fast-forward
- Elapsed timer

**Inside the horizon**
- Six story panels, each grounded in real general relativity
- Relativistic aberration animation — the ring of the outside universe shrinks toward a point
- Singularity flash sequence
- Soft ambient drone swells as you cross

**Dreaming mode**
- Three independently rotating nebula layers (outer haze, main body, inner glow) with additive blending
- Three-tier star field with Hertzsprung-Russell colour distribution and galactic band concentration
- Shooting stars every 4–9 seconds
- Inner nebula pulse animation
- Pink noise ambient audio

**Audio**
- Gravitational redshift modulation — the drone pitch drops as you approach
- Volume surges near the horizon
- Soft two-tone blip on each inside panel
- Music swells when you cross

---

## How to run

```
git clone https://github.com/itsarmi/gargantua.git
open gargantua.html
```

Or just download `gargantua.html` and open it. That's it.

Works in any modern browser (Chrome, Firefox, Safari, Edge). Requires an internet connection on first load to fetch Three.js from the CDN — after that it can run offline if cached.

---

## Stack

- [Three.js r0.165.0](https://threejs.org/) — 3D rendering
- `EffectComposer` → `UnrealBloomPass` → custom lensing `ShaderPass` → custom aberration `ShaderPass`
- Web Audio API — procedural drone, noise, and UI sounds
- Pure vanilla JS, no build step

---

## Physics accuracy

| Feature | Source |
|---|---|
| Gravitational lensing | Schwarzschild ray deflection approximation |
| Time dilation display | Schwarzschild metric `dt = dτ / √(1 − rₛ/r)` |
| Doppler beaming | Relativistic boost factor `(1 + β·cos θ)⁴` |
| Accretion disk inner edge | ISCO at 3× Schwarzschild radius |
| Einstein aberration ring | Relativistic aberration formula |
| Horizon crossing | Equivalence principle — no local observable crossing event |

The story panels inside the horizon are written to be scientifically honest, including what general relativity actually cannot tell you once you're inside.

---

## Credits

Created by **Armi** — Friday 08. of May 2026

Built with Claude (Anthropic).
