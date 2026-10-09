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

## Equal-budget, reactive-policy comparison v0.5 — 2026-10-08

Created downloadable Python harness `project_splice_sim_v05.py` and CSV trial and budget outputs. These artifacts are prototypes, not canonical game implementation.

**Methods:** four archetype squads (Fire/Wind, Water/Wind, Earth/Water, Fire/Earth), each with 16 occupied slots and role-specific creature assignments. Normalize **aggregate** HP, MP, ATK, WIS, SPD separately to closely matching totals while keeping individual species relative shapes. Test early (reduced stats and high-rank skills replaced with available C/D substitutes) and midgame (original skill assignment), 16 seeds both starting-side assignments, all six distinct pairings: **384 battles**. Side policy heuristically scores *currently affordable active skills, healing urgency, missing MP, status cleansing, active MP costs and resting needs*; policies restricted to the strategy's two elements. Eighteen-round cap. Note this is still not sophisticated planning.

**Results (wins for first named team, out of 32 trials per pairing/tier; others win unless specified as time-limit cases):**
| Matchup | Early first-team wins | Early time limits | Mid first-team wins | Mid time limits |
|---|---:|---:|---:|---:|
| Fire/Wind vs Water/Wind | 31 | 1 | 32 | 0 |
| Fire/Wind vs Earth/Water | 2 | 10 | 0 | 0 |
| Fire/Wind vs Fire/Earth | 6 | 23 | 0 | 32 |
| Water/Wind vs Earth/Water | 0 | 0 | 0 | 0 |
| Water/Wind vs Fire/Earth | 0 | 32 | 0 | 32 |
| Earth/Water vs Fire/Earth | 32 | 0 | 32 | 0 |

The normalized midgame stat budgets were all within about 3 points of each desired aggregate (HP 2320, MP 1640, ATK 640, WIS 630, SPD 525). Early totals within about 5 points of targets (HP 1600, MP 900, ATK 470, WIS 440, SPD 410). Unit assignments, innate passives, elemental availability, and move mixes still differ by archetype.

**Findings and limitations:** Water/Wind underperforms in this fixed model; Earth/Water strongly performs, possibly due to mechanics, selected skills or heuristic choices. These are **not final judgments on elemental balance**. The test has simplified targeting, attack/status resistance, incomplete passives, limited skill families and no adaptive multi-turn lookahead. Equal aggregate stats are not equivalent tactical strength; high-tier loadout swaps are coarse. No changes to approved combat rules. Recommended next investigation: inspect action logs and missing move coverage, compare policy-only vs formation-only controls, then refine skill-cost healing/control values with paired experiments.

## Corrected Water/Wind control loadouts v0.6 — 2026-10-08

Tested two revised Water/Wind variants, using v0.5 rules and aggregate stat budgets, against Fire/Wind and Earth/Water, in early/mid tiers, 16 seeds with side swaps: **256 runs**. This was a targeted **test-fixture modification** rather than a change to approved game mechanics.

- **Balanced**: Venom Fang on front Wind positions; Dark Gust, Sleeping Mist, and Withering Gust on rear Wind positions; Water front healing/attacks plus rear Healing Rain and Mana Current. Positions use Water/Wind shared corners and adjacent-element surcharge.
- **Control**: swaps in a second Sleeping Mist and a second Withering Gust option for more explicit disable/heal suppression, keeping Water restoration and physical offense.
- Confirmed that Wind activation includes actual Poison, Sleep, Blind or Heal Block applicators; Water activation uses both Water restoration and some surcharge-based Wind skills as designed.
- **Result:** each variant went 0 wins / 32 runs versus Fire/Wind and 0 / 32 versus Earth/Water, in **both** early and mid tiers (256 total, no time-limit draws).
- **Interpretation:** corrected status availability alone did not improve outcomes in this v0.5-derived test. This does **not** justify balance changes yet: some powerful high-rank effects are still present in the early tier; enemy rosters, relative unit roles, single-turn policy, control effect eligibility, and targeting are not proven fair. In particular, each assigned status skill's chance, live target selection and actual casts must be inspected before deciding whether control is ineffective or the simulator's side selection is at fault.
- Next: instrument combat events (ability used, hit/apply counts, enemy actions denied, wasted healing, net MP, center lane pressure), verify tactical policy and skill-slot legality. Consider true deterministic counterfactuals on identical encounter states.

## Instrumented Water/Wind diagnostics v0.7 — 2026-10-08

Reran **256** v0.6 corrected-loadout battles (Balanced and Control variants; Fire/Wind and Earth/Water opponents; early/mid; 16 seeds, both sides swapped) with event counters for skill casts, status attempts/successes, Sleep actions denied, effective/overheal amount, MP restoration, skill expenditures and center shield hits. Exported detailed CSVs and a limited per-action trace. No mechanics or numerical balance altered.

**All eight comparisons still had 0 Water/Wind wins out of 32.** In this fixture, neither variant caused a trainer shield hit, and their opponents registered six hits per battle.

