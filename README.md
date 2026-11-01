# Garage Diagnostic Assistant — Build 15.2

Mobile-first static diagnostic-guidance PWA.

## Main changes
- Separates Easy Mode and Workshop / Pro Mode into distinct diagnostic paths.
- Easy Mode uses simplified symptom questions and a plain-language report; it does not show scanner live-data fields.
- Pro Mode includes technical symptom questions, manual ECT/RPM/STFT/LTFT entry for both banks, and conditional fuel-trim screening.
- Mode buttons have mutually exclusive active states and a visible mode description.
- Report version and application version are both Build 15.2.
- New Case clears text inputs, radio choices, selects and the observations textarea.
- Saved reports retain mode, answers, findings, test plan and code guidance when reopened.
- Retains local case history, JSON export, print report, DTC guidance and safety-priority handling.

## Deploy
Replace `index.html`, `sw.js`, `manifest.json`, and `README.md` in the repository root. Keep `DIAGNOSTIC-ACCEPTANCE-TESTS.md` if it is already present, or upload the included test file. Wait for GitHub Pages deployment before testing.

## Important
This is a static guidance tool. It has no live OBD-II connection, automatic PID capture, VIN decoding, ECU communication, code clearing, OEM database or manufacturer wiring diagrams. All readings are manually entered. Fuel-trim bands are preliminary screening guidance, not factory pass/fail limits. Verify all procedures and specifications against service information for the exact vehicle. Never replace a component based only on a DTC.

## Verification status
Source syntax and static checks should be run after download. Safari/PWA interaction, GitHub Pages cache behavior, scanner validation and real-vehicle tests remain to be completed.
