# Decision Log
Initial checkpoint: 2026-10-08. 'Agreed' means direct user selection or explicit assent; 'Working' means favored, not final.

| Area | Decision | Status | Rationale / caveat |
|---|---|---|---|
| Combat | Select a whole elemental side | Agreed | JC2 pace and strategic team setup |
| Combat | Keep shared corners | Agreed | Adjacent side synergy |
| Combat | Add front and rear rows | Agreed direction | Defensive layers, vulnerable high-value casters |
| Combat | 16 slots, 2x8 concentric rings | Working | Geometry not final |
| Combat | Row-specific initiative; front phase then rear phase | Agreed | Fast coordinated actions without 12 separate turns |
| Combat | Front lane protects corresponding rear lane | Agreed | Tactical breakthroughs |
| Combat | Automatic smart skill targeting | Agreed direction | No individual commands |
| Combat | Individual MP; resting inactive monsters recover MP | Agreed | Incentivize elemental rotation |
| Genetics | Capture monsters, rare eggs for exciting variations | Agreed | Distinct acquisition purposes |
| Genetics | Sacrifice for reusable donor DNA archive | Agreed | Permanent collecting progression and moral mirror |
| Genetics | Multiple DNA specimens per species | Agreed | Individual specimen diversity matters |
| Combat / Genetics | Up to two front and two rear elemental skills per monster | Agreed 2026-10-08 | Four total slots; one matching/compatible skill automatically activated per row |
| Combat | Same-row skills must have distinct adjacent elements | Agreed 2026-10-08 | No duplicate or opposite elemental pairs; deterministic selection |
| Combat | Fire opposite Water; Wind opposite Earth | Agreed 2026-10-08 | JC2-inspired cardinal arrangement; Fire top, Earth right, Water bottom, Wind left (illustrative orientation) |
| Combat | Exact match first; otherwise adjacent skill with MP surcharge | Agreed, penalty OPEN | Opposite skill cannot cast; avoids player selecting specific skills |
| Combat | No skill match or insufficient MP triggers free basic attack | Agreed 2026-10-08 | Even one-element monsters remain usable; basic attack power OPEN |
| Combat | Automatic skill targeting, no manual focus | Agreed direction | Keeps turns quick; ability-defined targeting roles |
| Combat | Execute balancing via opportunity cost | Working / test | Lower power, MP cost, counters, simultaneous row resolution; values not final |
| Genetics | Choose donor front OR rear skill in a splice | Agreed | Replaces incompatible same-row skill as needed, e.g. Fire/Wind + Earth rear replaces Wind |
| Genetics | Donor passive gained; four passive slots | Agreed | Limited build capacity |
| Genetics | Innate growth grades improve with diminishing returns | Agreed | Long-term investment, preserve species identity |
| Genetics | Splicing resets recipient to level 1 | Agreed direction | Generational growth; catch-up needed |
| Platform | Full PC and Android game | Agreed 2026-10-08 | Shared gameplay; touch and mouse/controller UX from the start; Godot suggested |
| World | Familiar elemental regions, variable encounters/routes | Agreed | Replayability plus sense of place |
| World | Collection/optimization is main replayability priority | Agreed | Dungeons support builds |
| Art | Low-res original pixels and 2.5D cutout presentation | Agreed direction | Creative ownership and solo scope |
| Story | Friendly AI is protagonist's only true ally | Agreed | Emotional attachment |
| Story | AI wants to splice protagonist to create compatible humanity | Agreed | Tragic, non-cartoon villain |
| Story | Player must confront machine-led catastrophe | Agreed direction | Consequences of guardian quest |
| Story | Final elemental guardian unlocks **Human Splicing** as the expected machine-upgrade reward | Agreed | Familiar victory reward becomes the tonal pivot |
| Story | AI says the child changed its belief that coexistence was impossible and senses a unique passive trait | Agreed | Reveals love and extraction plan in the language of monster splicing |

## Most important open decisions
1. Actual geometry / screen readability and team sizes.
2. Battle targeting/damage order, row speed calculation, MP recovery rates and status timing.
3. Donor archive extraction rules for artificially inherited traits; possible exploit loops.
4. Stat refinement formula, level/evolution curve, splice costs and catch-up EXP.
5. Procedural dungeon design constraints and cost.
6. Art pipeline and final engine selection (Godot 4 recommended); PC/Android interface and save/resume implementation.
7. Full plot logic, protagonist identity, exact AI arc, finale.

## Addendum — 2026-10-08: shields, formation freedom, narrative mirror
| Area | Decision | Status | Rationale / caveat |
|---|---|---|---|
| Combat | Only fully collapsed **middle** front+rear lane exposes trainer shields | Agreed | Shared corners cannot make two elemental sides automatically fatal |
| Combat | No temporary immunity after shield damage | Agreed | Balance with shield pool, not artificial hit caps |
| Combat | Guild license raises monster capacity **and** maximum shields | Agreed | Scale survivability with combat roster |
| Combat | All formation positions available from first license | Agreed | Empty sides and concentrated builds are valid player choices |
| Combat | Early ~3–5 monsters; eventual ~10 shields | Working numbers | Tune in prototype; no committed tier table |
| Combat | No dedicated DEF stat; layered protection with piercing/splash exceptions | Agreed direction | Keep stats simple, distinguish defensive skills |
| Dungeon | Persistent trainer shields during expedition | Agreed direction | Sustained dungeon resource, restoration methods open |
| Story | AI trains child in parallel with child training monsters, concealed until Human Splicing | Agreed | Reframes sincere encouragement rather than villainizing it |

