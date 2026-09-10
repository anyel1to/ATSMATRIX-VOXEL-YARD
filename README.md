# ATSMATRIX // VOXEL YARD

[![License: MIT](https://img.shields.io/badge/License-MIT-6ea8ff?style=flat-square)](LICENSE)
[![Stack](https://img.shields.io/badge/Stack-Three.js%20%C2%B7%20WebGL-7d8aa0?style=flat-square)](#repository-layout)
[![Status](https://img.shields.io/badge/Status-Live%20visualizer-6cffb2?style=flat-square)](#project-status)
[![ATSMATRIX](https://img.shields.io/badge/Built%20by-ATSMATRIX-ff4d9d?style=flat-square)](https://atsmatrix.com)

**Minecraft-style 3D operations chunk for live desk metrics.**

Towers are numbers. Agents walk the stone cross. The beacon is the lock. This is a functional WebGL visualizer, not a screenshot of a dashboard.

Live floor (after Pages is enabled):

https://anyel1to.github.io/ATSMATRIX-VOXEL-YARD/

---

## Contents

1. [Purpose](#purpose)
2. [World map](#world-map)
3. [Controls](#controls)
4. [Repository layout](#repository-layout)
5. [Run locally](#run-locally)
6. [GitHub Pages](#github-pages)
7. [Project status](#project-status)
8. [Related surfaces](#related-surfaces)
9. [License](#license)

---

## Purpose

Flat panels hide scale. Voxel Yard puts the same desk state into a chunk you can orbit:

| Block | Meaning |
| --- | --- |
| Grass / river / trees | The floor. Terrain only. |
| Stone cross | Patrol path. |
| Obsidian plaza + gold / diamond core | Beacon lock. |
| Colored towers | Live metrics. Height = value. |
| Moving wool cubes | Named agents on patrol. |

The yard currently drives a high-fidelity **simulated clock** (NAV, P&L, edge, tower growth). It is the visual contract. It is not wired to a production market feed in this repository.

Full mapping: [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md)

---

## World map

```
              SIG (iron)
                 |
   NAV -------- CORE -------- LIQ
  (cyan)      gold/diamond   (gold)
                 |
   RISK -------------------- WR
 (redstone)              (emerald)
                 |
              EDGE (diamond)
```

Agents on the cross: **NYX · VEX · RIO · KAI · ORA · ZEN**

| Key | Tower | Role |
| --- | --- | --- |
| 1 | NAV | Net asset value |
| 2 | LIQ | Book liquidity |
| 3 | WR | Win rate |
| 4 | EDGE | Confirmed edge |
| 5 | RISK | Drawdown / heat |
| 6 | SIG | Signal count |

---

## Controls

| Input | Action |
| --- | --- |
| Drag | Orbit camera |
| Scroll | Zoom |
| `1`–`6` | Jump target to that tower |
| `SPACE` | Pause / resume simulation clock |

F3-style debug (xyz, NAV, P&L, edge, FPS) stays pinned top-left. Hotbar is a block legend, not an inventory.

---

## Repository layout

```
ATSMATRIX-VOXEL-YARD/
|-- index.html              WebGL yard (Three.js via CDN import map)
|-- docs/ARCHITECTURE.md    Block map and sim clock
|-- LICENSE                 MIT
|-- SECURITY.md
|-- CONTRIBUTING.md
|-- README.md
```

No package manager. No bundler. No API key required to fly the chunk.

Runtime dependency: Three.js r167 loaded from jsDelivr (`three` + `OrbitControls`). Offline use requires vendoring those two modules.

---

## Run locally

```bash
git clone https://github.com/anyel1to/ATSMATRIX-VOXEL-YARD.git
cd ATSMATRIX-VOXEL-YARD
python3 -m http.server 4173
```

Open [http://localhost:4173](http://localhost:4173).

A local server is required. Opening `index.html` as a `file://` URL will block the ES module import map.

---

## GitHub Pages

1. Repository **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: **main**, folder: **/(root)**
4. Save

Public URL after the first deploy:

https://anyel1to.github.io/ATSMATRIX-VOXEL-YARD/

---

## Project status

| Item | State |
| --- | --- |
| Public repository | Active |
| WebGL yard | Shipped (simulated telemetry) |
| Orbit / pause / tower jump | Shipped |
| Production market feed | Not in this repository |
| Live packet adapter | Planned |

Next professional layer is a real tick adapter: accept NAV / LIQ / WR / EDGE / RISK / SIG from the desk bus and set tower height from those values. The chunk should not gain ornament until that adapter exists.

---

## Related surfaces

- [ATSMATRIX-AGENT-RING](https://github.com/anyel1to/ATSMATRIX-AGENT-RING)
- [ATSMATRIX-AGENT-COMPOUND](https://github.com/anyel1to/ATSMATRIX-AGENT-COMPOUND)
- [ATSMATRIX-NEXUS](https://github.com/anyel1to/ATSMATRIX-NEXUS)
- [MATRIX-FILES](https://github.com/anyel1to/MATRIX-FILES)

Site: [atsmatrix.com](https://atsmatrix.com)

---

## License

MIT License © 2026 ATSMATRIX Technologies

Built by **ANYELO · ATSMATRIX**
