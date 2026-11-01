# Garage Diagnostic Assistant — Build 15

A mobile-first static diagnostic-guidance PWA for workshop use.

## Build 15 scope
- Reworked symptom intake and adaptive question paths.
- Safety-priority branches for overheating danger and oil-pressure warnings/codes.
- Evidence-led test sequences for P0171/P0174, P0300–P0308, P0128 and P0101.
- Unsupported codes are explicitly marked for OEM lookup instead of inventing repair procedures.
- Case saving to browser localStorage and printable report.
- Updated service-worker cache namespace.

## Important limitations
- No live OBD-II connection, VIN decoding, automatic PID capture, AI inference, OEM database, wiring diagrams or manufacturer specifications.
- Guidance is preliminary. Verify procedures, thresholds, connectors and specifications against the exact vehicle service information.
- Do not replace a part based only on a DTC or symptom. Confirm the component fault with a test.
- Saved cases remain in the current browser/device only.

## Deploy
Upload `index.html`, `sw.js`, `manifest.json`, `README.md` and `DIAGNOSTIC-ACCEPTANCE-TESTS.md` to the repository root. Wait for GitHub Pages deployment, then hard-refresh / clear the old PWA cache if required.
