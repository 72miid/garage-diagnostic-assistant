# Garage Diagnostic Assistant — Build 15.1

Mobile-first static diagnostic-guidance PWA for workshop use.

## Build 15.1
- Restores Easy Mode and Workshop / Pro Mode.
- Restores manual ECT, RPM, STFT and LTFT entry for both banks.
- Calculates combined fuel correction using multiplicative STFT/LTFT combination.
- Defers fuel-trim conclusions unless warm-up, closed-loop and matching bank conditions are confirmed.
- Adds adaptive symptom questions and ordered inspection guidance.
- Adds safety-priority handling for overheating, oil-pressure codes P0520–P0524, visible fuel leaks and visible smoke with electrical-burning smell.
- Includes guided paths for P0171/P0174, P0300–P0308, P0128 and P0101; unsupported codes are explicitly referred to OEM service information.
- Saves cases locally, reopens saved summaries, exports JSON and prints reports.
- Uses a new service-worker cache namespace.

## Deploy
Upload and replace `index.html`, `sw.js`, `manifest.json`, `README.md`, and `DIAGNOSTIC-ACCEPTANCE-TESTS.md` in the repository root. Wait for GitHub Pages deployment, then open the site in Safari and refresh. If an old installed PWA remains, close it fully and reopen the site.

## Limitations
No live OBD-II connection, automatic PID capture, VIN decoding, ECU communication, code clearing, OEM database, wiring diagrams or manufacturer-specific specifications. All readings are manually entered and cannot be verified by the app. Fuel-trim bands are preliminary screening guidance, not factory limits. Verify procedures, connectors, thresholds and specifications against service information for the exact vehicle. Never replace a component based only on a DTC.

## Verification
Static source checks and JavaScript syntax checks only. Browser interaction, GitHub Pages deployment, Safari PWA behavior, scanner validation and real-vehicle tests remain to be performed.
