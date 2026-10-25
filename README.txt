# Garage Diagnostic Assistant — Phase 1 refinement v6

Replace `index.html`, `manifest.json`, and `sw.js` in the repository root. Commit changes and wait for GitHub Pages to publish.

## Fix in v6
Urgent safety states show only safety-relevant causes and actions. Generic diagnostic checks are suppressed instead of being appended after the warning. Actions are labeled `SAFETY ACTION`, a notice says routine diagnostics are paused, and code interpretation is deferred while the vehicle may be unsafe. Cache name bumped to `garage-dx-phase1-v6`.

## Acceptance checks
1. Overheating + red gauge/warning/steam: top safety banner appears; routine checks are paused; no generic repeated cooling-system steps appear.
2. Overheating without danger-zone warning + low-speed symptom + fan does not run: report prioritizes fan-circuit testing.
3. Overheating without danger-zone warning + fan runs but temperature rises: report prioritizes airflow confirmation and coolant/radiator/thermostat/circulation checks.
4. Oil-pressure warning: urgent banner and no routine engine-running tests.
5. Smoke/fuel/electrical burning: safety banner and no routine test prompts.
6. Non-urgent symptoms still show answer-based checks and codes.
7. New diagnosis, save, history, export, and print controls remain available.

## Limitations
Rules-based prototype only; not a live OBD-II connection and not a confirmed diagnosis. Use vehicle-specific service information. Never open a hot cooling system.
