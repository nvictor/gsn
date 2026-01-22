# Groove Structure Notation (GSN)

GSN is a structural rhythm notation system. It is a compact symbolic system that describes what a groove does, not where individual hits occur. The system intentionally avoids encoding subdivisions, counts, or hit positions.

## Design Principles

1. **Structure over events**  
   GSN encodes rhythmic behavior, not note placement.

2. **Subdivision-agnostic**  
   No symbol may imply `e`, `&`, or `a`-level timing.

3. **Silent defaults**  
   Neutral values are omitted unless explicitly violated.

4. **Composable axes**  
   Each symbol describes an independent structural dimension.

## Core Axes

### 1. Grid (G)

Defines the structural pulse density.

- `G4`  - quarter-note grid
- `G8`  - eighth-note grid
- `G16` - sixteenth-note grid

Grid does not imply swing or subdivision usage-only resolution potential.

### 2. Anchor (A)

Defines where the groove perceives structural gravity.

- `A↓` - downbeat-anchored (beat 1 dominant)
- `A↑` - upbeat-anchored
- `A↔` - backbeat-anchored (beats 2 & 4 define identity)
- `A=` - neutral, floating, no anchor

### 3. Syncopation (S)

Describes sustained conflict with the anchor, not isolated off-grid hits.

- (omitted) - anchor-aligned behavior
- `S+` - persistent anchor opposition

Syncopation is behavioral, not positional.

### 4. Cadence (C)

Describes where structural resolution occurs relative to the anchor reset.

- (omitted) - resolves on the anchor
- `C<` - anticipatory cadence (resolves before anchor)
- `C>` - delayed cadence (resolves after anchor)
- `C<>` - both anticipatory and delayed cadence

## Examples

### Example 1: Straight groove with anticipation

Hit pattern:

```
1, 2, 3, 4, 4&
```

Structural reading:
- Quarter-note grid
- Downbeat anchored
- Anticipatory resolution
- No sustained syncopation

GSN:

```
G4  A↓  C<
```

### Example 2: Dense syncopated groove with anticipation

Hit pattern:

```
1, 1a, 2&, 3e, 4, 4&
```

Structural reading:
- Sixteenth-note grid
- Downbeat anchored
- Sustained anchor conflict
- Anticipatory resolution

GSN:

```
G16  A↓  S+  C<
```

### Example 3: Floating broken-beat loop

Structural reading:
- Sixteenth-note grid
- No dominant anchor
- Sustained syncopation
- No clear cadence

GSN:

```
G16  A=  S+
```

## Interpretation Rules (Hard Constraints)

1. No symbol may encode hit position
2. No symbol may imply a specific subdivision
3. Different hit patterns may share identical GSN
4. If a distinction requires counting, it does not belong in GSN

## Intent

GSN is designed to:
- compare grooves across genres
- reason about rhythmic function
- drive generative systems
- annotate groove libraries without overfitting
