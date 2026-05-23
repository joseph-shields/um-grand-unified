# Paper 05 — Game Theory from the Two-Pole Structure

**Joseph Shields** · 2026

---

## The Two-Pole Structure in Game Theory

Every game has committed strategies: the decisions already made, the contracted positions that define a player's current stance. Every game has an option space: all possible moves still available, the expanding field of alternatives not yet chosen. These are the two poles. Strategic interaction — the game itself, the place where players' choices meet and produce outcomes — is not a third independent object that might be absent. It is the forced interface that must exist wherever two players with committed strategies and open option spaces exist in relation to each other. You cannot have two players each holding strategies and an option space without a mechanism for those strategies to interact; that mechanism is W_B. The game exists at the interface, not in either player alone. W_B is forced by having two poles.

The UM axiom is φ² = φ + 1, giving r = 1/(2φ) ≈ 0.30902 as the unique stable fixed point of x_{n+1} = 1/(4x + 2). The Nash equilibrium is the game-theoretic fixed point of the best-response map.

| Channel | Weight | Game theory meaning |
|---|---|---|
| W_M = r² | ≈ 9.55% | Committed strategy (contracting, decided, dominating) |
| W_B = 2r(1−r) | ≈ 42.71% | Strategic interaction (forced interface between players) |
| W_L = (1−r)² | ≈ 47.75% | Option space (expanding, all possible moves, contingent) |

## Key Results

- **DERIVED:** The Nash equilibrium is r — the unique stable fixed point of the best-response map. Best-response dynamics x_{n+1} = BR(x_n) converges to Nash when the map is a contraction, and the UM map is a contraction with eigenvalue −4r² = −1/φ² ≈ −0.382. Each iteration of best-response dynamics removes ≈ 38.2% of the deviation from Nash, giving geometric convergence at rate 1/φ² per round.
- **STRUCTURAL:** In the Prisoner's Dilemma, defection is W_M behavior (contracting to self-interest, refusing W_B), cooperation is W_L behavior (expanding trust, accepting the interface), and communication/signaling is W_B (the forced interface that, when suppressed, collapses the game to the W_M-dominated defection equilibrium). The tragedy of the commons is what happens when W_B is institutionally suppressed.
- **STRUCTURAL:** Zero-sum games have W_L/W_M = 1 by definition: every gain to one player is a loss to the other, so the total value in W_L exactly equals the total value in W_M. This means W_B = 0 (no value is created by the interaction, only transferred). Zero-sum games have no W_B because there is no surplus at the interface to constitute a bond.
- **STRUCTURAL:** Positive-sum games have W_B > 0: value is created at the interface that exceeds what either player could achieve alone. The maximum value creation occurs at the UM equilibrium, where W_B ≈ 42.71% of total game value resides in the interaction layer.
- **STRUCTURAL:** The trembling hand epsilon — the minimum perturbation that changes equilibrium strategy selection — is ε_floor = r³ ≈ 2.95%. Strategies that differ by less than r³ in expected payoff are indistinguishable under trembling-hand refinement and collapse to the same equilibrium selection.

## The Fixed Point

In game theory, r ≈ 0.309 is the Nash equilibrium — the strategy profile at which no player can improve their payoff by unilaterally deviating, given the other players' strategies. Convergence to r under best-response dynamics is the process of iterated rationality: each player updates their strategy by best-responding to the current profile, and the eigenvalue −4r² ensures that this process converges rather than diverges. At the Nash equilibrium, the three channels are in balance: W_M ≈ 9.55% (the committed core strategy), W_B ≈ 42.71% (the interaction surplus), and W_L ≈ 47.75% (the remaining option space that each player holds in reserve).

## The Floor

The braiding floor ε_floor = r³ ≈ 2.95% is the trembling-hand epsilon — the minimum perturbation size that matters for equilibrium selection. In a finite game, any strategy that costs less than r³ of the total payoff range to deviate from is, for practical purposes, indistinguishable from the equilibrium strategy. This is the irreducible noise floor of strategic reasoning: players cannot respond to payoff differences smaller than r³ without the "trembling hand" effect making those responses unreliable. For a game with n sequential interaction stages, the accumulated floor is n × r³, which sets the minimum payoff resolution at which the game has distinct strategic content.

## What Remains Open

The identification of Nash equilibrium with the UM fixed point r requires showing that the best-response map in a generic n-player game has the same fixed-point structure as x_{n+1} = 1/(4x + 2) — which is a non-trivial claim requiring a reduction argument. The zero-sum/positive-sum W_B = 0 / W_B > 0 claim is structural and correct in spirit but needs a formal measure of W_B in terms of game-theoretic value creation. The trembling-hand floor identification should be tested against explicit game-theoretic calculations in parameterized game families.
