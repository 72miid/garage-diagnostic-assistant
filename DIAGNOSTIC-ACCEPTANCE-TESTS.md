# Build 15 — Acceptance test matrix

Use synthetic values only. Never present test values as measurements from a real vehicle.

| Test | Input | Expected |
|---|---|---|
| Safety overheating | Overheating; first answer Yes | Stop instruction; routine running tests not prioritized |
| Overheating at idle | No danger; stopped/traffic | Fan command/operation and airflow checks prioritized |
| Coolant loss | Cold coolant below minimum / visible leak | Leak identification and cold pressure-test path; no hot cap opening |
| Oil pressure warning | Warning-light symptom; Oil pressure | Stop engine and verify pressure before restart |
| P0171 | Enter P0171 | Intake inspection, warm closed-loop trims, smoke test, MAF/fuel delivery path |
| P0174 | Enter P0174 | Bank 2 lean interpretation; no automatic O2 sensor replacement |
| P0300 | Enter P0300 | Misfire counters, shared-cause checks, catalyst-protection warning |
| P0302 | Enter P0302 | Cylinder-specific ignition → injector → compression test sequence |
| P0308 | Enter P0308 | Cylinder 8 path; no automatic coil replacement |
| P0128 | Enter P0128 | Cold ECT/IAT plausibility, cold coolant check, warm-up behavior and OEM test |
| P0101 | Enter P0101 | Intake path, wiring/power/ground, MAF plausibility; no blind sensor replacement |
| Unknown DTC | Enter unsupported code | Clearly states OEM lookup required; no fabricated test path |
| No DTC | Leave code field empty | Symptom path still available; no code invented |
| Case persistence | Complete and save a case, reload page | Saved record remains in this browser |
| Print | Open report and print | Browser print dialog presents report |
| Cache update | Inspect `sw.js` | Cache name is `garage-dx-build-15` |

## Release gate
Do not call this a confirmed diagnostic system until it has been tested on representative vehicles, validated against OEM service information, and reviewed by qualified technicians. Build 15 is a structured prototype with explicit limits.
