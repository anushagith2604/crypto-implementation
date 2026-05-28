# crypto-implementation


##  `crypto-implementation`
Create a file named `README.md` inside your `crypto-implementation` folder and paste the following content:


# Cryptographic Implementations & Quantum Vulnerability Analysis

A dual-purpose security repository providing a clean, from-scratch implementation of classical **Asymmetric RSA Cryptography** coupled with an algorithmic complexity simulator tracking vulnerability vectors against **Shor's Algorithm**.

## 🚀 Overview

This project serves as an analytical codebase to evaluate modern cryptographic vulnerabilities. It splits into two core modules:
1. **From-Scratch Asymmetric Engine:** Pure Python implementation of RSA key generation, modular multiplicative inverse calculation via the Extended Euclidean Algorithm, and basic message en/decryption transformations.
2. **Post-Quantum Cryptography (PQC) Complexity Analysis:** A mathematical simulation modeling the operational scaling of the **General Number Field Sieve (GNFS)** vs. **Shor's period-finding quantum runtime**.

---

## 📉 Algorithmic Complexity Comparison

The core post-quantum risk factor stems from the dramatic divergence in scaling characteristics when handling large composite integers ($N$):

| Metric | Classical Factoring (GNFS) | Quantum Factoring (Shor's) |
| :--- | :--- | :--- |
| **Complexity Profile** | Sub-Exponential | Cubic Polynomial |
| **Big-O Notation** | $\mathcal{O}\left(\exp\left(c \sqrt[3]{\ln N} \sqrt[3]{(\ln \ln N)^2}\right)\right)$ | $\mathcal{O}\left((\log_2 N)^3\right)$ |
| **2048-bit RSA Space**| $\approx 10^{30}$ classical operations (Secure) | $\approx 8.5 \times 10^9$ quantum gates (Breached) |

---

## 🛠️ Installation & Execution

1. **Clone the repository:**
```bash
   git clone [https://github.com/anushakhare/crypto-implementation.git](https://github.com/anushakhare/crypto-implementation.git)
   cd crypto-implementation
Run the baseline python script (no external dependencies required):Bash   python quantum_vulnerability_analysis.py



🧠 Architectural InsightsKey Generation Mechanics: Prime generation variables $p$ and $q$ compute $N$ and Euler's Totient $\phi(N)$. The system selects a public exponent $e$ coprime to $\phi(N)$ and solves for the private key parameter $d \equiv e^{-1} \pmod{\phi(N)}$.Quantum Break-case Analysis: Classical encryption relies on the fact that finding the prime components of a 2048-bit key takes billions of years using conventional computing power. Shor's algorithm bypasses this restriction by translating the factoring challenge into a period-finding function on quantum registers, which can be computed efficiently via the Quantum Fourier Transform.
