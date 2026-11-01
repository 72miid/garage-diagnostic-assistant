# Build 15.1 acceptance test matrix

Use synthetic values only for software checks. Do not treat sample values as readings from a real vehicle.

| Test | Input / setup | Expected result |
|---|---|---|
| Version | Load deployed app | Header and report show Build 15.1 |
| Cache | Inspect `sw.js` | Namespace is `garage-dx-build-15-1` |
| Easy / Pro | Switch modes | Both controls work; Easy hides selected advanced ECT/RPM fields |
| Guided questions | Select each symptom | Relevant adaptive questions appear and report builds |
| P0171 / P0174 | Enter code | Lean-condition test sequence appears; no O2 sensor replacement assumption |
| P0300–P0308 | Enter code | Misfire path appears; cylinder-specific code is described |
| Other P03xx | Enter P0315 | No generic misfire classification |
| P0128 | Enter code | Cold ECT/IAT and warm-up checks appear; thermostat not condemned automatically |
| P0101 | Enter code | Intake, wiring, MAF plausibility checks appear |
| P0524 | Enter code | Safety-priority stop instruction appears; no engine-running live-data test |
| Overheating | Answer Yes to red-zone / steam question | Safety priority appears and routine checks are paused |
| Fuel leak | Smoke/smell = fuel, visible smoke/leak = Yes | Stop-priority warning appears |
| Electrical smoke | Burning electrical smell + visible smoke = Yes | Stop-priority warning appears |
| No trims | Leave all STFT/LTFT blank | No trim conclusion |
| Incomplete pair | Enter STFT B1 only | Complete same-bank pair requirement shown |
| One bank | Enter STFT + LTFT B1 only | B1 estimate shown; bank comparison deferred |
| Context gate | Both banks entered; warm or closed-loop unknown | Interpretation deferred |
| Matching gate | Both banks complete; same RPM/load = No | Bank comparison deferred |
| Valid context | Both pairs; warm Yes; closed loop; same conditions Yes | Preliminary comparison appears |
| Implausible trim | Enter value outside -100 to +100 | Interpretation paused and verification warning appears |
| Save / history | Save a case, open history | Case is listed and summary can be reopened |
| Export | Export history | JSON file downloads |
| Print | Print report | Browser print view opens |

## Scope
This is a manual acceptance checklist. Static checks do not replace browser interaction tests, GitHub Pages deployment verification, scanner validation or a technician's diagnosis.
