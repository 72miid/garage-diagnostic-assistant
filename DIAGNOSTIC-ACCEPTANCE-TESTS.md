# Diagnostic acceptance tests — build 9

The report must reflect selected answers and must not assert a failed part without confirming evidence.

## Low power
1. Smooth + under load + steady engine light: choose “No, feels smooth but weak”, “At high speed / under load”, “Steady on”. Expect “Power loss under load — check measured data first”, saved-code/freeze-frame guidance, and no assertion of an active misfire.
2. Shaking/stuttering: choose “Yes, shakes or stutters” or “Sometimes”. Expect misfire/uneven combustion to be considered, with cylinder-specific tests and no guessed part replacement.
3. Flashing engine light: expect a safety-priority banner, no hard acceleration/repeated road tests, and codes/freeze-frame guidance.
4. Repeat low-power diagnosis twice: question count must remain stable.

## Overheating
5. Red gauge / warning / steam: urgent safety banner and routine tests paused.
6. Not red + slow traffic + fan does not run + coolant level correct: prioritize fan circuit checks without redundant coolant-level reminders.
7. Fan runs but temperature rises: verify airflow and cooling-system circulation; do not assume the fan is faulty.

## Other symptoms
8. No-start: distinguish no-crank from crank-no-start.
9. Rough idle + flashing engine light: prioritize safety and saving codes/freeze-frame data.
10. Smoke/fuel/electrical-burning smell: safety warning before routine diagnosis.
11. Oil-pressure or temperature warning: stop safely and switch off.
12. DTCs P0300–P0308 describe misfire patterns/cylinders; P0171/P0174 indicate lean-condition evidence; P0128 concerns warm-up/temperature regulation. No code alone proves a specific part failed.

## App behavior
13. New diagnosis resets radio choices, codes, live-data fields, and saved-question state.
14. Edit answers resumes the diagnostic questionnaire with previous answers selected.
15. Save/history/export/print remain functional.
16. Header/footer display BUILD 9 after deployment. If absent, the old page is still being served or cached.
17. Workshop live-data entries appear in the report as reference-only, not as interpreted results.
