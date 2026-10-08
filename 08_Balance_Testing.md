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

## Full formation simulator v0.3 — 2026-10-08

New experimental Python test harness and Excel summary created during design session.

**Changes and coverage**
- Fixed the v0.2 trainer-targeting issue: a lane-aligned attack may strike the trainer immediately when the opponent's **front and rear middle slots are both empty**, even when enemy flank monsters survive. This requires testing each target behavior more extensively and is not the only final shield-targeting rule.
- Sequential SPD ordered actions, immediate KO/protection updates, basic sleep wake-up critical, Poison and Mana Burn full-round ticks.
- Compared four scripted rotation patterns, four numerical settings (standard, weaker MP restoration, stronger MP restoration, stronger Ward), four fixed matchup compositions and 12 seeds: **768 total simulations**.
- Specific validation assertions passed for breached-center trainer attacks, protected rear exclusion, and no automatic shield attack from a flank-aligned basic hit.
- Case-specific base rotations under the standard numeric setting: Water/Wind vs Fire mean 6 rounds and 0 build shield hits; Fire/Wind vs Earth mean 8 rounds and 6 build shield hits; Earth/Water vs Fire mean 10 rounds and 0 build shield hits; Fire/Earth vs Water mean 5 rounds and 6 build shield hits.
- In these simplified setups some aggressive builds win by removing shields while enemy monsters still survive; this is **expected** if a central lane is exposed. The presence of six hits alone does not prove a fair balance advantage.

**IMPORTANT LIMITATIONS**: Fixed scripts (not intelligent decisions), 12 assigned monsters per team (within a 16-slot geometry), uneven comparative rosters, incomplete rules and status behavior, provisional damage/MP/buff values; random seeds do not imply comparable fair trials. The current routing for skills with special targets is not authoritative. Next milestone should test precisely defined special-skill trainer targeting, full skill targeting and status compatibility, equal-budget rosters, and side-policy optimization. **Do not tune elemental balance yet.**
