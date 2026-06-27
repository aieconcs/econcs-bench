---
name: MMS Approximation and Truthful Fair Allocation
contributor: Moshe Babaioff
---

## MMS Approximation and Truthful Fair Allocation

### Problem Description

Consider a fair-division instance with a set $N$ of $n$ agents and a set $M$ of indivisible goods. Each agent $i \in N$ has an additive valuation function $v_i : 2^M \rightarrow \mathbb{R}_{\geq 0}$.

### Maximin Share (MMS)

The **maximin share** of agent $i$ with respect to $n$ agents and goods $M$ is

$$
\text{MMS}_i(n, M) = \max_{(A_1, \ldots, A_n)} \min_{j \in [n]} v_i(A_j),
$$

where the maximum is taken over all partitions of $M$ into $n$ bundles.

An allocation $X = (X_1, \ldots, X_n)$ is an **$\alpha$-MMS allocation** if, for every agent $i \in N$,

$$
v_i(X_i) \geq \alpha \cdot \text{MMS}_i(n, M).
$$

It is known that for $n = 3$ additive agents, an exact MMS allocation (i.e., $\alpha = 1$) might not exist.

### Truthful Mechanisms

A deterministic mechanism is **(dominant-strategy) truthful** if no agent can benefit from misreporting her valuation, regardless of the reports of the other agents.

A randomized mechanism is **truthful in expectation (TIE)** if no agent can increase her expected utility by misreporting, regardless of the reports of the other agents.

### Known Results

### MMS Approximation (without incentives)

Exact MMS allocations do not always exist, even for three additive agents. The best known approximation guarantees for $\alpha$-MMS allocations with additive agents have been steadily improved through a sequence of works. The current best approximation factor is strictly less than 1.

### Truthful Mechanisms

Babaioff, Feige, Manaker, and Morag (2026) study the limits of fairness achievable by truthful mechanisms:

- **Deterministic truthful mechanisms.** Their results are based on a characterization that requires the mechanism to be "non-bossy" and "neutral." Under these assumptions, they establish bounds on the best MMS approximation achievable by deterministic truthful mechanisms for $n$ additive agents (when goods can be left unallocated). It is open whether removing these structural restrictions enables better guarantees.

- **Randomized TIE mechanisms.** They show that a truthful-in-expectation mechanism can achieve a $1/\log(n)$ ex-post MMS guarantee.

### Research Goals

**Open Problem 1 (MMS approximation).** Find the best $\alpha$ such that an $\alpha$-MMS allocation is guaranteed to exist for every instance with $n$ additive agents. Furthermore, determine the best $\alpha$ for which such an allocation can be computed in polynomial time.

**Open Problem 2 (Truthful and fair allocation).** What are the limits of fairness achievable by (dominant-strategy) truthful mechanisms?

Specifically:

**Open Problem 2a.** What is the best MMS approximation that a deterministic truthful mechanism can obtain for $n$ additive agents (when goods can be left unallocated)? In particular, do the known bounds (Babaioff, Feige, Manaker, and Morag, 2026), which rely on non-bossiness and neutrality, extend to all deterministic truthful mechanisms?

**Open Problem 2b.** What is the best MMS approximation that a randomized truthful-in-expectation mechanism can ensure? The best known result achieves a $1/\log(n)$ ex-post MMS guarantee (Babaioff, Feige, Manaker, and Morag, 2026). Can this be improved, and what is achievable by polynomial-time mechanisms?

### Key References

- Moshe Babaioff, Uriel Feige, Shai Manaker, and Morag (2026). Truthful fair allocation mechanisms.
