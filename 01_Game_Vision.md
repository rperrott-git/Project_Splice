# Game Vision

## Pitch — CONFIRMED direction
An original monster-collecting dungeon crawler inspired mechanically by *Jade Cocoon 2*, centered on four-sided elemental formation combat and permanent genetic splicing progression. Low-resolution hand-drawn monster sprites appear in a stylized 2.5D world. The seemingly helpful AI companion becomes the emotional and moral heart of a post-AI-catastrophe story.

## Design pillars — CONFIRMED / DIRECTION
- **Fast, tactical combat:** choose one elemental side, not commands for every monster; coordinated row animations resolve quickly.
- **Deep experimentation:** customize favorite monsters over generations with donor DNA, four elemental active-skill slots (two front, two rear), passives, and innate-stat refinement.
- **Meaningful collecting:** capture standard monsters; discover special eggs and variants; each extraction expands a reusable genetic archive.
- **Replayable exploration:** recognizable elemental regions, with variable routes and encounters; rewards feed the monster-building loop.
- **An emotionally consequential story:** companion AI earns player trust; genetic extraction raises questions about consent and personhood.
- **Solo-developer realistic art:** leverage creator's chunky low-resolution pixel sprites rather than requiring many 3D creature models.

## Main loop — DIRECTION
Hub/preparation → expedition into elemental region → formation battles & exploration → capture monsters / discover eggs & resources → return → extract selected creatures into permanent DNA templates → splice, rebuild formation, relevel, repeat.

## Known target feel
Monster optimization and collecting are the **primary** replayability motivators; randomized maps are a supporting system rather than the main attraction.

## Scope guardrails — PROPOSAL
First prototype: battle sandbox with placeholder creatures; next: splice preview; then one small replayable dungeon. Do not commit to 100+ monsters, full story, or all elemental biomes before combat and progression are fun.

## Open
Exact control layout, engine implementation details, roster size, length, accessibility, pricing, production timeline, final name. **Confirmed platforms: full game on Windows PC and Android**; Godot 4/GDScript is the current recommended engine (not yet formally committed). Plan shared gameplay logic, landscape mobile interface, touch controls, offline play and interruption-friendly saving. Steam Deck/Linux support is an optional future goal.

## License-based formation growth — AGREED 2026-10-08
Guild licenses increase the number of monsters the protagonist can command **and** maximum trainer shields. All 16 formation positions remain available at every license tier; choosing to concentrate creatures on only one or two sides is permitted. Examples of 3–5 starting monsters and ~10 shields at mastery are balance hypotheses, not final values. Deeper dungeons should naturally challenge single-element burst strategies through MP exhaustion, limited healing, and exposure from empty sides.

## Monster development direction — 2026-10-08
Long-term development uses a **visible evolution meter filled by splicing**, where more evolved/genetically compatible DNA generally advances progress faster. Monsters undergo around 2–3 increasingly significant evolutions, chosen during a splice; new evolved forms persist across subsequent level resets and can improve innate stat-growth grades. Extraction has no minimum level; recipients must meet a consistent minimum level to splice. Preserve unrestricted reusable archive DNA for initial tests; exact inheritance of acquired traits from extracted developed monsters remains deliberately undecided.
