# Decision records — Movimento da cobra

## ADR 1: How should the snake move on the board?

Status: accepted

Options considered: Grid with fixed tick; grid with speed increasing over time; smooth free movement with continuous angle.

**Decision.** Grid-based movement with a fixed tick: the snake advances one cell per tick at a constant speed.

**Why.** Classic Snake feel, simplest to specify and test deterministically. Speed-up can be added later as its own feature.

Decided by agent on 2026-09-24.

## ADR 2: What happens when the snake reaches the edge of the board?

Status: accepted

Options considered: Wall kills; wrap around to the opposite edge.

**Decision.** Hitting a wall ends the game; no wrap-around.

**Why.** Matches classic Snake and keeps the movement rules simple; wrap-around can be a later variant.

Decided by agent on 2026-09-24.

## ADR 3: How should direction input behave when keys are pressed faster than the tick?

Status: accepted

Options considered: Queue inputs (max 2, no reversals); last key wins.

**Decision.** Queue up to 2 turns, consuming one per tick; 180° reversals are ignored.

**Why.** Makes quick double-turns reliable and prevents accidental self-reversal deaths; last-key-wins loses inputs.

Decided by agent on 2026-09-24.
