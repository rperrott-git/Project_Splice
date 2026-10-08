# Monsters, Capturing, and DNA Splicing

## Acquisition — CONFIRMED
- Players can **capture** monsters. Normal captures are the reliable route to common species and extraction materials.
- **Eggs** are exciting, rarer discoveries, especially important for unusual species forms/variants. Variants could supply distinct looks and genetic possibilities (exact rarity/benefits OPEN).
- The game's term is **splicing**, not Jade Cocoon 2's merging/cocoons.

## Sacrifice / archive — CONFIRMED
- A monster may be permanently sacrificed/extracted to preserve a **reusable DNA specimen template**.
- The template is not consumed by later splices: its DNA may be used an unlimited number of times.
- Archive stores **multiple individual specimens of the same species**, not merely one species unlock.
- Each template preserves that individual monster's innate stat grades and extractable abilities. Individual specimens can be valuable for different reasons.
- This creates a meaningful keep-versus-sacrifice choice, especially with rare egg variants.

## Splicing — CONFIRMED mechanics / OPEN details
1. Choose a living recipient monster (base species identity retained).
2. Choose an archived donor DNA specimen.
3. Choose to inherit **either donor front skill OR donor rear skill** into that row's skill set (**up to two per row, four total**). Each row may contain only two **distinct adjacent elements**, never duplicates or opposite pairs. Replacement is constrained by elemental compatibility, rather than freely choosing any slot.
   - Example: rear Fire + Wind, splice an Earth rear skill ⇒ **Earth replaces Wind** (Wind and Earth are opposites; Fire/Earth are adjacent).
   - If there is only one existing skill, the new skill can fill the open slot if compatible, or replace the incompatible existing skill. Specific UI for this edge case OPEN.
   - Skills are associated with their own element; off-element casting in adjacent sides costs extra MP (amount OPEN). The recipient's innate element does not prohibit inheritance.
4. Receive donor passive ability; support **up to four passives**, with choice of replacement when full.
5. Improve innate stat grades over time with **diminishing returns**.
6. Splicing resets recipient to **level 1** (agreed direction, based on earlier discussion); releveling should not become tedious.

## Grades — CONFIRMED direction
Core exemplar stats: HP, MP, ATK, WIS, SPD; letter grades such as S/A/B/C/D describe innate growth potential. Example: HP S / MP C / ATK A / WIS D / SPD B implies tanky physical attacker. A donor's strong grades should help improve recipient potential over generations, while diminishing returns avoid homogenized all-S monsters.

## Stat refinement formula — PROPOSAL ONLY
Player selects primary stat and minor secondary gains; donor strength affects refinement amount and recipient species biases/caps control diminishing returns. Prior conversations discussed this as a preferred formula, but **the creator has not explicitly finalized how stat targeting should work**. Point values and grade thresholds unspecified.

## Passive example set — PROPOSALS ONLY
Thick Hide (physical reduction), Mana Bloom (more rest MP), Last Stand (low-HP defense), Guardian (reduces penetration against protected rear), etc. These were illustrations, not canonical creature abilities.

## Archive preservation / anti-loop — OPEN
Must specify whether a previously spliced monster's inherited abilities and acquired stat refinements survive extraction. One proposed safeguard: archive only original innate DNA, naturally extractable move/passive and variant identity, not acquired refinements. This safeguard is **not yet agreed upon**; resolve before implementation to prevent self-amplifying loops.

## Additional OPEN decisions
- What exact passive(s) donors transfer when possessing several acquired passives?
- Is the donor's passive fixed by native genetics, selected from its currently equipped four, or another mechanism?
- Evolution triggers, branching/evolution appearances, and their stat effects.
- Level cap, EXP catch-up, fusion/splicing costs, conservation of progression.
- DNA archive UI filtering/favorites/comparisons and duplicate workflows.
- Whether rare variants have exclusive skills/passives, altered grades, or primarily cosmetics.
- Species-specific soft caps and whether heavily spliced stats can reach S.

## Principle
A favorite early monster should be a viable long-term investment through thoughtful splicing, while species specialization and finite skills/passive slots preserve choices. A monster can hold two skills per row (adjacent elements only), with deterministic skill use when an elemental side activates.

## Guaranteed post-battle recruitment — AGREED 2026-10-08
- In a wild battle (a single enemy side, at most six enemy monsters), defeat the enemy group and **select one of the defeated monsters to recruit with guaranteed success**.
- No individual midcombat capture action, capture chance roll, rare-species hard lock, or need to keep a chosen target alive for recruitment.
- Newly recruited monsters remain unsecured until a safe return to town; failure risks expedition discoveries, not previously banked monsters.
- Boss progression upgrades the protagonist's **rare-monster attraction**, enriching wild encounter pools with rarer species, stronger species, and unusual variants of existing ones. No species must become unobtainable due to upgrading attraction.
- Species rarity, variant rarity, and individual innate genetic quality are distinct concepts. Powerful or unusual donors can still arise from familiar species.
- Specific rare egg exclusivity, attraction rates, recruitment choice UX and specimen preview are OPEN.

## Evolution and generational progression — AGREED DIRECTION (2026-10-08)
- Each monster family is intended to have **2–3 major evolutionary transformations** (some variation by family is possible). Later transformations become progressively harder and are major accomplishments, rather than frequent level-only events.
- **Evolution happens during a splice**, never unexpectedly in the dungeon. Evolution is permanent: an evolved monster remains in its evolved form when later splices reset it to level 1.
- **Extraction has no level requirement.** The living recipient must reach a **consistent minimum level before each splice**; exact level/cap remain OPEN. Every splice resets the recipient to level 1.
- Every splice adds to a **visible evolution progress meter**. Donor evolutionary stage/genetic complexity, genetic compatibility (possibly elemental or species-related), and exceptional genetics can affect the gain. All values/formula and definition of compatibility are OPEN.
- Evolution progress thresholds increase for later stages. Evolution can improve innate growth grades, so subsequent level-1-to-cap training uses better growth potential. Evolution and acquired DNA stat refinement must combine transparently without silently wasting previous investment; formula OPEN.
- Some monster families may have **limited evolution branches**. Player chooses among unlocked forms; standard branches should be intuitive, while advanced requirements may depend on developed genetics. Avoid opaque checklists and excessive sprite production.
- A splice can simultaneously grant an active skill, passive, refinement and evolution progress, potentially triggering evolution. Balance donor tradeoffs and XP/cost requirements so quantity alone does not dominate.
- **Repeated reuse of the same archived DNA template has no diminishing returns initially**, pending balance testing. An optional future lever is a transparent diversity bonus or repetition penalty, but neither is currently adopted.
- **Extraction inheritance model remains OPEN.** Compare (A) natural/evolved genetics only, (B) complete developed traits/refinements, and (C) story-unlocked progressive extraction. Do not treat any as the settled system; prototype before selecting. Preserve meaningful rewards for sacrificing developed specimens while watching for recursive donor amplification.
- Generation-count milestones and displayed numerical thresholds discussed earlier were examples, **not approved requirements**. The evolution meter, rather than a mandatory number of splices, is the current design direction.
