# Build 15.2 acceptance tests

## Mode separation
1. Open the app. Easy Mode is selected and only Easy Mode is highlighted.
2. Choose a symptom and continue. Easy Mode skips the Workshop Data panel.
3. Complete Easy questions. Confirm report says `EASY MODE` and hides Live-data analysis.
4. Return to intake and choose Workshop / Pro Mode. Confirm only Pro is highlighted and the mode description changes.
5. Continue. Confirm Workshop Data panel appears before Pro questions.
6. Complete Pro questions. Confirm report says `WORKSHOP / PRO MODE` and shows Live-data analysis.
7. Switch back to Easy Mode. Confirm ECT/RPM/STFT/LTFT are not part of the Easy flow.

## Data and report
8. In Pro Mode, enter a complete STFT/LTFT pair but leave warm-up or closed-loop unknown. Confirm interpretation is deferred.
9. Enter complete pairs for both banks and confirm warm + closed loop + same RPM/load. Confirm screening calculation appears.
10. Enter an out-of-range trim (e.g. 150). Confirm no interpretation is shown.
11. Confirm header and report both show Build 15.2.
12. Save a report, open Case History, reopen it, and compare mode, answers, findings, tests and codes.
13. Export JSON and print the report.
14. Start a new case and confirm observations, codes, readings and selected symptom are cleared.

## Safety and scope
15. Test oil pressure warning / P0520–P0524, overheating red-zone response, visible fuel leak and electrical smoke response.
16. Confirm unsupported DTCs are referred to OEM service information.
17. Confirm no UI claims live OBD connection or confirmed diagnosis.

## Not covered by static acceptance
Safari installation, offline behavior, physical OBD scanner validation, OEM threshold validation and real-vehicle repair validation require separate testing.
