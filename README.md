# Groove Structure Notation (GSN)

Groove Structure Notation (GSN) is a compact symbolic system for describing the structural behavior of rhythmic grooves, independent of instrumentation, bar analysis, step grids, or performance nuance.

GSN is inspired by the same philosophy as Harmony Flow Notation (HFN):  
it encodes function and intent, not events.

Two grooves with very different hit/note placements can share the same GSN if they behave the same way structurally.

## Why GSN Exists

Traditional rhythm notation answers questions like:
- *What notes are played?*
- *On which subdivision?*
- *In which bar?*

GSN answers different questions:
- *What defines time?*
- *Where does rhythmic gravity live?*
- *Does the groove lean forward or sit back?*
- *Are strong beats reinforced or violated?*

GSN intentionally ignores:
- Exact hit locations
- Bar length
- Instrumentation
- Swing ratios
- Performance microtiming

Those details can vary freely without changing the groove’s structure.

## Core Concepts

GSN describes a groove using **four independent structural dimensions**:

1. **Grid (G)** – how time is subdivided  
2. **Anchor (A)** – where rhythmic gravity lives  
3. **Push (P)** – directional energy of the groove  
4. **Displacement (D)** – intentional violation of strong beats  

All symbols are optional. If a symbol is omitted, the groove is assumed to behave in the neutral or default way for that dimension.

## Grid (G)

**What subdivision governs motion?**

```
G4   quarter-note grid
G8   eighth-note grid
G16  sixteenth-note grid
```

The grid describes *how time is articulated*, not how busy the groove is.

Examples:
- Four-on-the-floor house → `G4`
- Boom bap hip-hop → `G8`
- Funk / drum & bass → `G16`

## Anchor (A)

**Where does rhythmic gravity live?**

```
A↓   downbeat anchored (beat 1 is dominant)
A↔   backbeat anchored (beats 2 & 4 define identity)
```

If omitted, the groove is not primarily defined by anchoring.

## Push (P)

**Which way does energy lean?**

```
P→   forward push (anticipatory, driving)
P←   laid-back pull (settling, relaxed)
```

Push describes *directional bias*, not timing accuracy.
A groove can feel forward or laid-back even when played perfectly in time.

## Displacement (D)

**How are strong beats intentionally violated?**

Displacement symbols are only used when beats are *actively* displaced.
On-beat playing is the default and is not notated.

```
D<    anticipation (before the beat)
D>    delay (after the beat)
D<>   bracketed displacement (before and after)
D!    beat avoidance (explicitly not allowed to land)
```

Displacement refers to **structural tension**, not ornamentation or ghost notes.

## Groove Signatures

A **Groove Signature** is a space-separated list of GSN symbols.

Examples:

### Rock (classic backbeat)
```
G8  A↔
```

### Four-on-the-floor (house / disco)
```
G4  A↓
```

### Boom bap hip-hop
```
G8  A↔  P→  D<>
```

### Laid-back hip-hop / neo-soul
```
G8  A↔  P←
```

### Funk
```
G16  A↓  P→  D<>
```

## Design Principles

GSN follows these rules:

- **Structure over events**  
  If changing one hit changes the notation, the notation is too detailed.

- **Defaults are silent**  
  Only non-neutral behavior is encoded.

- **Survives variation**  
  Ghost notes, fills, swing, and sound choice do not change the signature.

- **Composable dimensions**  
  Each axis describes an independent structural force.

## Relationship to Harmony Flow Notation (HFN)

HFN describes **harmonic structure over time**.  
GSN describes **rhythmic structure over time**.

Both:
- Compress musical time into gestures
- Ignore surface detail
- Encode motion, gravity, and tension
- Allow comparison without alignment

They are designed to be complementary.

## Status

GSN is intentionally minimal and evolving.  
The symbol set is small by design and should remain so.

If a new symbol is required, it must describe a **new structural force**, not a variation of an existing one.
