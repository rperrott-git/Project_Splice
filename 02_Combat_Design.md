# Combat Design

## Formation — DIRECTION (two-ring 16-slot model, not final geometry)
- Four elemental sides arranged as in JC2: **Fire opposite Water; Wind opposite Earth**. Clockwise order (when Fire is at top): Fire → Earth → Water → Wind. This geometry determines adjacent and opposite elements.
- Preserve **shared corners**: a corner monster participates when either adjacent side is chosen.
- Preferred working layout: two concentric rings, each with 8 positions: 4 corners + 4 side centers = 16 total slots.
- Each selected side activates 3 front-row and 3 back-row monsters (shared-corner positions included).
- Front row is first defensive layer. The monster in each lane protects its corresponding rear-row monster; losing one front defender exposes **that lane's** rear monster, not the entire back row.
- Rear row should have valuable, vulnerable roles: high damage, healing, buffs, debuffs. Center rear positions may favor some durability; corner positions can be aggressive. These are incentives, not class locks.
- Special skills may pierce front-row protection or deal splash damage.

## Turn structure — CONFIRMED direction
Player chooses **one elemental side per round**, not commands per monster. Resolve front-row phase first, then rear-row phase. Within each phase, player and enemy row order is determined by **row-specific Speed/initiative**. Example: player front → enemy front → enemy rear → player rear. The three monsters of a row act together as a coordinated sequence to keep battles quick; avoid individual monster cinematic turns.

## Four equipped elemental skills — AGREED (2026-10-08)
- Each monster has **up to two front skills and up to two rear skills** (four total); only its current row's skills can activate.
- Each skill has one elemental identity. Within a single row, two learned skills **must have distinct, adjacent elements**; duplicate-element and opposite-element pairs are not allowed.
- When a side activates: use a skill of the exact selected element if present; otherwise use its **single adjacent-element skill** if present, applying an off-element MP surcharge (amount OPEN). An opposite-element skill is incompatible.
- A monster with only Fire rear skill, for example: Fire activates Fire skill; Wind/Earth activate Fire skill with surcharge; Water uses free basic attack (opposite).
- With Fire + Wind rear skills: Fire → Fire, Wind → Wind, Water → Wind, Earth → Fire. Thus two adjacent-element skills always yield one unambiguous skill for any active side.
- If no compatible skill exists, or the chosen skill cannot be afforded, the monster uses its **free basic attack**. Do not automatically switch to a cheaper skill on MP failure. Basic attack formula and usefulness remain OPEN.
- All skill selection is automatic; no mid-combat player skill choice, priority menu, or manual target designation.

## Offensive targeting — AGREED DIRECTION / OPEN balance
- **Smart automatic targeting**, determined by a move's targeting behavior and potentially formation lane. Player does not choose individual targets or a focus lane.
- Provisional targeting roles: random/general, lane preference, Breaker, Execute (weak-target preference), splash/cleave, penetration. Precise classifications remain OPEN.
- To avoid six Execute skills becoming universally optimal, test **lower base damage, increased MP cost, missing-HP scaling and enemy counters**, rather than hard composition limits.
- Test **same-row target snapshot and simultaneous damage resolution**: row members select targets from one pre-phase state, excess damage does not spill to new targets. These details are provisional and need playtesting.
- No manual focus-fire controls; intended to keep the game fast and emphasize DNA preparation.

## HP, MP, sustain — CONFIRMED direction + OPEN values
- Every monster has its own HP/MP and innate MP growth grade.
- Participating monsters automatically use their compatible equipped row skill when affordable; if no compatible skill is present or MP is insufficient, they use a free basic attack (**agreed fallback**, power/formula OPEN).
- Monsters **not participating** in selected elemental side recover some percentage of maximum MP each round. Shared corners may activate frequently and rest less.
- A dedicated MP-restoring skill / support monster can help sustain frequently used sides.
- Test inactive-only MP recovery first (DIRECTION); rate of 15% per round was an illustrative proposal, **not a locked value**.
- HP healing is primarily via skills/items, rather than the same universal inactive regeneration mechanic (DIRECTION).

## Status & counters — PROPOSALS
Poison (HP damage), Sleep (no acting), Blind (accuracy penalty), Silence (no MP-cost skills), Heal Block (inhibits HP restoration), Mana Burn (drains MP or reduces regeneration). Sleep should probably not erase a defender's physical protection. Piercing, splash, cleave, shields, guard, and heal-disruption counter defensive stall.

## Balance / prototype tests — OPEN
- Speed aggregation for each row (average, highest, weighted, modifiers).
- Test same-row target snapshot / simultaneous damage rather than assuming it is finalized.
- Target-selection heuristics and enemy targeting telegraphs; balancing Execute-heavy builds.
- How dying front units expose rear units later in the same round (current direction: immediately).
- Whether exposed rear attackers can be focused by any enemy lane.
- Damage, defense, Wisdom, resistance, hit chance, shield/player damage formulas.
- Passive trigger order, MP spend/recovery timing, CC duration.
- How arena rotation and sprite facing communicate active sides.
- Verify round time and first-strike damage in playtests.

## Center-lane shields and guild licenses — AGREED 2026-10-08
- **Only the center lane** of the currently selected side can expose the trainer's shields. Both its front-middle and rear-middle monsters must be defeated before ordinary attacks can hit the trainer. Missing corner defenders do not directly open shield access even though a corner is shared by two elements.
- Front-to-rear lane protection applies to **all three lanes**; losing a front defender exposes only the rear monster in that lane. Corner losses can still reduce offense and leave rear corner specialists vulnerable.
- No post-hit immunity/protection window: repeated successful attacks on an exposed trainer may each remove a shield. Exact attack-to-shield rules and encounter balance remain to test.
- **Guild license** controls maximum number of monsters assigned to a formation and maximum trainer shields; higher licenses raise both. Starting at roughly 3–5 monsters and scaling toward 16, and an eventual ~10 shields, are **provisional examples, not fixed tiers**.
- **No placement restrictions:** all 16 positions are available from the start even when license capacity is low. Empty sides and empty middle lanes are permitted strategic choices, with their natural risks.
- Specializing heavily in one element is permitted rather than prevented by composition limits. Weaknesses include low access to other elemental functions, diminished opportunities for inactive MP recovery, and vulnerability when an unprotected side is selected. Playtest whether these costs are sufficient.
- **Shield persistence between dungeon encounters** is the preferred direction agreed for design; recovery facilities, items, and details remain open.
- The basic stat prototype retains HP/MP/ATK/WIS/SPD without dedicated DEF (agreed direction); physical/magical formulas are untested. Full frontline protection with piercing/splash exceptions is the agreed direction.
