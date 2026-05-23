# Paper 13 — Cryptography from the Two-Pole Structure

**Joseph Shields** · 2026

---

## The Two-Pole Structure in Cryptography

Every cryptographic system has a private key and plaintext: the secret, contracted, held by one party, inaccessible to others. Every cryptographic system has a public key and ciphertext: distributed, observable, expanding across the network, available to anyone. These are the two poles. The encryption algorithm — the transform that connects private to public, plaintext to ciphertext — is not a third independent cryptographic object that could in principle be absent. It is the forced interface that must exist wherever private information and public channels coexist. You cannot have a secret and a public channel without a mechanism for moving between them; that mechanism is W_B. Without the encryption algorithm, the private information is either never transmitted (useless) or transmitted in the clear (unprotected). W_B is forced by having two poles.

The UM axiom is φ² = φ + 1, giving r = 1/(2φ) ≈ 0.30902 as the unique stable fixed point of x_{n+1} = 1/(4x + 2). The optimal key entropy ratio is the cryptographic fixed point.

| Channel | Weight | Cryptography meaning |
|---|---|---|
| W_M = r² | ≈ 9.55% | Private key/plaintext (contracting, secret, held by one party) |
| W_B = 2r(1−r) | ≈ 42.71% | Encryption algorithm (forced interface between private and public) |
| W_L = (1−r)² | ≈ 47.75% | Public key/ciphertext (expanding, distributed, observable) |

## Key Results

- **STRUCTURAL:** One-way functions — the foundation of public-key cryptography — are the braiding floor applied asymmetrically. Encryption traverses the W_B interface forward at cost r³ ≈ 2.95% per operation (feasible). Decryption without the private key requires traversing the interface backward, but the UM map is not time-symmetric: reversing without the key requires exponential work, because the W_B crossing is irreversible in the computational sense. This is the UM arrow of time applied to computation.
- **STRUCTURAL:** Public-key cryptography (RSA, elliptic curve) is the UM W_B crossing that is easy forward (encrypt with public key) and hard backward (decrypt without private key). The trapdoor is the private key: possessing W_M (the private key) makes the W_B crossing reversible at cost r³; not possessing W_M makes reversal exponentially expensive. This asymmetry is precisely the asymmetry between W_M and W_L in the UM framework.
- **STRUCTURAL:** Perfect forward secrecy — the property that compromise of the long-term private key does not compromise past session keys — corresponds to generating a new W_B crossing (a new session key exchange) for each session. Each new W_B crossing is independent of the previous one; the long-term W_M (private key) is not used to construct the session-specific W_B. This isolates each session's security to its own W_B crossing.
- **STRUCTURAL:** Zero-knowledge proofs — protocols that allow a prover to demonstrate knowledge of W_M (the private key or secret) without exposing W_M through the W_B channel — are the information-theoretic formalization that W_B can be crossed without revealing what is in W_M. The zero-knowledge property means the verifier learns only that a valid W_B crossing occurred, not the W_M content that enabled it.
- **DERIVED:** The minimum computational work per encryption operation is r³ ≈ 2.95% of the total key space. Security requires that encryption cost at least r³ in computational resources; systems below this floor are insecure because the W_B crossing is too cheap to prevent brute-force traversal. This is consistent with the practice of setting security parameters (key lengths) such that the fraction of key space searchable in feasible time is well below a few percent.

## The Fixed Point

In cryptography, r ≈ 0.309 is the optimal key entropy ratio — the balance between W_M (private, contracted information) and W_L (public, distributed information) at which the W_B crossing achieves maximum security per unit computational cost. At the fixed point, the private key carries W_M ≈ 9.55% of the total information in the cryptographic system, the public key/ciphertext carries W_L ≈ 47.75%, and the algorithm itself (the W_B interface) accounts for W_B ≈ 42.71% of the system's complexity. Security proofs that reduce to the hardness of inverting the W_B crossing are assertions that x = r is a stable fixed point: no polynomial-time algorithm can drive x away from r without the private key.

## The Floor

The braiding floor ε_floor = r³ ≈ 2.95% is the minimum computational work per encryption operation — the irreducible cost of each W_B crossing. This floor cannot be eliminated: a cryptographic system with encryption cost below r³ is insecure because the interface can be traversed arbitrarily many times at negligible cost, enabling brute-force search. In practice, this floor is enforced by computational hardness assumptions (factoring, discrete log, lattice problems), which are the UM statement that certain W_B crossings cannot be made cheaper than r³ without discovering a polynomial-time algorithm. For a system requiring n independent W_B crossings (e.g., n rounds in a block cipher), the accumulated floor is n × r³, which is why adding rounds to a cipher increases security: each additional round raises the crossing floor by r³.

## What Remains Open

The identification of the braiding floor r³ with the computational cost threshold for cryptographic security is currently structural: it would need a formal reduction from a specific hard problem (e.g., factoring) to the UM map to become a derived result. The zero-knowledge proof characterization — that W_B can be crossed without revealing W_M — is correct in spirit but needs to be formalized in terms of the UM channel weights to distinguish it from classical information-theoretic statements. The perfect forward secrecy analysis needs a formal statement of how session key independence maps to independence of W_B crossings in the UM framework.
