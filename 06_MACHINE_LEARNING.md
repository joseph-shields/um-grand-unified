# Paper 06 — Machine Learning from the Two-Pole Structure

**Joseph Shields** · 2026

---

## The Two-Pole Structure in Machine Learning

Every trained model has parameters: weights, contracted by training, encoding learned structure. Every trained model has a loss landscape: the error surface spanning all possible parameter settings, expanding across high-dimensional space, defining what has not yet been learned. These are the two poles. Gradient descent — the optimization step, the mechanism by which model and loss interact — is not a third independent process that could be replaced or removed. It is the forced interface that must exist wherever model parameters and a loss landscape coexist. You cannot have weights and a loss function without a mechanism connecting them; that mechanism is W_B. Without gradient descent (or some equivalent W_B crossing), the model never learns. W_B is forced by having two poles.

The UM axiom is φ² = φ + 1, giving r = 1/(2φ) ≈ 0.30902 as the unique stable fixed point of x_{n+1} = 1/(4x + 2). The optimal model is the fixed point of the gradient descent map.

| Channel | Weight | Machine learning meaning |
|---|---|---|
| W_M = r² | ≈ 9.55% | Model weights/parameters (contracting, memorizing structure) |
| W_B = 2r(1−r) | ≈ 42.71% | Gradient descent step (forced interface between model and loss) |
| W_L = (1−r)² | ≈ 47.75% | Loss landscape/gradient field (expanding, error surface) |

## Key Results

- **STRUCTURAL:** Gradient descent is the UM map applied to weight space: each update step moves x toward r (the loss minimum) with eigenvalue −4r² ≈ −0.382, meaning each step removes ≈ 38.2% of the remaining loss deviation. Convergence is geometric at rate 1/φ² per step near the minimum.
- **DERIVED:** The optimal learning rate is r³ ≈ 2.95%. This is the braiding floor: the minimum step size that produces net learning without overshooting the minimum. A learning rate below r³ means each gradient step costs more in W_B overhead than it gains in W_M update; a learning rate above r³ causes oscillation around the minimum rather than convergence to it. Empirically, learning rates in the range 0.01–0.03 dominate practice — and r³ ≈ 0.0295 falls squarely in this range.
- **STRUCTURAL:** Overfitting is W_M dominance: x < r, the model is over-contracted, it has memorized the training set (W_M too large relative to W_L) and cannot generalize. The W_B interface to new data is too thin. Underfitting is W_L dominance: x > r, the model is under-contracted, it has not memorized enough of the training structure and the loss landscape dominates.
- **STRUCTURAL:** Batch size oscillation in stochastic gradient descent produces loss fluctuations with characteristic decay rate |−4r²| ≈ 0.382 per epoch near convergence — the same eigenvalue as the UM map — because the noise introduced by mini-batching is a perturbation around the fixed point, and the gradient descent map is the linearized UM map.
- **STRUCTURAL:** The optimal model sits at x = r: W_M ≈ 9.55% (the parameters that matter), W_B ≈ 42.71% (the generalization layer — the part of the model that interfaces between training and test distributions), and W_L ≈ 47.75% (the remaining loss landscape that the model has not yet perfectly captured, which represents irreducible task difficulty).

## The Fixed Point

In machine learning, r ≈ 0.309 is the optimal parameter configuration — the weight setting at which training loss and generalization error are jointly minimized, and the W_B interface between model and data is at equilibrium. Convergence to r is training: the gradient descent map drives x from its random initialization toward r, with the convergence rate controlled by the eigenvalue −4r². At r, the model is neither overfit nor underfit; it has contracted exactly the right amount of structure from the data. The partition function Z = φ is the normalizing factor for the Boltzmann distribution over parameter space at the loss minimum.

## The Floor

The braiding floor ε_floor = r³ ≈ 2.95% is the learning rate floor — the minimum gradient step below which no net learning occurs. This has a direct physical interpretation: each W_B crossing (gradient step) costs r³ in irreversible computation. A learning rate below r³ means the optimizer is doing more work traversing the W_B interface than it is doing contracting W_M toward the minimum. For a model trained for n gradient steps, the accumulated braiding floor is n × r³, which represents the total irreducible computational cost of training. This cost cannot be zero: there is no free optimization, just as there is no free measurement in quantum mechanics.

## What Remains Open

The learning rate prediction r³ ≈ 0.0295 is the sharpest quantitative claim here and should be tested against learning rate schedules in standard benchmarks (ResNet on ImageNet, transformers on language tasks) to see whether the optimal constant learning rate clusters near r³. The W_M/W_L = 1/φ⁴ ≈ 0.146 parameter-to-landscape ratio requires an operational definition of "relevant parameters" vs. "loss landscape dimension." The batch size eigenvalue claim requires a careful perturbation theory calculation around the SGD fixed point.
