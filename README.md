# Garage Diagnostic Assistant — Build 14

Mobile-first static diagnostic-guidance PWA for iPhone Safari / GitHub Pages.

## Build 14 changes
- Narrows the misfire rule to the supported cylinder-misfire family P0300–P0308. Other P03xx codes no longer get automatically labelled as misfires.
- Reports explicitly when no fuel-trim values are supplied, when a bank has an incomplete STFT/LTFT pair, or when only one bank has a complete pair.
- Makes the report's manual-data limitation explicit: the app cannot verify vehicle provenance, PID selection, units, or measurement conditions. Example/test numbers are not actual vehicle measurements.
- Updates the service-worker cache namespace to v14.
- Retains Build 13's warm-engine, closed-loop, matching-RPM/load context gates and multiplicative combined-trim estimate.

## Deploy to GitHub Pages
1. Extract the ZIP.
2. Replace `index.html`, `manifest.json`, `sw.js`, `README.md`, and `DIAGNOSTIC-ACCEPTANCE-TESTS.md` in the repository.
3. Commit and push the changes.
4. Wait for the Pages deployment to complete.
5. Open `https://72miid.github.io/garage-diagnostic-assistant/?v=14` and confirm BUILD 14 appears in the header and footer.
6. If an old version remains, close the installed PWA, reopen the URL in Safari, and refresh after the deployment completes. The cache namespace changed to v14.

## Limitations
- No live OBD-II connection, automatic PID validation, ECU communication, code clearing, or manufacturer database.
- All sensor values are manually entered and cannot be verified by the app.
- Fuel-trim thresholds are preliminary screening guidance, not Dodge factory specifications or pass/fail limits.
- A code or trim pattern cannot prove a component has failed. Confirm with vehicle-specific service information and tests.
- No unsafe road tests or work around hot/moving engine components. Stop if the vehicle may be unsafe.

## Verification performed for this package
- JavaScript syntax check with Node.js (`node --check`).
- Static checks for Build 14 labels, cache version, narrowed misfire matcher, and explicit incomplete/no-trim branches.
- This is not a claim of live Safari, GitHub Pages, or real-vehicle validation.
