# Paper 03 — Music from the Two-Pole Structure

**Joseph Shields** · 2026

---

## The Two-Pole Structure in Music

Every tonal system has a tonic: the root, the home pitch, the contracting center to which all motion resolves. Every tonal system has a domain of tension: the overtone series, the dominant, the leading tone — expanding, pulling away from the center, generating motion. These are the two poles. The harmonic interval — the leading tone, the W_B space between tension and resolution — is not a third independent musical object. It is the forced interface that must exist wherever a tonic and a field of tension coexist. You cannot have a root and a dominant without an interval structure connecting them; that interval structure is W_B. The bond is forced: suppress all intervals and you have no music, only a drone (pure W_M) or noise (pure W_L).

The UM axiom is φ² = φ + 1, giving r = 1/(2φ) ≈ 0.30902 as the unique stable fixed point of x_{n+1} = 1/(4x + 2). Tonal motion in music is convergence toward this fixed point in frequency space.

| Channel | Weight | Music meaning |
|---|---|---|
| W_M = r² | ≈ 9.55% | Tonic/root (contracting, resolving, the stable center) |
| W_B = 2r(1−r) | ≈ 42.71% | Leading tone/harmonic interval (forced interface between tension and resolution) |
| W_L = (1−r)² | ≈ 47.75% | Dominant/overtone series (expanding, generating tension) |

## Key Results

- **STRUCTURAL:** Fibonacci numbers appear throughout musical scale structure: the pentatonic scale has 5 notes, the diatonic scale has 8, the chromatic scale has 13. These are consecutive Fibonacci numbers. Since φ = lim F_{n+1}/F_n, the scale hierarchy is a direct manifestation of the golden ratio fixed point geometry — each scale level is the W_B interface between the one below and the one above.
- **STRUCTURAL:** The perfect fifth ratio 3/2 = 1.500 lies close to φ = 1.618; the difference is 1.618 − 1.500 = 0.118, which equals φ − 3/2. The fifth is the closest simple-integer frequency ratio to φ, which is why the circle of fifths functions as a UM map on pitch space: iterating by fifths is the pitch-domain analog of x_{n+1} = 1/(4x + 2), spiraling around the chromatic fixed point.
- **DERIVED:** Musical tension is |x − r|: the distance in pitch or harmonic space between the current chord and the tonic fixed point. Resolution is convergence to r; the eigenvalue of that convergence is −4r² = −1/φ² ≈ −0.382, meaning each harmonic step toward resolution removes ≈ 38.2% of remaining tension — a geometric decay that gives tonal music its characteristic sense of progressive relaxation.
- **STRUCTURAL:** The tritone (ratio √2 ≈ 1.414) is the time-symmetric point of the octave: it is exactly equidistant (in log-frequency space) from the tonic (ratio 1) and the octave (ratio 2). This is maximum tension in the UM framework because the tritone is the fixed point of the map x → 2/x on [1,2], which is the time-reversal of the UM map — it is maximally far from r in the sense of being the anti-fixed-point.
- **STRUCTURAL:** The circle of fifths has 12 steps closing on itself. The UM map x_{n+1} = 1/(4x + 2) on pitch space, iterated on the logarithmic scale, produces a return period commensurate with 12 — because log₂(3/2) × 12 ≈ 7.02 octaves, and the fractional residual ≈ 0.02 is of order ε_floor = r³ ≈ 0.0295.

## The Fixed Point

In music, r ≈ 0.309 is the golden ratio attractor in frequency space — the pitch relationship at which the tension between the expanding overtone field and the contracting tonic resolves into stable harmonic structure. Convergence to r is what listeners experience as resolution: a dominant seventh chord resolving to the tonic is the UM map applied once, reducing harmonic displacement by the factor 1/φ² ≈ 0.382. Composers who work in sonata form are iterating the UM map across long timescales: the exposition establishes W_L tension, the development explores displacements far from r, and the recapitulation is convergence back to the tonic fixed point.

## The Floor

The braiding floor ε_floor = r³ ≈ 2.95% is the minimum pitch displacement that is perceptible as harmonic tension — the just-noticeable difference for harmonic context. In cents (1200 cents per octave), r³ of an octave is ≈ 35 cents. This is roughly the threshold below which pitch deviations (from equal temperament to just intonation, for example) cease to be heard as dissonance and become inaudible. For a melody traversing n intervals, the accumulated braiding floor is n × r³, which sets the minimum expressive range below which a melody is harmonically indistinguishable from a monotone.

## What Remains Open

The Fibonacci/scale structure correspondence is well-documented empirically but needs a derivation showing that the UM map on discrete pitch space necessarily selects Fibonacci cardinalities rather than other sequences. The tension-as-|x − r| claim requires a psychoacoustic model mapping music-theoretic harmonic distance to a UM displacement. The tritone identification is clean but requires a formal statement of what "time-symmetric point" means in the UM framework and why that corresponds to maximum tension rather than simply maximum distance.
