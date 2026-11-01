# Diagnostic acceptance tests — Build 13

All tests use simulated data. No test result is a real vehicle diagnosis.

## Fuel trim classification
For all comparison tests, select: engine fully warmed = Yes; fuel system = Closed loop; same RPM/load across banks = Yes.

1. **Shared positive correction:** Bank 1 STFT +15, LTFT +12; Bank 2 STFT +17, LTFT +14. Expect both combined estimates (~+28.8% and ~+33.4%) and a shared-pattern explanation. Do not name a failed part.
2. **Bank-specific positive correction:** Bank 1 STFT +25, LTFT +18; Bank 2 STFT +3, LTFT +5. Expect a stronger Bank 1 pattern and bank-specific checks, not a definitive component diagnosis.
3. **Low corrections:** Bank 1 +3/+5; Bank 2 +2/+4. Expect no notable combined correction in this sample, not a declaration that the vehicle is fault-free.
4. **Shared negative correction:** Bank 1 −15/−12; Bank 2 −17/−14. Expect similar notable negative correction on both banks.
5. **Conditions unknown / cold / open loop:** Expect classification to be deferred; show the estimates only with a clear caution.
6. **Different RPM/load across banks:** Expect comparison to be deferred and request a repeat under matching conditions.
7. **Only one complete bank pair:** Show one combined estimate and state that bank comparison is unavailable.
8. **Implausible trim outside −100% to +100%:** Pause fuel-trim interpretation and ask to verify sign, units and PID.
9. **Difference near threshold:** Do not overstate borderline differences; retain cautious language.

## Other live data and safety
10. ECT 120°C: prompt verification; stop safely and switch off if actual overheating/warning is present; never open a hot cooling system.
11. RPM 0: ask whether engine off/cranking/PID unavailable; do not diagnose from zero alone.
12. All live data blank: do not invent readings or show a false conclusion.
13. Flashing MIL with rough running: safety priority, avoid driving and save codes/freeze-frame when safe.

## App integrity
14. New diagnosis clears numeric live-data fields and resets context selectors to Unknown.
15. Saved history and JSON export preserve all six numeric values and three measurement-context values.
16. Older saved cases missing new context fields must not crash; missing context is treated as Unknown.
17. Header/footer show BUILD 13 and service-worker cache name is v13.
18. JavaScript parses successfully; HTML IDs are unique.
