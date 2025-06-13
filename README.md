# QuantumStatePrep

Preparing an arbitrary $n$-qubit quantum state - a mini-project for the [Erdos Quantum Computing Boot Camp](https://www.erdosinstitute.org/programs/summer-2025/quantum-computing-boot-camp).

Employing an algorithm by Long and Sun [(arXiv)](https://arxiv.org/pdf/quant-ph/0104030) [(Phys. Rev. A)](https://journals.aps.org/pra/abstract/10.1103/PhysRevA.64.014303), I show how one can initialize a system of $n$-qubits from the state $|0\rangle^{\otimes n}$ into any arbitrary quantum state of the form $\sum_{x=0}^{2^n-1} c_x |x\rangle, c_x\in \mathbb{C}$. The algorithm runs very quickly for $n\leq 8$, and a user can enter a vector of their choice as a $2^n$-dimensional `numpy` array, or use the random array provided as default.

```
## Input state as a 2ⁿ-dimensional numpy array
n = 3;

state = np.random.rand(2**n) + 1j * np.random.rand(2**n);
prep = create_state_prep(state);

s = Statevector(prep); 
assert norm(s - state) < 1e-12;
```
