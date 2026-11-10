# Photon Sphere

A real-time ray-traced black hole that runs in the browser (WebGL 2, no libraries).

Every pixel traces a light ray backwards through Schwarzschild spacetime. The ray bends around the black hole until it hits the accretion disk, falls past the event horizon, or escapes to the star field. The lensed arc over the top, the thin photon ring and the lopsided brightness all come from that math rather than being painted on.

## Run it

Open `index.html` in a browser. Nothing to install.

## Controls

- Drag to orbit, scroll or pinch to zoom
- View presets: tilted, edge-on, face-on, close-up
- Toggle light bending, Doppler beaming and gravitational redshift one at a time
- Disk temperature, orbital time scale, exposure
- `H` hides the panel

## Physics notes

- Units: Schwarzschild radius r_s = 1. Null geodesics are integrated with the conserved-angular-momentum form `a = -1.5 h² x / r⁵` (leapfrog, adaptive step).
- Disk: thin, from the ISCO (3 r_s) outward, temperature profile ~ r^(-3/4)(1 - sqrt(r_in/r))^(1/4).
- Observed light is scaled by g⁴ and color-shifted by g, where g combines the Doppler factor of the orbiting gas and gravitational redshift.
- HDR render with mip-chain bloom and ACES tone mapping; resolution adapts to keep the frame rate up.
