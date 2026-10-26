# Mario and Luigi: Bowser's Inside Story — Manual for Archipelago

## Logic model

- Physical checks (beanholes, blocks, and rewards) are assigned to an area region in `locations.json`. Their local `requires` is empty unless the check has its own explicit collection threshold; the area's story gate is applied by `regions.json`.
- Story milestones and unlocks are represented as events in `events.json`, not item-bearing locations. Events are progression flags used by region requirements and later events.
- `Opening` is a location-free starting region. It grants the opening Bowser battle event, which opens the early castle/Bowser route. The story then branches into Bowser's overworld and the Bros' path inside Bowser before converging around Toad Town.
- Star Cure events form a dependency chain: Wisdurm / first cure, Fawful Express / second cure, Chakron / third cure, Miracle Cure, endgame barrier and final boss sequence.
- Attack Piece completion events require the ten pieces for their corresponding attack. Mushroom Ball reward thresholds require the corresponding number of `Mushroom Ball` items.

## Known logic limitations

This is an area-level first pass based on the supplied location names and published story progression. The existing check list does not identify every room or movement-gated sub-area, so broad regions such as Peach's Castle and Cavi Cape can still include checks from more than one story phase. This does not model movement abilities as randomized items, because the current item pool does not define those abilities. Test the generated Manual world and refine any route that appears too early or is unreachable.
