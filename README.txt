# Garage Diagnostic Assistant — Complete package

## Upload
Replace these three files in the root of the GitHub Pages repository:
- `index.html`
- `manifest.json`
- `sw.js`

Commit the changes and wait for GitHub Pages to publish.

## Included
- Guided vehicle/symptom selection.
- Symptom-specific sequential questions.
- Answer-based prioritization for overheating, no-start, rough idle, low power, smoke/smell, and warning lights.
- Prominent safety-priority banner for reported red temperature gauge/steam, oil-pressure warning, and potential fire/fuel/electrical-burning risk.
- Case history in browser local storage, JSON export, print report, optional workshop live-data fields.
- Cache version bump and network-first handling for HTML to reduce stale-page issues.

## Important limitations
This is a rules-based prototype, not an AI mechanic, not an OBD connection, and not a confirmed diagnosis. It cannot identify a failed component without tests and vehicle-specific service information. Never open a hot cooling system. If an oil-pressure warning is active or the engine is overheating, stop safely and switch off.