## Addendum — 2026-10-08: reconstruction and expedition risk
| Area | Decision | Status | Rationale / caveat |
|---|---|---|---|
| Story | AI openly offers limited machine-to-human splice early; child knowingly accepts | Agreed | Sincere protection, foreshadows final Human Splicing without deception |
| Story / Gameplay | Save State operates through biological reconstruction rather than time reversal | Agreed direction | Explains recovery and raises identity questions; technical limitations open |
| Gameplay | Early enhancement supplies Recall outside combat | Agreed | Safe return with all collected expedition rewards |
| Dungeon | Rare eggs and unsecured expedition loot risk loss on defeat | Agreed | Push-your-luck exploration; exact penalty open |
| Dungeon | Voluntary retreat outside combat retains all earned rewards | Agreed | Player controls expedition risk |
| Story | Early human augmentation is limited; final guardian unlocks full Human Splicing | Agreed | Prevents contradiction and strengthens tonal pivot |
| Gameplay | Save-and-quit is independent of diegetic reconstruction | Design requirement | Mobile interruption must not count as defeat |
| Open | After-betrayal Failsafe access, capture security, reconstruction details | Unresolved | Need future decisions |

## Addendum — 2026-10-08: wild recruitment and attraction
| Area | Decision | Status | Rationale / caveat |
|---|---|---|---|
| Combat | Wild battles use one enemy side, up to six enemies, victory by defeating the group | Agreed | Distinct from shield-based trainer battles |
| Combat | KO removes monster from live fight; KO slot remains assigned at 0 HP afterward | Agreed | Clear gaps; formation can be rearranged freely between fights |
| Collection | Choose exactly one defeated wild monster after victory; recruitment guaranteed | Agreed | No capture RNG or interruption of fast automatic combat |
| Dungeon | Fresh captures and rare eggs are unsecured until safely recalled | Agreed | Meaningful risk/reward for deep expeditions; exact loss rule open |
| Dungeon | Recall outside combat banks all expedition discoveries | Agreed | Retreat at any time, floor transitions may prompt choice |
| Progression | Bosses grant AI-linked rare monster attraction, unlocking uncommon forms and stronger species in encounter pools | Agreed direction | Expand encounter possibilities rather than raise capture odds |
| Collection | Preserve availability of common species as new encounters unlock | Agreed direction | Maintain reliable access to targeted DNA donors |
| Open | Loot-loss percentage, rare attraction rates, bait/scouting, exact variants/egg exclusivity | Unresolved | Requires design and playtests |

## Addendum — 2026-10-08: evolution and DNA inheritance
| Area | Decision | Status | Rationale / caveat |
|---|---|---|---|
| Progression | 2–3 major evolutions per monster family, increasingly demanding | Agreed direction | Meaningful long-term milestones; scope and counts may vary by family |
| Progression | Evolution triggered during splicing; evolved form persists at level 1 afterward | Agreed | Evolution improves subsequent level-up growth |
| Progression | Extraction has no minimum level; every splice has a consistent minimum level requirement | Agreed | Simple raising cycle; exact threshold open |
| Progression | Visible evolution meter increases from each splice | Agreed direction | Intuitive progress and donor comparisons |
| Progression | More evolved/complex and compatible donor DNA generally raises meter faster | Agreed direction | Reward exceptional archived specimens; exact formula open |
| Progression | Evolved forms can improve innate stat growth grades | Agreed | The new level-1 monster grows stronger per level |
| Progression | Limited branching evolution; player selects unlocked forms | Agreed direction | Customization without mandatory opaque requirements |
| DNA | No diminishing returns for reusing the same DNA donor initially | Agreed prototype rule | Leave as balancing lever for later |
| DNA | What acquired refinements, skills, and passives survive extraction | OPEN | Compare natural-only, full, and progressive story-unlocked inheritance experimentally |
| Open | Evolution thresholds, donor compatibility, base growth math, level/EXP economy | Unresolved | Define and simulate next |

