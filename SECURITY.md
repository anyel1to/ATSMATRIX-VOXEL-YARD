# Security Policy

## Supported versions

The `main` branch is the only supported line.

## Reporting a vulnerability

Do not open a public issue for a vulnerability.

Email: contact listed on [atsmatrix.com](https://atsmatrix.com)

Include:

- affected file and line if known
- steps to reproduce
- impact (XSS, supply-chain CDN, etc.)

This visualizer loads Three.js from jsDelivr. Treat that CDN as an external trust boundary. For locked-down deployments, vendor `three.module.js` and `OrbitControls.js` into this repository and point the import map at those files.

No API keys are stored in this repository. Do not add keys to `index.html`.
