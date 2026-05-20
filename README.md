# Groove Unified Syntax (GUS)
**Version:** 1.1.0

GUS is a compact notation for describing the felt structure of a groove.

It captures pulse count, pulse shape, anchor, and syncopation. It does not capture instrumentation, dynamics, exact subdivisions, or exact MIDI/audio placement.

## Syntax

```text
GUS ::= <Pulse> [<PulseShape>] [<Anchor>] [<Syncopation>...]
```

Example:

```text
P4 A↓ S1<
```

## Symbols

### Pulse

Use `P` to name the number of felt pulses in the cycle.

- `P2`, `P3`, `P4`, `P5`, `P6`, `P8`

### Pulse Shape

Add a ratio when the pulses have uneven felt spans.

```text
P6[3:3:3:3:2:2]
```

The ratio values must match the pulse count. Ratios describe felt weight, not exact timing.

### Anchor

Use `A` to name the groove's structural gravity.

- `A↓`: Downbeat-anchored.
- `A↑`: Upbeat-anchored.
- `A↔`: Backbeat-anchored.
- Omit `A` for neutral or floating grooves.

### Syncopation

Use `S` to name the pulse that carries tension, displacement, or timing pressure.

```text
S<position><timing?>
S(<positions>)<timing?>
```

- `S2`: Pulse 2 is syncopated.
- `S1<`: Pulse 1 arrives early.
- `S4<`: Pulse 4 arrives early.
- `S2>`: Pulse 2 arrives late.
- `S2<>`: Pulse 2 has both early and late tension.
- `S(2,3,4,1)<`: Grouped form for `S2< S3< S4< S1<`.
- `S(2,4)<>`: Grouped form for `S2<> S4<>`.

`<` and `>` attach to the pulse they modify. Grouped positions keep their written order, so `S(2,3,4,1)<` is not the same reading as `S(1,2,3,4)<`.

## Rules

- A GUS expression must contain exactly one `P` token.
- Positions refer to felt pulse numbers, not exact beats or subdivisions.
- Symbols from different axes cannot be nested.
- Omit neutral values by default.
- Read tokens left to right.

## Live Shorthand

Use shorthand for fast capture while listening.

- `v`: `A↓`
- `^`: `A↑`
- `<`: early
- `>`: late

Example:

```text
4vS1< = P4 A↓ S1<
```

## Examples

### Straight groove with anticipation

Hit pattern: `1, 2, 3, 4, 4&`

```text
P4 A↓ S1<
```

### Metal "gallop" groove

Hit pattern: `1, 1&, 1a, 2, 2&, 2a, 3, 3&, 3a, 4, 4&`

```text
P8 A↓ S(2,3,4,1)<
```

### Reggaeton groove / "It's My Life"

Hit pattern: `1, 1a, 2&, 3, 3a, 4&`

```text
P4 A↓ S2<> S4<>
```

### 8-pulse action groove / Basara deshi

Hit pattern: `1, 1&, 2, 2&, 3, 3&, 4, 4&`

```text
P8 A↓
```

### 6-pulse uneven action groove

Hit pattern: `1, 1a, 2&, 3e, 4, 4&`

```text
P6[3:3:3:3:2:2] A↓
```
