## The Birthday Paradox  
*A Probabilistic Study in Combinatorics, Asymptotics, and Monte Carlo Simulation*

---

### Overview

The birthday paradox is a classical result in probability theory:

> In a group of just 23 people, the probability that at least two individuals share the same birthday exceeds 50%.

Although widely cited as a counterintuitive phenomenon, this study explores further the birthday problem through:

- Exact combinatorial probability
- Asymptotic approximation
- Expected value analysis
- Monte Carlo simulation

The goal is to understand *why* it occurs and how the probability scales with group size.

---

### Objectives

1. Derive the exact probability formula for shared birthdays.
2. Compute probabilities for varying group sizes.
3. Develop an exponential asymptotic approximation.
4. Analyze expected numbers of matching pairs.
5. Validate theoretical results using simulation.

---

### Mathematical Model

Let $n$ denote the number of individuals in a group.

The probability that all birthdays are distinct is:

$P(\text{no match}) = \prod_{k=0}^{n-1} \frac{365-k}{365}$

Therefore, the probability of at least one shared birthday is:

$P(\text{match}) = 1 - \prod_{k=0}^{n-1} \frac{365-k}{365}$

The smallest $n$ such that this probability exceeds 0.5 is: $n=23$

---

### Asymptotic Approximation

Using the logarithmic expansion:

$\ln(1 - x) \approx -x,$

we obtain the approximation:

$ P(\text{match}) \approx 1 - \exp\left(-\frac{n(n-1)}{2 \cdot 365}\right).$

This reveals that collision probability grows approximately quadratically in $n$, explaining the rapid increase in shared birthdays as group size grows.

---

### Expected Number of Collisions

Using indicator random variables and linearity of expectation:

$E[X] = \binom{n}{2} \cdot \frac{1}{365}$

This shows that the expected number of matching pairs grows proportionally to \( n^2, clarifying the structural reason behind the paradox.

---

### Monte Carlo Simulation

To empirically validate the model, the project implements Monte Carlo simulations:

- Randomly generate birthdays
- Repeat experiments across many trials
- Estimate collision probability
- Compare simulation results with exact and asymptotic curves

Simulation results closely align with theoretical predictions, demonstrating convergence consistent with the law of large numbers.

---

### Repository Structure

birthday-paradox/

│

├── birthday_paradox.ipynb

├── README.md

└── requirements.txt


---

### Key Insight

The paradox arises not from coincidence, but from the rapid quadratic growth in pairwise comparisons as the number of individuals increases.

This project demonstrates how mathematical modelling, approximation theory, and simulation can transform an intuitive puzzle into a structured probabilistic analysis.

---