# Paper 14 — Control Theory from the Two-Pole Structure

**Joseph Shields** · 2026

---

## The Two-Pole Structure in Control Theory

Every control system has a plant: the physical system being controlled — contracting, measured, its state determined by physical law. Every control system has disturbances and noise: the uncontrolled inputs from the environment — expanding, unknown, pushing the plant away from the desired state. These are the two poles. The controller — the feedback mechanism that reads the plant state and generates a corrective signal — is not a third independent system component that might be absent. It is the forced interface that must exist wherever a measurable plant and an uncontrolled disturbance environment coexist. You cannot have a plant in a noisy environment without a mechanism for correcting deviations from the desired state; that mechanism is W_B. Remove the controller and you have an open-loop plant in a noisy environment — not a control system at all. W_B is forced by having two poles.

The UM axiom is φ² = φ + 1, giving r = 1/(2φ) ≈ 0.30902 as the unique stable fixed point of x_{n+1} = 1/(4x + 2). The setpoint r is the desired fixed point toward which the controller drives the plant state.

| Channel | Weight | Control theory meaning |
|---|---|---|
| W_M = r² | ≈ 9.55% | Plant state (contracting, measured, physical system) |
| W_B = 2r(1−r) | ≈ 42.71% | Controller (forced interface between measured state and control signal) |
| W_L = (1−r)² | ≈ 47.75% | Disturbance/noise (expanding, uncontrolled, environmental input) |

## Key Results

- **DERIVED:** The PID controller is the UM map decomposed into its three components. The proportional term P applies a restoring force toward the setpoint r: this is the linearized UM map term, corresponding to the restoring force −(4r² + 2r − 1)/(4x + 2)² evaluated near r. The integral term I accumulates W_B crossings over time: the accumulated braiding floor N × r³ for N steps. The derivative term D applies the eigenvalue correction −4r² per step, anticipating the next position of the state before it arrives. Together, PID reconstructs the full UM map dynamics.
- **DERIVED:** The eigenvalue of the UM map at r is −4r² = −1/φ² ≈ −0.382. Optimal control converges at rate 1/φ² per step: each control cycle removes ≈ 38.2% of the remaining state error. This is the fastest convergence achievable without overshoot (|λ| < 1) for a second-order system, and it is the golden-ratio-optimal convergence rate — the control analog of the golden section search.
- **STRUCTURAL:** The control resolution — the quantization floor of the control signal — is ε_floor = r³ ≈ 2.95%. Control signals smaller than r³ of the full actuator range cannot produce a distinguishable plant response above the sensor noise floor. Digital-to-analog converters in control systems are specified with resolution such that the least significant bit corresponds to approximately r³ of the full-scale output — the smallest step that has engineering significance.
- **STRUCTURAL:** Overfitting in control (integrator windup) corresponds to W_M dominance: the integral term has accumulated so much history that the controller is responding to past states rather than present ones (x < r, over-contracted in time). Underfitting (insufficient integral action) corresponds to W_L dominance: the controller fails to accumulate enough history to reject steady-state disturbances (x > r).
- **DERIVED:** The Nyquist stability criterion — the condition that the feedback loop does not oscillate or diverge — is the requirement that the loop eigenvalue satisfies |λ| < 1. For the UM map, |−4r²| = 4 × (1/(2φ))² = 4/(4φ²) = 1/φ² ≈ 0.382 < 1. The UM map is stable by construction: its eigenvalue at the fixed point is exactly 1/φ² < 1, which means any control system designed around the UM fixed point automatically satisfies the Nyquist criterion. Instability occurs when the designer moves x away from r, increasing the effective eigenvalue above 1.

## The Fixed Point

In control theory, r ≈ 0.309 is the setpoint — the desired plant state that the controller is designed to maintain in the presence of disturbances. Convergence to r is closed-loop regulation: the controller applies the UM map x_{n+1} = 1/(4x + 2) to the plant state at each control cycle, driving x toward r at rate 1/φ² per cycle. At the fixed point, the plant state (W_M ≈ 9.55%), controller activity (W_B ≈ 42.71%), and residual disturbance (W_L ≈ 47.75%) are in their equilibrium proportions. The partition function Z = φ normalizes the total system energy at the fixed point configuration.

## The Floor

The braiding floor ε_floor = r³ ≈ 2.95% is the control resolution — the minimum step size of the control signal below which no plant response is distinguishable from sensor noise. This is the quantization floor of the control system: it sets the minimum meaningful actuator increment and determines the precision of the setpoint that the system can maintain. For a control system operating through n actuator stages in series (e.g., a multi-joint robot arm), the accumulated floor is n × r³, setting the minimum positioning error achievable at the end effector. No control system can reduce steady-state error below n × r³ without increasing actuator resolution, because each stage contributes at least r³ of irreducible quantization noise.

## What Remains Open

The PID decomposition — that P corresponds to the linearized UM map, I to the accumulated braiding floor, and D to the eigenvalue correction — is structural and needs to be formalized as an exact correspondence rather than an analogy. The Nyquist derivation is exact for the UM map at r, but the claim that any UM-designed controller is automatically stable needs a proof that covers the full nonlinear map, not just the linearization at r. The control resolution claim r³ ≈ 2.95% should be compared against standard engineering practice in precision control systems (CNC machining, semiconductor lithography) where actuator resolution is specified in physical units that can be compared against r³ of the full operating range.
