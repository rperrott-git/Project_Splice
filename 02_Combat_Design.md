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

## Skill rank and independent abilities — AGREED 2026-10-08
- Every skill rank is a **distinct active move**, not an automatic upgrade of a family. Replacing a cheaper move with a higher-ranked one is a conscious donor/inheritance tradeoff.
- Higher-ranked skills generally offer more immediate power or unique effects for substantially higher MP costs; inexpensive lower-ranked abilities remain desirable for expedition endurance. Exact rank bands, MP costs and damage formulas are OPEN.
- **ATK-scaling and WIS-scaling skills exist in both front and rear rows across all four elements**; element defines tactical emphasis rather than forbidding offensive or physical roles. Water retains real offensive abilities, alongside restoration.
- Each element has characteristic tactical effects (Fire offense, Water restoration, Wind disruption, Earth defense/buffs), but should not be restricted to those effects exclusively.
- Skill **rank** (potency/expense) and **rarity** (acquisition difficulty) are distinct. Unusual effects such as percentage-HP damage, Execute or special area interactions may be separate ranked moves, not necessarily direct upgrades of basic attacks.
- Keep the existing one-active-skill-per-row-action, deterministic elemental selection and no individual battle commands. Skill library names/values and rank distribution are still to design.

## Sequential actions within each row — AGREED 2026-10-08 (supersedes snapshot proposal)
- The two teams' **front rows resolve before the two rear rows**. For each row tier, compare row-specific initiative to decide which team's three-monster group acts first.
- **Within an acting row, individual living monsters act in descending SPD order**, not fixed left-to-right. Ties require a deterministic tie-breaker (OPEN).
- Each monster selects its target **immediately before its own action**, using that skill's defined automatic targeting behavior and the current battlefield state. Apply damage, healing, statuses, KOs and other effects immediately before the next monster acts.
- A defender defeated by the second action disappears at once; the third action may target its newly exposed rear partner. If both center-lane defenders fall, subsequent eligible attacks may damage the trainer's shields **within the same row phase**, with no artificial shield-invulnerability period.
- Row actions should appear as one brisk coordinated sequence (quick successive motions), **not** twelve long individual cinematic turns.
- The previous proposal to take one targeting snapshot for a whole row and simultaneously apply damage is **rejected for the first prototype**. Rebalance Execute skill power/MP if sequential retargeting makes it too dominant. Sequential healing naturally accounts for previously applied heals.
- **Automatic targeting is skill-specific** (e.g. general/random, lane preference, Execute, penetration, splash); no manual target selection. Exact target heuristics, row-Speed aggregation, SPD tie handling and specific ability values remain OPEN.

## Prototype status-effect rules — AGREED framework (2026-10-08)
This section is the current source of truth for statuses, superseding earlier status brainstorming where it conflicts.

**Shared rules**
- Six initial statuses: Poison, Blind, Silence, Sleep, Heal Block, Mana Burn.
- Ongoing status damage, resource loss and duration progress **once per complete combat round**, not on every row action. Effects persist even if the affected monster's elemental side is not active.
- A successful repeat application of the same status **refreshes its duration and effect**; it never stacks multiple instances of itself. Different statuses **may coexist**, including overlapping or strategically redundant ones (e.g. Blind with Sleep). Players decide whether combinations are useful.
- Status application and immediate effects happen when the individual skill resolves, within sequential SPD-sorted row actions. Incapacitated monsters still physically occupy formation slots and protect their rear partner.
- Specific hit chances, durations, debuff percentages, cleanse effects, resistance and boss adjustments remain **PROVISIONAL** until tested.

**Six statuses**
| Status | Core behavior | Balancing intention |
|---|---|---|
| Poison | Deals a percentage of **target maximum HP** at end of each full round | Valuable against high-HP tanks; example 5%/round only |
| Blind | Reduces accuracy of accuracy-dependent offensive abilities | Cheaper, more reliable, longer lasting than hard control; example 40–50% accuracy penalty only |
| Silence | Prevents MP-consuming skill use; monster falls back to its free basic attack | Counters heals, casters and expensive skills without removing all actions |
| Sleep | Cannot act while asleep; remains in formation protecting its lane. **First direct damaging hit is a guaranteed critical and wakes target immediately** | Either control or burst setup; applies to single-target, cleave, splash and piercing direct hits. Poison/other damage-over-time ticks **neither wake nor consume** the critical. Example crit modifier 1.5x only |
| Heal Block | Greatly reduces incoming HP restoration, including healing, regeneration and lifesteal/drains when applicable | Counter to Water sustain rather than full denial; example **75% reduction** only |
| Mana Burn | Drains a percentage of target maximum MP at end of each full round | Counter to Water/MP sustain and costly skill builds; example **10% max MP** only; passive/resting regen may still occur, with net effect determined by timing |

**Tactical goals / balance cautions**
- Blind should remain useful relative to Sleep and Silence via low MP cost, reliability, duration and/or damage-bearing application moves.
- Sleep's guaranteed wake-up critical on **any direct damaging hit** creates a meaningful choice between preserving control and cashing out burst. Whether a sleeping unit awakened by an earlier attack still gets its already-pending action needs explicit testing/specification.
- Reapplication refreshes, not stacks. Poison vs large bosses and repeated Sleep against bosses require resistance tuning rather than assumed blanket immunity.
- Heal Block and Mana Burn give Wind/disruption builds ways to pressure Water's healing and MP recovery; cleansing abilities may give Water counterplay.
- Initial status move candidates include Venom Fang, Dark/Blinding Gust, Sleeping Mist, and future dedicated Heal Block and Mana Burn moves. **Skill ranks, names, costs, exact targeting, and effect quantities not locked.**
