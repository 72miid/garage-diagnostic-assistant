# Garage Diagnostic Assistant (Garage Dx)

An iPhone-friendly, installable PWA prototype for workshop diagnostics.

## Prototype features
- Vehicle details, complaint and symptom selection
- Manual entry of OBD-II DTCs and live data (ECT, STFT/LTFT both banks, MAF, RPM, voltage)
- Rule-based diagnostic directions and ordered test plans
- Generic OBD-II quick reference library
- Local case history and JSON backup export
- Print-friendly diagnostic report
- PWA manifest and service worker app shell

## Run locally
Open `index.html` for basic UI testing. PWA installation and service worker caching require HTTPS or localhost.

## Publish with GitHub Pages
1. Create a new repository named `garage-diagnostic-assistant`.
2. Upload `index.html`, `manifest.json`, `sw.js`, and `README.md` to the repository root.
3. Open Settings → Pages → Build and deployment.
4. Select Deploy from a branch, branch `main`, folder `/ (root)`, then Save.
5. Wait for the Pages deployment to complete and open the HTTPS URL in Safari on iPhone.
6. In Safari, use Share → Add to Home Screen.

## Current limitations
- Hybrid-ready architecture: this first prototype uses transparent deterministic rules; it does not call an AI API yet.
- Local browser storage only. No accounts, cloud sync, or direct OBD adapter/MaxiSys integration.
- The included DTC library is deliberately small and generic. OEM-specific definitions and procedures must be checked for the exact vehicle and module.
- The tool provides hypotheses and test suggestions, not confirmed diagnoses. Use manufacturer service information, wiring diagrams and safe workshop procedures.
- Never open a hot pressurized cooling system. Stop safely if severe overheating, fuel leakage, electrical smoke or other immediate danger is present.
