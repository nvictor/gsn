# Groove Unified Syntax (GUS)
**Version:** 1.1.0

GUS is a structural rhythm notation system for capturing the rhythmic contour and feel of a groove quickly.

## Model: Captures vs Ignores

| Captures | Ignores |
| :--- | :--- |
| Pulse anchors and gravity | Timbre / Instrumentation |
| Groove contour and timing tension | Exact MIDI/Audio placement |
| Metric tension and syncopation | Dynamics / Velocity |
| Felt grouping and pulse shape | Exact subdivision detail |

## Canonical Syntax

```text
GUS ::= <Pulse> [<PulseShape>] [<Anchor>] [<Syncopation>...]
```

Example: `P4 A↓ S1<`

## Symbol Table

### 1. Pulse (P)

Defines the number of felt groupings in the cycle.

- `P2`, `P3`, `P4`, `P5`, `P6`: Number of perceived main impulses.

### 2. Pulse Shape

Defines the relative span of each pulse when the pulses are uneven.

- `P6[3:3:3:3:2:2]`: 6-pulse feel where the first four pulses are 1.5x the length of the last two.
- *(omitted)*: Pulses have equal or unspecified span.

Pulse-shape ratios describe felt weight, not exact timing math.

### 3. Anchor (A)

Defines where the groove perceives structural gravity.

- `A↓`: Downbeat-anchored (beat 1 dominant).
- `A↑`: Upbeat-anchored (beat 3 dominant).
- `A↔`: Backbeat-anchored (beats 2 and 4 define identity).
- *(omitted)*: Neutral or floating.

### 4. Syncopation (S)

Names the pulse that carries internal tension, displaced articulation, or timing pressure.

- `S2`: Pulse 2 has internal tension or displaced articulation.
- `S1<`: Pulse 1 is anticipated. This often means the next cycle arrives early.
- `S4<`: Pulse 4 itself is anticipated.
- `S2>`: Pulse 2 is delayed.
- `S1< S3 S4>`: Multiple pulse positions are marked.
- *(omitted)*: Clean pulses.

The `<` and `>` marks attach to the pulse they modify. `S1<` and `S4<` are different readings.

## Semantics Rules

- **Structural Priority:** GUS describes what a groove feels like, not where individual hits occur.
- **Pulse Dominance:** The Pulse (`P`) axis is the primary reference for all other modifiers.
- **Positional Syncopation:** Syncopation may name felt pulse positions.
- **Silent Defaults:** Neutral values are omitted by default.
- **Left-to-Right:** Symbols are typically read and processed in the order defined by the syntax.

## Constraints / Invariants

- A GUS expression must contain exactly one Pulse (`P`) definition.
- A pulse-shape ratio must match the pulse count: `P6[3:3:3:3:2:2]` has six ratio values.
- Symbols from different axes cannot be nested.
- Positions refer to felt pulse numbers, not exact beats or subdivisions.
- If a distinction requires exact MIDI/audio placement, it is outside the scope of GUS.

## Live Mode (Shorthand)

Optimized for high-speed capture during listening.

- Omit labels (`P`, `A`) where position is unambiguous.
- Use simple characters: `v` (down), `^` (up), `<` (early), `>` (late).
- Keep syncopation positions attached to `S`.

Example: `4vS1<` is equivalent to `P4 A↓ S1<`.

## Examples

### Straight groove with anticipation

Hit pattern: `1, 2, 3, 4, 4&`

Structural reading:

- 4 main pulses
- Downbeat anchored
- The next cycle is anticipated
- Clean internal structure

GUS:

```text
P4 A↓ S1<
```

### Metal "gallop" groove

Hit pattern: `1, 1&, 1a, 2, 2&, 2a, 3, 3&, 3a, 4, 4&`

Structural reading:

- 4 main pulses
- Downbeat anchored
- The next cycle is anticipated
- Clean internal structure

GUS:

```text
P4 A↓ S1<
```

### Reggaeton groove / "It's My Life"

Hit pattern: `1, 1a, 2&, 3, 3a, 4&`

Structural reading:

- 2 main pulses
- Downbeat anchored
- Pulse 2 carries the internal syncopation

GUS:

```text
P2 A↓ S2
```

### 3-pulse action groove / Basara deshi

Hit pattern: `1, 1&, 2, 2&, 3, 3&, 4, 4&`

Structural reading:

- 3 main pulses: `1`, `2&`, `4`
- Neutral anchor
- The next cycle is anticipated

GUS:

```text
P3 S1<
```

### 6-pulse uneven action groove

Hit pattern: `1, 1a, 2&, 3e, 4, 4&`

Structural reading:

- 6 main pulses
- The first four pulses feel longer than the last two
- Neutral anchor
- Internal friction is carried by the uneven pulse shape

GUS:

```text
P6[3:3:3:3:2:2]
```

## Quick Reference

- `P4`: 4-pulse feel.
- `P6[3:3:3:3:2:2]`: 6-pulse feel with unequal pulse spans.
- `A↓`: Downbeat-anchored.
- `A↑`: Upbeat-anchored.
- `A↔`: Backbeat-anchored.
- `S2`: Pulse 2 is syncopated.
- `S1<`: Pulse 1 arrives early.
- `S2>`: Pulse 2 arrives late.
- `4vS1<`: Live shorthand for `P4 A↓ S1<`.
