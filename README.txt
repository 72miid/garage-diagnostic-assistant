# Garage Diagnostic Assistant — Diagnostic Priority v7

Replace `index.html`, `manifest.json`, and `sw.js` in the root of the GitHub Pages repository. Commit changes and wait for deployment.

## What changed
- Non-urgent overheating now uses an answer-driven report instead of appending generic cooling-system causes and repeated routine checks.
- If overheating is mainly at low speed and the fan is reported not to run, the report prioritizes fan circuit testing.
- The fan path now separates checking fuse/relay and commanded power/ground from testing the fan motor, avoiding premature parts replacement.
- If the cold coolant level is already confirmed correct and the fan is not running, the report no longer adds a redundant coolant-level reminder.
- Urgent safety behavior from v6 is retained.
- Cache version bumped to `garage-dx-diagnostic-priority-v7`.

## Acceptance tests
1. Overheating + danger-zone answer: safety banner appears and routine diagnostics are paused.
2. Overheating but not red + low-speed/slow traffic + fan does not run + coolant at correct level: prioritize fan circuit; no generic duplicate cooling checks and no repeated coolant-level reminder.
3. Same symptoms but fan runs while temperature rises: prioritize verifying fan speed/airflow, then coolant/radiator/thermostat/circulation tests.
4. Non-overheating symptoms continue to use their symptom-specific checks.
5. New diagnosis, save/history, export and print controls remain available.

## Limitations
Rules-based prototype only. No live OBD-II connection and no confirmed part diagnosis. Follow vehicle-specific service information and do not open a hot cooling system.