Aggregated per Water/Wind battle:
| Signal | Balanced | Control |
|---|---:|---:|
| Sleeping Mist casts | 2.88 | 6.25 |
| Successful Sleep applications | 3.45 | 8.64 |
| Successful Heal Block applications | 1.45 | 2.06 |
| Successful Poison applications | 2.84 | 3.03 |
| Effective HP healed | 80.3 | 90.94 |
| Healing capacity unused due to full HP or overheal | 66.9 | 70.1 |
| MP restored by skills | 85.3 | 92.4 |
| MP spent on skills | 363.1 | 422.6 |
| Trainer shield hits | 0 | 0 |

Additional actual **enemy actions denied by Sleep**: against Fire/Wind, 1.50 per Balanced battle / 4.59 per Control; against Earth/Water, 2.47 / 7.41. Sleep is being cast and prevents actions, contrary to the initial concern that Wind skills were never activating; a lot of additional applications refresh Sleep, hit enemies that don't act again or are removed by damage, so raw status applications must not be equated to actions denied.

**Takeaway:** v0.6's roster bug was corrected, but statuses actually trigger; the team lacks center-lane shield pressure. This is not yet evidence that Water/Wind is inherently weak. Targeting and formation openings, heal-use efficiency, comparison policy and **win-by-center-shield** must be scrutinized. Status numeric balance unchanged. Note diagnostic early-tier retained some B-rank skills and is not a faithful early-game test.

**Important implementation caveat:** This is still a simplified model; e.g. simulation win condition is shield-based, skill heuristics are crude and some skill families do not handle all the intended target semantics. Keep results experimental.

## v0.8: two-turn planning and five-encounter expeditions (2026-10-08)

An experimental executable Python script `project_splice_sim_v08.py` and its generated `project_splice_sim_v08_engine.py` were produced, with CSVs `Project_Splice_Expeditions_v0.8.csv` (encounters) and `Project_Splice_Expedition_Summary_v0.8.csv` (aggregates). Sources/results are downloadable from that ChatGPT conversation; these files are **not** in the repository.

**Test design:** Four archetypes (pure offense, Wind setup + Fire payoff, four-element balance, Earth/Water endurance); 16 assigned monsters/team with matching aggregate stat budgets per tier inherited from v0.5; early/mid tier; 12 seeded expeditions per variant; five fights (three wild, one elite, one trainer). Wild win requires KO of all six wild foes; trainer win by shields. Player HP/MP/KO and shield counts persist across encounters. Opponents use fixed elemental side; test player has heuristic two-step action-value scoring, Wind-setup bonus, and policy-specific directional biases. This is **not** an actual two-ply battle-state simulator or expert side AI. 22-round cap per fight; hitting time cap counts as noncompletion. Status and targeting fidelity still approximate.

**Both original and lowered-difficulty tests:** The initial opponent setup produced 0/12 expedition completions for every archetype/tier; calibrated foes had 0.68x HP and 0.70x ATK/WIS (these are arbitrary diagnostic difficulty multipliers, not progression recommendations).

| Strategy | Calibrated early expedition completions /12 | Calibrated midgame /12 |
|---|---:|---:|
| Pure offense | 1 | 0 |
| Wind setup/Fire burst | 0 | 1 |
| Balanced all four | 12 | 12 |
| Defensive endurance | 12 | 12 |

**Interpretation:** Multi-encounter recovery/replenishment matters dramatically under current HP/MP persistence, and wind setups did not translate into reliable expedition completion in this fixture. But **not evidence of true meta**: encounter tuning severely favors recovery, all teams' opponents were fixed-side AI, Wind/Fire loadout can be poor, staged wild opponents are reconstituted from same-level individual species without equal encounter budget, special target fidelity incomplete, and the lookahead estimates utility rather than simulates two actual turns. Strong results for sustain may reflect a fixture advantage; never change canonical combat rules based solely on these scores.

**Next test priority:** Before tuning skills, instrument **element choices per turn**, actual Wind→Fire transitions, status effect follow-up damage, healing/MP efficiencies, and center-lane damage per side. Compare controlled ablations *within the same formation* (Wind enabled/disabled, passive restore on/off), evaluate intelligent enemy choice, and calibrate expedition difficulty to a non-trivial completion range (not 0% or 100%). Consider explicit rules for inter-battle recovery and trainer shields.

## v0.9 — side-rotation diagnostics, intermediate difficulty, support ablations

