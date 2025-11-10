# ⚛️ Quantum Algo Track: From Random Walks to Quantum Search

A collection of simulations exploring fundamental quantum algorithms, transitioning from classical diffusion models to ballistic quantum computation models. This project is structured as a progressive learning path.

***

## 🚀 Key Implementations & Concepts (Problems 0 - 4)

### 1. Classical vs. Quantum Spread

| Problem | Model | Key Result | Scaling | Speedup |
| :--- | :--- | :--- | :--- | :--- |
| **0** | Classical Random Walk ($\pm 1$) | Diffusive spread | $\text{RMS}(t) \propto \mathbf{\sqrt{t}}$ | Baseline |
| **2** | DTQW (Hadamard Coin) | Ballistic spread (via interference) | $\text{RMS}(t) \propto \mathbf{t}$ | $\mathbf{\text{Quadratic}}$ |
| **4** | QHO Walk ($a, a^\dagger$ operators) | Ballistic spread (Energy Levels) | $\text{RMS}(t) \propto \mathbf{t}$ | $\mathbf{\text{Quadratic}}$ |

### 2. Quantum Search Mechanics (Problem 3)

* **Goal:** Implement a Discrete-Time Quantum Walk (DTQW) on a graph $G$ to find a target vertex $t$.
* **Target System:** Implemented on a **$C_4$ Cycle Graph**.
* **Methodology:** The unitary evolution $U = S \cdot C$ is constructed using custom matrix operators in the $\text{Vertex} \otimes \text{Edge Direction}$ Hilbert space.
    * $\mathbf{C}$ (Coin): Block-diagonal matrix applying the local Hadamard operator.
    * $\mathbf{S}$ (Shift): Permutation matrix mapping outgoing edges to the corresponding incoming edge at the neighboring vertex (based on $G$'s adjacency).
* **Result:** Demonstrated a high, oscillating success probability ($P_{success}=0.50$ at $T=2$ on $C_4$), exceeding the classical steady-state ($P_{classical}=0.25$), confirming the concentrated search capability of the quantum walk.

### 3. Core Operators and Simulation

All simulations (Problems 2, 3, 4) rely on high-dimensional linear algebra using **NumPy** to explicitly define and apply the time evolution operator $U$ to the state vector, tracking complex probability amplitudes.

***

## ⏭️ Next Steps

The track continues with the shift from dynamical search to optimization:

* **Problem 6:** Adiabatic Quantum Computation (AQC) slowly changing a Hamiltonian from an easy-to-prepare initial state to a complex final state (the solution).
* **Problem 7:** Exploring the relationship between **QAOA** (Variational Circuits) and **Adiabatic Quantum Computation (AQC)** via Trotterization.
* **Problem 8:** Analyzing the effects of **Noise and Decoherence** on quantum algorithms.
