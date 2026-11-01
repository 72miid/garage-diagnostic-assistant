# Garage Diagnostic Assistant — Build 13

Static, mobile-first diagnostic guidance prototype for iPhone Safari / GitHub Pages.

## Build 13 changes
- Separates three fuel-trim patterns: similar notable correction on both banks (possible shared cause), a materially larger correction on one bank (possible bank-specific cause), and low corrections on both banks (no notable trim correction in that sample).
- Calculates combined STFT/LTFT correction multiplicatively for each bank: `((1 + STFT/100) × (1 + LTFT/100) − 1) × 100`.
- Adds required context fields: fully warmed engine, scanner fuel-system status (closed/open loop), and whether both banks were captured at the same RPM/load.
- Defers conclusions when warm-up, closed-loop status, or matching measurement conditions are not confirmed.
- Flags implausible entered trim values outside a broad −100% to +100% plausibility screen.
- Preserves the added context in reports, saved cases, and exported history.
- Bumps the service-worker cache to v13 to reduce stale-page issues.

## Deploy
1. Extract this ZIP.
2. Replace `index.html`, `manifest.json`, `sw.js`, and `README.md` in the repository with these files.
3. Add/replace `DIAGNOSTIC-ACCEPTANCE-TESTS.md`.
4. Commit changes and wait for GitHub Pages deployment.
5. Open `https://72miid.github.io/garage-diagnostic-assistant/?v=13` and verify the header and footer show BUILD 13.

## Important limitations
- No live OBD-II connection, automatic PID validation, code clearing, or manufacturer database.
- Values are manually entered. The app cannot verify whether the scanner PID is correct or whether data were captured under matching conditions.
- Thresholds are preliminary screening bands, not Dodge factory specifications. A trim pattern cannot prove a failed part.
- Do not perform high-speed road tests or unsafe engine-running checks. Follow the vehicle-specific service procedure.
