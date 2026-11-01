# Build 14.1 acceptance test matrix

Use synthetic values only for software checks. Never treat sample values as readings from a real vehicle.

| Test | Input / setup | Expected result |
|---|---|---|
| Build label | Load deployed app | Header and footer show BUILD 14 |
| Cache | Inspect `sw.js` | Cache namespace ends in `v14` |
| P0300 | Enter code P0300 | Misfire guidance appears |
| P0308 | Enter code P0308 | Misfire guidance appears; cylinder 8 code description shown |
| Other P03xx | Enter a non-P0300–P0308 P03xx code (e.g. P0315) | No generic misfire classification; generic code guidance only |
| No trims | Leave all STFT/LTFT fields blank | Report says no fuel-trim values entered and makes no trim conclusion |
| Incomplete pair | Enter STFT B1 only | Report says both STFT and LTFT from one bank are required |
| One complete bank | Enter STFT + LTFT B1 only | B1 estimate shown; B2 marked incomplete; no bank comparison |
| Two banks, unknown context | Enter both pairs; leave warm-up/loop/matching condition unknown | Combined estimates may be displayed, but interpretation is deferred |
| Two banks, open loop | Enter both pairs; warm Yes; loop Open loop | Fuel-trim conclusion deferred |
| Two banks, mismatched conditions | Enter both pairs; warm Yes; Closed loop; same condition No | Bank comparison deferred |
| Valid matching context | Enter both pairs; warm Yes; Closed loop; same condition Yes | Preliminary pattern classification appears; no component is declared failed |
| Implausible trim | Enter any trim below −100 or above +100 | Interpretation paused and value verification warning appears |
| Data disclaimer | Generate report with or without numeric entries | Report states values are manual and app cannot verify vehicle/PID/units/conditions; sample values are not real measurements |
| Save/export | Save a report and export history | Case includes manually entered values and context fields |
| Safety | Trigger a safety-priority scenario | Routine checks remain paused as in Build 13 |

## Scope
This matrix is a manual acceptance checklist. Static source checks and JavaScript syntax validation do not replace browser interaction tests, deployment checks, scanner verification, or a technician's diagnosis.


## Build 14.1 regression checks
- [ ] One complete bank pair + other bank incomplete + warm-up unknown: report the incomplete bank and defer interpretation.
- [ ] One complete bank pair + other bank incomplete + open loop: report the incomplete bank and defer interpretation.
- [ ] No trim values: explicitly state no fuel-trim values were entered.
- [ ] Only one STFT or LTFT value: explicitly state a complete same-bank pair is required.
- [ ] Both banks complete but conditions differ: defer bank-to-bank comparison.
