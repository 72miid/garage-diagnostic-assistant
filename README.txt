# Garage Diagnostic Assistant — Phase 1 Complete (v5)

## Upload
Replace the existing `index.html`, `manifest.json`, and `sw.js` in the root of the GitHub Pages repository with the three files in this package. Commit changes and wait for GitHub Pages to publish.

## Phase 1 improvements
- Sequential symptom-specific questions.
- Answer-based prioritization for overheating, no-start, rough idle, low power, smoke/smell, and warning lights.
- Safety-first report banners for red-temperature/steam, oil-pressure warning, and potential smoke/fuel/electrical-burning risk.
- In urgent cases, routine diagnostic checks are suppressed instead of repeating contradictory/general steps.
- Overheating guidance branches by reported conditions: low-speed vs moving, fan behavior, and cold coolant level.
- Case history, JSON export, print report, and optional workshop live-data fields.
- Service-worker cache version bumped to `garage-dx-phase1-v5`.

## Manual acceptance tests after deployment
1. Overheating + “Yes — red gauge / warning / steam”: report must show a red safety-priority banner first, no routine checks that suggest continued testing, and a stop/switch-off instruction.
2. Overheating + “It rises but is not in the red” + “Mostly stopped or idling” + “Fan does not run”: report should prioritize fan-circuit verification.
3. Same overheating answers but “Fan runs but temperature rises”: report should instead mention airflow verification and coolant/radiator/thermostat/circulation checks.
4. No-start + “Cranks normally but will not start”: report should show crank-no-start checks, not battery/starter as the first assumption.
5. Rough idle + flashing engine light: report should warn against driving under load and prioritize misfire code capture.
6. Smoke/smell + fuel smell or electrical burning smell: report must show a safety banner and suppress routine checks.
7. Use New diagnosis after a report: the wizard must return to the vehicle selection screen.
8. Save a case, open Case history, and export history.

## Limitations
This is a rules-based prototype. It is not a live OBD-II connection, does not clear codes, and cannot confirm a failed part without appropriate tests and vehicle-specific service information. Never open a hot cooling system. If an oil-pressure warning is active or the engine is overheating, stop safely and switch off.
