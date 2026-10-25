# Garage Diagnostic Assistant — v8 Low-Power Diagnostic Path

## Upload
Replace `index.html`, `manifest.json`, and `sw.js` in the root of the GitHub Pages repository, then commit changes. Wait for deployment before testing.

## What's new
- Added a dedicated answer-based low-power diagnostic path.
- Distinguishes smooth power loss from shaking/misfire symptoms.
- Gives priority to power loss under load without assuming a failed part.
- Treats a flashing check-engine light as a high-priority warning and discourages hard acceleration/repeated road tests.
- For steady engine light, requests stored/pending codes and freeze-frame data without falsely treating the light as proof of active misfire.
- Avoids appending generic low-power causes/checks over the tailored pathway.
- Service worker cache bumped to `garage-dx-diagnostic-v8`.

## Acceptance tests
1. Low power + smooth/no shake + under load + steady light: report should prioritize data/codes and under-load measurements; must not claim active misfire.
2. Low power + shaking/misfire: report should prioritize misfire confirmation and cylinder-specific tests.
3. Low power + flashing light: urgent caution appears, routine generic guidance is suppressed, codes/freeze-frame are requested when safe.
4. Overheating paths from v7 still behave as before.
5. Save, history, export, print and new diagnosis remain available.

## Limits
Rules-based prototype only; no live OBD-II connection and no confirmed part diagnosis. Follow manufacturer-specific service information. Avoid unsafe road tests.
