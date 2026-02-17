# Groove Unified Syntax (GUS)
**Version:** 1.0.0

GUS is a structural rhythm notation system for capturing the rhythmic contour and "feel" of a groove quickly.

## Model: Captures vs Ignores

| Captures | Ignores |
| :--- | :--- |
| Pulse anchors (gravity) | Timbre / Instrumentation |
| Groove contour (push/drag) | Exact MIDI/Audio placement |
| Metric tension (syncopation) | Dynamics / Velocity |
| Felt grouping | Subdivision details (e.g., 16th vs 32nd) |

## Canonical Syntax

```text
GUS ::= <Pulse> [<Anchor>] [<Syncopation>] [<Cadence>]
```

Example: `P4 A↓ S C<`

## Symbol Table

### 1. Pulse (P)
Defines the number of felt groupings in the measure.
- `P2`, `P3`, `P4`, `P5`: Number of perceived main impulses.

### 2. Anchor (A)
Defines where the groove perceives structural gravity.
- `A↓`: Downbeat-anchored (beat 1 dominant).
- `A↑`: Upbeat-anchored.
- `A↔`: Backbeat-anchored (beats 2 & 4 define identity).
- *(omitted)*: Neutral or floating.

### 3. Syncopation (S)
Describes internal conflict within the pulse groups.
- `S`: Syncopated pulses. Contains complex internal articulation or friction.
- *(omitted)*: Clean pulses.

### 4. Cadence (C)
Describes how pulses relate to one another temporally.
- `C<`: Anticipatory (Push). Pulses tend to arrive early.
- `C>`: Delayed (Drag). Pulses sit behind the beat.
- `C<>`: Mixed.
- *(omitted)*: On-beat resolution.

## Semantics Rules

- **Structural Priority:** GUS describes what a groove *feels like*, not where individual hits occur.
- **Pulse Dominance:** The Pulse (`P`) axis is the primary reference for all other modifiers.
- **Silent Defaults:** Neutral values (no specific anchor, clean pulses, on-beat resolution) are omitted by default.
- **Left-to-Right:** Symbols are typically read and processed in the order defined by the syntax.

## Constraints / Invariants

- A GUS expression must contain exactly one Pulse (`P`) definition.
- Symbols from different axes cannot be nested.
- If a distinction requires counting specific subdivisions, it is outside the scope of GUS.
- No symbol may encode absolute hit positions.

## Live Mode (Shorthand)

Optimized for high-speed capture during listening.

- Omit labels (`P`, `A`, `C`) where position is unambiguous.
- Use simple characters: `v` (down), `^` (up), `<` (push), `>` (drag).

Example: `4vS<` is equivalent to `P4 A↓ S C<`.

---

See [EXAMPLES.md](./EXAMPLES.md) for usage and [CHEATSHEET.md](./CHEATSHEET.md) for a quick reference.