- Script: `project_splice_sim_v09.py`; exports `Project_Splice_Expeditions_v0.9.csv`, `Project_Splice_Diagnostics_v0.9.csv`, `Project_Splice_Rotation_Traces_v0.9.csv`, `Project_Splice_Ablations_v0.9.csv`. Generated in the ChatGPT session; links provided there. All numeric values and controls are experimental.
- **256 five-encounter expedition runs**: 4 archetypes × early/midgame × 4 difficulty variants × 8 seeds. Intermediate difficulty test scales *enemy* HP to 80%, 86% or 92%, ATK/WIS to 82%, 88% or 94%, respectively, relative to original prototype; previous 68%-HP calibrated difficulty included as a reference. No changes to canonical combat rules.
- Actual selected side frequency and Wind→Fire consecutive-round transitions now recorded, alongside Sleep actions denied and shield hits. NOTE: sequences are *not* verified Sleep→critical-hit payoffs, only adjacent side selections; transitions may span encounter boundaries in this diagnostic and require separation in later versions.
- At enemy 86% HP/88% ATK+WIS: early balanced four-element build finished **4/8** expeditions; all other archetype/tier conditions, including midgame balanced, finished **0/8**. The early setup-and-burst policy chose Wind→Fire 5.12 times per expedition on average but did not finish a complete expedition. This establishes rotation **selection**, not genuine setup payoff.
- Within early balanced build (same eight seeds, enemy 86% HP / 88% damage-stat scale), replace *Water healing + MP restoration skills* with same-row Water attacks: expeditions finished **0/8** vs **4/8** baseline, mean stages 3.38 vs 4.25. Replace Earth protection skills with attacks: **3/8** completed, vs 4/8 baseline, mean stages 4.38. These skill-replacement ablations also alter DPS and spell affinities; they are diagnostic rather than clean causal measurement of healing alone vs Earth protection.
- **Important caveat**: the underlying v0.8 planner is still a two-step utility approximation, not actual two-turn rollout; enemy strategy remains fixed-side; the early/mid roster skill allocation remains problematic; statuses, special targeting and healing specifics have partial fidelity. The engine's result collection reports observed metrics but doesn't yet count critical extra damage due specifically to Sleep or missed attacks from Blind. Do NOT interpret these as definitive balance judgments.
- Follow-up priorities: reset transition tracking at encounter boundaries, record exact Sleep-to-critical chains and effect attribution, implement real prospective two-action planning, test varied enemy tactical controllers and reward an expedition-completion range between ~20% and ~80% without tuning solely around one archetype.

## v1.0 — Per-action Sleep attribution and progression diagnostic (2026-10-08)

**Runnable experiment**: `project_splice_sim_v10.py` and generated `project_splice_sim_v10_engine.py`; CSV exports `Project_Splice_Expedition_Attribution_v1.0.csv`, `Project_Splice_Attribution_Summary_v1.0.csv`, `Project_Splice_Action_Trace_v1.0.csv`. Artifacts generated in conversation, **not committed to repo**.

**Methods:** Same v0.8 combat formulas, 12 expeditions × four strategies × two early/mid tiers = **96 expeditions**, one intermediate enemy scaling (86% HP, 88% ATK/WIS), with five encounters maximum. Track per-encounter active side selections, Wind→Fire transition, Sleep application, wake-up critical count and bonus damage, enemy actions skipped; encounter boundaries now reset rotation tracking. Enemy side remains fixed and player policy remains the crude v0.8 two-step *utility estimate*, NOT genuine two-turn state rollout. No approved combat mechanics changed.

**Experiment result (early / mid):**
- Setup and burst: 51 / 42 Wind→Fire transitions, 32 / 13 Sleep applications by the player, 32 / 12 wake-up criticals, bonus crit damage 306 / 363, 0 / 0 *confirmed* Sleep applied on Wind in one round and consumed by Fire in a later round, and 0 / 0 completed 5-encounter expeditions.
- Balanced: 7/12 early expedition completions, 0/12 mid. Its Sleep wake-up criticals were 38 early / 40 mid, for ~560 / 902 bonus damage.
- Pure offense and defensive endurance: 0/12 completions each tier.
- **Major discovery:** actual Sleep crits do occur but not in the presumed Wind-then-Fire pattern. Per-action trace shows a Fire-selected side applying Sleep from an adjacent Wind skill, followed by a Water-side **basic attack** waking that target. This is valid for adjacency rules but the planning heuristic cannot accurately value and sequence these combinations.
- **Trace caveat:** Some species names repeat within an encounter; the coarse correlation by target name can misattribute Sleep source if different individual specimens share a name. The reported zero exact Wind→Fire followups is diagnostic, **not a rigorous identity-safe proof**. The direct global wake bonus metric is engine-derived. Need immutable per-monster IDs for definitive chain attribution.
- **Progression flaw:** v0.4-derived early loadouts are generated by taking midgame-species move sets, then automatically replacing only A/S skills with arbitrary first matching C/D damage/heal/ward moves; B-ranked moves survive early, and midgame contains many high-cost S/A moves. This can make midgame more MP-hungry, suppress actual support skills, and confuse the comparison. Equal *aggregate* stats do not imply legal, equivalent progression. **Do not tune game progression on observed midgame failure.**

**Next engineering priorities:** immutable entity IDs per slot for status→wake attribution, a genuine two-turn state-based side-selector with adversary response approximation (rather than scoring future hypothetical actions on unchanged state), authored D/C early and B/A mid loadouts with comparable power and MP economy, responsive enemy rotations, and enough difficulty settings for nondegenerate completion rates. Retest then, do not weaken Wind or Sleep on these data.
