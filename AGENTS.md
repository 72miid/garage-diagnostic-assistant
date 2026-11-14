# Garage Diagnostic Assistant — Codex Project Instructions

## Project identity
Repository: `72miid/garage-diagnostic-assistant`.
Mobile-first static diagnostic-guidance PWA. Current README identifies Build 15.2.

## Product boundaries
- This is a diagnostic-guidance tool, not a live vehicle scanner.
- No live OBD-II connection, automatic PID capture, VIN decoding, ECU communication, code clearing, OEM database, or manufacturer wiring diagrams are currently documented.
- Live readings are manually entered.
- Never claim a fault is confirmed from a DTC alone or recommend replacing a component solely because of a code.
- Fuel-trim bands are preliminary screening guidance, not factory pass/fail limits.
- Verify procedures and specifications against service information for the exact vehicle.

## Workflow
1. Read README and `DIAGNOSTIC-ACCEPTANCE-TESTS.md` before changing diagnostic behavior.
2. Preserve Easy Mode and Workshop/Pro Mode separation, local case history, export, print, DTC guidance, and safety-priority handling unless explicitly requested.
3. Run syntax/static checks and acceptance checks after changes.
4. Clearly identify what still requires Safari/PWA, scanner, or real-vehicle testing.
5. Never claim vehicle validation without an actual vehicle test.
