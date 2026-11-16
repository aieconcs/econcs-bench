---
name: Complexity of Envy-Free Cake Cutting
contributor: Ariel Procaccia
status: partial
claims:
  - ref: "Qilin Ye and Yannan Bai. Cutting Down the Tower: Single-Exponential Envy-Free Cake Cutting."
    url: https://arxiv.org/abs/2609.05191
    date: 2026-09-04
    venue: arXiv preprint
    outcome: partial
    ai_assisted: true
    lean: none
  - ref: "Simon Mackenzie and Mashbat Suzuki. Exact Envy-Free Cake Cutting with Polynomial Expected Queries."
    url: https://arxiv.org/abs/2610.28535
    date: 2026-10-20
    venue: arXiv preprint
    outcome: partial
    ai_assisted: true
    lean: none
  - ref: "Alireza Farhadi and Mohammadtaghi Hajiaghayi. The Query Complexity of Envy-Free Division: Cake, Chores, and Mixed Resources."
    url: https://arxiv.org/abs/2611.11424
    date: 2026-11-08
    venue: arXiv preprint
    outcome: partial
    ai_assisted: true
    lean: full
---

## The Complexity of Envy-Free Cake Cutting

> [!NOTE]
> **Status: partial progress.** Three recent preprints greatly narrow the gap
> from the upper-bound side. Ye and Bai
> ([arXiv:2609.05191](https://arxiv.org/abs/2609.05191), September 2026) give a
> deterministic protocol using $n^{O(1)}2^n$ RW queries, the first
> single-exponential bound. Mackenzie and Suzuki
> ([arXiv:2610.28535](https://arxiv.org/abs/2610.28535), October 2026) give a
> randomized (Las Vegas) protocol using $\widetilde{O}(n^{30})$ expected queries.
> Farhadi and Hajiaghayi ([arXiv:2611.11424](https://arxiv.org/abs/2611.11424),
> November 2026) improve this to $O(n^{12}\log n)$ expected queries, for both
> cake and chores. They also show that any exact protocol with fixed positive
> success probability needs $\Omega(n^2)$ expected queries, so the $\Omega(n^2)$
> lower bound extends to randomized protocols.
> *Qualifications:* the lower bound is not improved in order, and the
> deterministic gap between $\Omega(n^2)$ and $n^{O(1)}2^n$ remains open,
> including whether polynomially many queries suffice deterministically. Not yet
> peer reviewed. Farhadi and Hajiaghayi report a
> [Lean formalization](https://github.com/farhadi94/envy-free-division) of their
> main results; the other two papers have none.

### Problem Description

In the **fair division of a divisible heterogeneous resource**, the resource — called the "cake" — is represented by the interval $[0,1]$. There is a set $N=\{1,\ldots,n\}$ of agents, where each agent $i$ has a nonatomic value measure $v\_i$ over subsets of the cake. The value measure is assumed to be additive and normalized so that $v\_i([0,1])=1$.

An allocation of the cake is denoted $A=(A\_1,A\_2,\ldots,A\_n)$, where the pieces $A\_i$ are pairwise disjoint and their union is the entire cake.

An allocation is **envy-free (EF)** if every agent weakly prefers their own piece to that of every other agent:

$$
v_i(A_i)\geq v_i(A_j)
\qquad \text{for all } i,j\in N.
$$

The standard model for studying the complexity of cake cutting is the **Robertson-Webb (RW) model**, in which an algorithm can access valuations only through two types of oracle queries:

* **Cut Query:** $\mathrm{Cut}\_i(x,\alpha)$ asks agent $i$ to identify a point $y\geq x$ such that $v\_i([x,y])=\alpha$.

* **Eval Query:** $\mathrm{Eval}\_i(x,y)$ asks agent $i$ to report the value $v\_i([x,y])$.

The complexity of a cake-cutting algorithm is measured by the number of RW queries it performs.

### Known Results

* For two agents (cut-and-choose) and three agents (Selfridge-Conway), envy-free allocations can be found using a bounded number of RW queries.

* For decades, it was unknown whether a finite envy-free protocol exists for an arbitrary number of agents.

* Aziz and Mackenzie (2016) resolved this question by designing the first finite envy-free protocol for any number of agents, but its query complexity is

$$
O\left(n^{n^{n^{n^{n^n}}}}\right).
$$

* On the lower-bound side, Procaccia (2009) proved a lower bound of $\Omega(n^2)$.

### Research Goal

Close the enormous gap between the upper bound and the lower bound. Any improvement of the lower bound would be a good first step.

### Key References

* Haris Aziz and Simon Mackenzie. "A Discrete and Bounded Envy-Free Cake Cutting Protocol for Any Number of Agents." *FOCS* (2016).

* Ariel D. Procaccia. "Thou Shalt Covet Thy Neighbor's Cake." *IJCAI* (2009).
