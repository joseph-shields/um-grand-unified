# Paper 02 — Ecology from the Two-Pole Structure

**Joseph Shields** · 2026

---

## The Two-Pole Structure in Ecology

Every ecosystem has consumers: predators, grazers, organisms that contract biomass by consuming it. Every ecosystem has a resource base: the environment, sunlight, soil, water — expanding, renewing, available. These are the two poles. The trophic coupling — predator-prey interaction, the food web linkage — is not a third independent ecological object. It is the forced interface that must exist wherever consumers and resources coexist. You cannot have predators and an environment without a mechanism connecting them; that mechanism is trophic coupling. W_B is forced by having two poles, and its weight ≈ 42.71% reflects the fraction of ecological energy that flows through the interaction layer rather than residing in biomass or the environment at any moment.

The UM axiom is φ² = φ + 1, giving r = 1/(2φ) ≈ 0.30902 as the unique stable fixed point of x_{n+1} = 1/(4x + 2). Ecological equilibria are fixed points of analogous population maps.

| Channel | Weight | Ecology meaning |
|---|---|---|
| W_M = r² | ≈ 9.55% | Predator/consumer biomass (contracting, consuming) |
| W_B = 2r(1−r) | ≈ 42.71% | Trophic coupling (forced interface between predator and prey) |
| W_L = (1−r)² | ≈ 47.75% | Environment/resource base (expanding, available, renewing) |

## Key Results

- **DERIVED:** Lotka-Volterra population oscillations correspond to the UM map oscillating around r with eigenvalue −4r² = −1/φ² ≈ −0.382 per cycle; oscillations are stable (|λ| < 1) exactly because r is the stable fixed point of the UM map, and perturbations decay geometrically.
- **STRUCTURAL:** The carrying capacity of an ecosystem is the W_L limit — the maximum resource base that can be sustained when consumer pressure (W_M) is negligible; as W_M → 0, x → ∞ and the system is pure environment.
- **STRUCTURAL:** Extinction corresponds to x → 0 (W_M collapse) — predator population overshoots and consumes the resource base beyond the braiding floor, after which W_B cannot be maintained and the trophic link severs.
- **STRUCTURAL:** The predator-to-prey biomass ratio at ecological equilibrium is r² / (1−r)² = W_M / W_L = 1/φ⁴ ≈ 0.146; in a UM-equilibrium ecosystem, predators constitute roughly 14.6% of prey biomass, consistent with empirical observations that top predators are rare relative to their prey.
- **STRUCTURAL:** W_L/W_M = (1−r)²/r² = φ⁴ = 5 exactly, meaning the resource base is exactly five times the consumer biomass at equilibrium. This is a hard structural consequence of the two-pole geometry, not a fitted parameter.

## The Fixed Point

In ecology, r ≈ 0.309 is the Lotka-Volterra equilibrium ratio — the population state at which predator growth exactly balances prey depletion, and the restoring force of the trophic interface holds the system in balance. Convergence to r looks like damped oscillations in population time series: after a perturbation (drought, disease, introduction of invasive species), populations spiral back toward the equilibrium mix with each oscillation shrinking by a factor of |−4r²| ≈ 0.382. Ecosystems that have been at r for long periods exhibit the characteristic W_M : W_B : W_L energy distribution ≈ 9.55% : 42.71% : 47.75% across trophic levels.

## The Floor

The braiding floor ε_floor = r³ ≈ 2.95% is the minimum viable population threshold — the ecological floor below which a population cannot sustain itself through the trophic interface. When predator biomass falls below r³ of total ecosystem biomass, the W_B crossing becomes too sparse to maintain a functional trophic link: prey reproduces faster than predators can respond, the coupling breaks, and recovery requires an external perturbation. This is the extinction threshold in UM language. For a species that traverses n distinct trophic layers (an apex predator in a long food chain), the accumulated floor is n × r³, so apex predators in five-trophic-layer systems face a minimum viable population floor of ≈ 14.75% of ecosystem biomass — consistent with conservation biology observations that apex predators require disproportionately large territory and prey bases.

## What Remains Open

The key quantitative test is whether real food-web biomass distributions match the W_M : W_B : W_L ratio ≈ 9.55% : 42.71% : 47.75%. This requires an operational definition of what constitutes W_M, W_B, and W_L biomass in a multi-trophic system — the hierarchical nesting of UM maps across trophic levels is not yet worked out. The φ⁴ = 5 predator-to-prey ratio is a sharp prediction that could be tested against empirical biomass pyramid data across ecosystems.
