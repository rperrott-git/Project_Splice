# Balance testing — v0.2 (2026-10-08)

A Python prototype and accompanying Excel balance workbook were generated in the conversation. This is a **testing harness** only, not authoritative game data or a completed Godot implementation.

## Exercised systems
- 16-position geometry per team (8 front, 8 rear), sharing cardinal-side corners; test scenarios fill 12 positions per team.
- Selected-side activation and cyclic scripted side rotations; exact-element or adjacent off-element skill with a **test-only 30%** MP surcharge.
- Front groups before rear groups; team initiative by mean living row SPD, then individual descending SPD, with immediate action resolution and dynamic targeting.
- Lane protection, damage, HP/MP recovery, assorted skill effects and status ticks. All numbers preliminary.
- Four fixed matchups and twelve seeded runs per matchup. No trained tactical side-selection AI.

## Latest corrected results
| Scenario | Mean rounds (12 runs) | Mean remaining HP, build/opponent |
|---|---:|---:|
| Water/Wind versus Fire | 6 | 830 / 1474 |
| Fire/Wind versus Earth | 8 | 1062 / 1387 |
| Earth/Water versus Fire | 10 | 821 / 1147 |
| Fire/Earth versus Water | 5 | 1734 / 1192 |

These do not establish balance rankings: starting rosters, level-like stats, MP values, skills, and scripted rotations are not balanced or equivalent, and remaining HP is not a direct winner determination.

## Outstanding fidelity work
- Shield attacks are simplified and currently only tested when there are no eligible monster targets. Implement central-lane routing even while other lanes contain monsters, before using trainer matchups for balance claims.
- Add sophisticated automatic skill targeting, precise healing/cleansing/status action timing, status duration rules and passives.
- Verify that side activation/corner resting, row initiative, and pierce/splash targeting reflect final intended design.
- Test alternative rosters and fair baselines with paired seeded trials and meaningful win conditions; vary MP restoration and defensive buff strength.
- Prototype adds *Siphoning Mist* (Mana Burn application) as a **33rd test skill**, not approved canonical content.
