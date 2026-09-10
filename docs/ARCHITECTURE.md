# Voxel Yard — architecture

## Clock

The yard uses a client-side simulation clock `t` in seconds.

```
k = 1 - (1 - min(1, t / 12))^3
NAV  = 2140 + (16440 - 2140) * k
EDGE = 2.1 + 9.7 * k
tower live height = 2 + floor((maxH - 2) * k)
```

Agents follow a parametric loop on the stone cross. Even index: X corridor. Odd index: Z corridor.

This clock is the contract. A production adapter should replace `k` with normalized values from the desk bus and leave the mesh graph alone.

## Scene graph

- Shared `BoxGeometry(1,1,1)`
- One `MeshLambertMaterial` per block kind
- Directional sun + hemisphere + ambient
- `OrbitControls` with damping

## Trust boundary

Three.js is loaded from jsDelivr at r167. Pages and local server both require network for first load unless the modules are vendored.

## Non-goals

- Not a Minecraft server, launcher, or asset dump.
- Not official Mojang / Microsoft software.
- Not a live brokerage terminal.
