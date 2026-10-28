# Garage Diagnostic Assistant — Build 11

## Included
- `index.html` — responsive PWA interface and deterministic diagnostic rules.
- `manifest.json` — installable app metadata.
- `sw.js` — versioned service worker with network-first app-document loading and old-cache cleanup.
- `DIAGNOSTIC-ACCEPTANCE-TESTS.md` — manual acceptance tests for primary symptom and safety paths.

## Important fixes in build 9
- Low-power answer matching now normalizes wording rather than relying on one exact phrase; the previous shaking rule did not match the actual radio option text.
- Removed a duplicate low-power flashing-light rule.
- Fixed a shared-array mutation in the question builder that could accumulate extra questions each time a symptom was diagnosed again.
- “New diagnosis” now resets form inputs and diagnostic state.
- “Edit answers” resumes the saved diagnostic questions instead of restarting and losing those answers.
- Manually entered workshop live-data values appear in the report, clearly marked as reference-only because this prototype provides cautious rule-based preliminary interpretation, with explicit limits and context checks.
- Added DTC descriptions for P0305–P0308, useful for an eight-cylinder engine.
- Added BUILD 9 label so a stale app can be distinguished from the deployed build.
- Bumped the service-worker cache version.

## Publish
Replace the repository-root `index.html`, `manifest.json`, `sw.js`, and `README.md` with the matching files in this package. Add `DIAGNOSTIC-ACCEPTANCE-TESTS.md`. Commit the changes and wait for GitHub Pages to deploy. The GitHub integration currently rejects write operations, so this package is ready for manual upload.

## Limits
This is a rules-based prototype, not a confirmed diagnostic system. It has no live OBD-II connection, does not clear codes, and cannot automatically interpret manually entered live data. Use manufacturer-specific service information and safe test procedures. Never open a hot pressurized cooling system. Stop safely for severe overheating, oil-pressure warnings, fuel leaks, smoke, or other immediate danger.


## Build 11 — case history review
- Case-history entries can be expanded to show stored diagnostic answers, initial timing, scanner status, codes, and manually entered live-data values.
- Dates are formatted for the device's local timezone instead of displaying raw UTC timestamps.
- Older saved cases remain readable; fields that were not stored are identified as unavailable.
- This remains a rules-based prototype. History stores vehicle data and answers, not a reconstructed full diagnostic report.


## Build 11 — preliminary live-data interpretation
- Added rule-based interpretation for manually entered coolant temperature, RPM, STFT Bank 1 and LTFT Bank 1.
- Flags extreme/strongly shifted entries for verification, describes modest readings cautiously, and calculates a simple STFT + LTFT reference for Bank 1 when both values are entered.
- Every interpretation states relevant limits: values must be verified, engine state/closed-loop status and vehicle specifications matter, and no reading alone confirms a failed part.
- This is not a manufacturer-calibrated diagnostic model. RPM cannot be diagnosed from a single value; only Bank 1 trims are captured in this prototype, so comparison with Bank 2 requires an expanded interface.
- Service-worker cache bumped to v11.
