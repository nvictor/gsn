# Groove Structure Notation (GSN)

GSN is a structural rhythm notation system. It is a compact symbolic system that describes what a groove feels like-its grouping and gravity-rather than where individual hits occur. The system intentionally avoids encoding subdivisions or counts.

## Design Principles

1. **Structure over events**  
   GSN encodes rhythmic behavior (grouping, gravity), not note placement.

2. **Subdivision-agnostic**  
   No symbol may imply `e`, `&`, or `a`-level timing.

3. **Silent defaults**  
   Neutral values are omitted unless explicitly violated.

4. **Composable axes**  
   Each symbol describes an independent structural dimension.

## Core Axes

### 1. Pulse (P)

Defines the number of felt groupings of the measure. It describes how many main impulses the listener perceives, regardless of the mathematical time signature.

- `P5` - 5-pulse feel
- `P4` - 4-pulse feel
- `P3` - 3-pulse feel
- `P2` - 2-pulse feel

### 2. Anchor (A)

Defines where the groove perceives structural gravity.

- `A↓` - downbeat-anchored (beat 1 dominant)
- `A↑` - upbeat-anchored
- `A↔` - backbeat-anchored (beats 2 & 4 define identity)
- (omitted) - neutral, floating, no dominant anchor

### 3. Syncopation (S)

Describes internal conflict within the pulse groups.

- (omitted) - Clean pulses. Hits mostly align with the main pulse structure.
- `S` - Syncopated pulses. Contains complex internal articulation, ghost notes, or friction against the main pulse.

### 4. Cadence (C)

Describes how the pulses relate to one another temporally.

- (omitted) - On-beat resolution.
- `C<` - Anticipatory (Push). Pulses tend to arrive early or "push" into the next slot.
- `C>` - Delayed (Drag). Pulses sit behind the beat or resolve late.
- `C<>` - Mixed. Contains both pushing and dragging elements.

## Examples

### Example 1: Straight groove with anticipation

Hit pattern:
```
1, 2, 3, 4, 4&
```

Structural reading:
- 4 main pulses (Standard feel)
- Downbeat anchored
- Last hit pushes into the next bar (Anticipation)
- Clean internal structure

GSN:
```
P4 A↓ C<
```

### Example 2: 5-pulse action groove

Hit pattern:
```
1, 1a, 2&, 3e, 4, 4&
```

Structural reading:
- 5 main pulses
- Not anchored
- High internal friction/complexity (Syncopation)
- Anticipatory resolution

GSN:
```
P5 S C<
```

### Example 3: Reggaeton groove / "It's My Life"

Hit pattern:
```
1, 1a, 2&, 3, 3a, 4&
```

Structural reading:
- 2 main pulses
- Downbeat anchored
- Internal syncopation
- No real cadence

GSN:
```
P2 A↓ S
```

### Example 4: 3-pulse action groove / Basara deshi

Hit pattern:
```
1, 1&, 2, 2&, 3, 3&, 4, 4&
```

Structural reading:
- 3 main pulses (1, 2&, 4)
- Not anchored
- Clean hits on downbeats and upbeats
- Anticipatory resolution

GSN:
```
P3 C<
```

### Example 5: Metal "gallop" groove

Hit pattern:
```
1, 1&, 1a, 2, 2&, 2a, 3, 3&, 3a, 4, 4&
```

Structural reading:
- 4 main pulses
- Downbeat anchored
- Clean internal structure
- Anticipatory cadence

GSN:
```
P4 A↓ C<
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