## Addendum — 2026-10-08: numerical stats and XP loop
| Area | Decision | Status | Rationale / caveat |
|---|---|---|---|
| Stats | Hidden numerical growth potential within visible D/C/B/A/S bands | Agreed direction | Small gains even before grade changes; AI reveals analysis gradually |
| Stats | Grade affects modest level-1 baseline and per-level growth | Agreed direction | Early stat differences small, developed growth meaningful |
| Stats | Moderate grade differentiation; skills/passives remain at least as important | Agreed balance target | Avoid all-S homogenization |
| DNA | Every splice gives small nonnegative automatic potential gains to all five stats, based on donor strengths | Agreed | Donor choice is primary decision, not manual stat assignment |
| DNA | No species-specific absorption multipliers initially | Agreed prototype rule | Minimize opacity; use donor quality and diminishing recipient gains |
| Evolution | Fixed, branch-specific potential bonuses | Agreed | Distinct evolved forms and predictable improvements |
| XP | Full shared XP to all living formation monsters regardless of participation; no splitting | Agreed | Sixteen-monster management should remain practical |
| XP | No XP to knocked-out or stored monsters | Agreed | Must be active in equipped formation and alive |
| XP | No low-level catch-up XP | Agreed | Leveling between splices should take meaningful time |
| Splicing | Hub-only, reset to level 1 with full HP/MP at new maxima | Agreed | No mid-dungeon splicing or extra healing chore |
| Recovery | Hub return heals and revives monsters automatically | Agreed | Expedition endurance remains separate |
| XP | Modest evolutionary-stage XP scaling, not per-generation scaling | Working direction | Test expedition minutes before committing multipliers |
| Open | Level cap, XP curve, minimum splice level, benefit of extra levels, grade boundaries and refinement formula | Unresolved | Next design and simulation work |

## Addendum — 2026-10-08: initial progression test targets
| Area | Decision | Status | Rationale / caveat |
|---|---|---|---|
| Levels | Max 20; splice eligibility at level 15 | Working agreed test values | Revisit after modeling expeditions |
| Levels | 16–20 grant greater **current combat stat** gains (test 1.5–2x) | Agreed direction; magnitude OPEN | Keep-level-20 vs splice-at-15 choice |
| Splicing | No permanent refinement bonus for waiting past level 15 | Agreed direction | Avoid forcing max level before each splice |
| XP | Level 20 XP stops initially | Working | No prestige/overflow XP system |
| Pacing | Around two challenging suitable expeditions to level 15 | Agreed target | Real-time pace, not exact encounter count |
| Next | Test full numerical progression before final formulas | Agreed plan | Tune XP scaling, stat potential, evolution bonuses |

## Addendum — 2026-10-08: revised final act and Failsafe ending
| Area | Decision | Status | Rationale / caveat |
|---|---|---|---|
| Story | First post-reveal battle against AI creations derived from the genetic archive/party | Agreed direction | Personalizes the betrayal; not a mandatory exact mirror match |
| Story | AI loses confrontation and withdraws to machine-occupied capital | Agreed direction | Escalates quest and gives AI an emotionally wounded departure |
| Story / Hub | Original lab remains playable hub, but without AI voice | Agreed | Preserve systems, emphasize loss; supersedes spy/shelter relocation proposal |
| Story | AI seeks further human samples and stronger means to restrain/extract child | Agreed direction | Forced human splicing motive; other humans also viable materials |
| Failsafe | Automatic terminal disassembly of compromised body; biological reconstruction at lab | Agreed direction | Denies captors the original body; alluded to non-graphically |
| Failsafe | AI cannot cancel Failsafe triggering, but can remotely disable reconstruction | Agreed | Establishes meaningful final choice |
| Ending | Only after last battle AI discloses that it could have permanently prevented reconstruction but never did | Agreed | Love despite strategic cost; don't reveal or foreshadow explicitly earlier |
| Story | Child might be a war orphan | Possible / OPEN | Evocative backstory, not yet confirmed |
| Postgame | Advanced elemental revisits + trainer gauntlet + small optional challenges | Direction / scope OPEN | Hybrid reuse of assets and collection-oriented longevity |

## Addendum — 2026-10-08: ambiguous epilogue
| Area | Decision | Status | Rationale / caveat |
|---|---|---|---|
| Ending | Child chooses to recreate an AI after defeating the original | Agreed | Mirrors AI's attempt to redesign humanity |
| Ending | Never identify the traits the child changed or removed | Agreed | Keep autonomy, identity, and repeating-the-cycle interpretations open |
| Ending / Postgame | Familiar AI presence returns; old laboratory becomes warm and lively again | Agreed direction | Emotionally comforting ending and functional postgame hub |
| Ending | No forced ominous reveal or explanation of whether recreated AI is the original | Agreed | Ambiguity emerges through reflection, not a horror sting |

## Addendum — 2026-10-08: skill framework
| Area | Decision | Status | Rationale / caveat |
|---|---|---|---|
| Skills | Different ranks are independent moves, not automatic upgrades | Agreed | Low-MP abilities can remain valuable despite higher-rank donors |
| Skills | Greater rank generally increases power/effect at higher MP costs | Agreed direction | Exact rank/efficiency curve OPEN |
| Skills | All four elements and both rows can use ATK- or WIS-scaling abilities | Agreed | Support physical glass cannons, mages and hybrid builds |
| Skills | Rank and rarity are separate | Agreed direction | Unique effects need not be a linear upgrade |
| DNA | Every splice requires inheritance of donor front OR rear active skill | Agreed | Preserves meaningful tradeoff; future frustration testing needed |
| Next | Define 20–24 prototype skills with element, row, stat scaling, rank, targeting and MP cost | Planned | Proposals only until reviewed |
