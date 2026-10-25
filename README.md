# Garage Diagnostic Assistant — Build 9

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
- Manually entered workshop live-data values appear in the report, clearly marked as reference-only because this prototype does not automatically validate or interpret them.
- Added DTC descriptions for P0305–P0308, useful for an eight-cylinder engine.
- Added BUILD 9 label so a stale app can be distinguished from the deployed build.
- Bumped the service-worker cache version.

## Publish
Replace the repository-root `index.html`, `manifest.json`, `sw.js`, and `README.md` with the matching files in this package. Add `DIAGNOSTIC-ACCEPTANCE-TESTS.md`. Commit the changes and wait for GitHub Pages to deploy. The GitHub integration currently rejects write operations, so this package is ready for manual upload.

## Limits
This is a rules-based prototype, not a confirmed diagnostic system. It has no live OBD-II connection, does not clear codes, and cannot automatically interpret manually entered live data. Use manufacturer-specific service information and safe test procedures. Never open a hot pressurized cooling system. Stop safely for severe overheating, oil-pressure warnings, fuel leaks, smoke, or other immediate danger.
