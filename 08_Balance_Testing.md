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

## Equal-roster & targeting experiment v0.4 — 2026-10-08

**Runnable Python source** and CSVs were produced in the conversation (not committed to repo). v0.4 starts both sides with **identical twelve monsters, stats, skills and slots**, comparing only scripted elemental rotations. Swaps A/B assignments and repeats 24 seeds for each matchup = **336 runs** across seven comparisons.

**Explicit targeting test rules** (PROTOTYPE interpretations, not all canonical): lane-targeted single-hit attacks prefer corresponding enemy lane and target unprotected fronts/rears; piercing prefers protected/unprotected rear; Execute seeks lowest absolute living eligible HP; Magma seeks greatest HP capacity; splash extends to neighboring positional lanes; row effects touch eligible front row; center-lane-aligned ordinary hits may strike trainer shields when both center monsters are down even if flank monsters survive. Execute, piercing, highest-HP and row-wide attacks do *not* auto-seek shields. Healing chooses most injured by fraction of HP. Status and resource effects resolve sequentially; DoT ticks once per full round.

**Results (wins for first strategy / 48, 14 round cap):**
- Water/Wind vs Fire-only: 0 wins, 0 draws.
- Fire/Wind vs Fire-only: 48 wins, 0 draws.
- Earth/Water vs Fire-only: 0 wins, 0 draws.
- Fire/Earth vs Fire-only: 48 wins, 0 draws.
- Water/Wind vs Earth/Water: 0 wins, 0 draws.
- Fire/Wind vs Fire/Earth: 0 wins, **48 time-limit draws**.
- Four-side cycle vs Fire-only: 48 wins, 0 draws.

**Smoke tests:** center-lane breach; living front protecting rear; piercing reaching rear; Water-selected adjacent Wind move incurring 30% test MP surcharge. All passed in v0.4.

**Interpretation:** Results are *not* relative elemental power rankings; the same fixed roster disproportionately suits some selected sides, many high-rank moves are equipped initially, scripted choices ignore HP/MP/opponent state, and the 24 seeds cannot resolve systematic roster/script bias. Time-limit results are not draws under final game rules. This prototype still has simplified passives, skill targeting edge cases, healing priorities, shields, and row/status interaction; **no changes to canonical combat balance justified yet**.

**Next priority:** compare deliberately balanced element-specific team budgets across side-selection policies; choose viable reasonable policy controllers (e.g. threshold MP/HP-aware), verify shield routing through hand-authored microtests and improve skill-effects fidelity. Distinguish trainer from wild wins.
