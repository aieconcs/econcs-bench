---
name: Complexity of Envy-Free Cake Cutting
contributor: Ariel Procaccia
---

## The Complexity of Envy-Free Cake Cutting

### Problem Description

In the **fair division of a divisible heterogeneous resource**, the resource — called the "cake" — is represented by the interval $[0,1]$. There is a set $N=\{1,\ldots,n\}$ of agents, where each agent $i$ has a nonatomic value measure $v_i$ over subsets of the cake. The value measure is assumed to be additive and normalized so that $v_i([0,1])=1$.

An allocation of the cake is denoted $A=(A_1,A_2,\ldots,A_n)$, where the pieces $A_i$ are pairwise disjoint and their union is the entire cake.

An allocation is **envy-free (EF)** if every agent weakly prefers their own piece to that of every other agent:
$$
v_i(A_i)\geq v_i(A_j)
\qquad \text{for all } i,j\in N.
$$

The standard model for studying the complexity of cake cutting is the **Robertson--Webb (RW) model**, in which an algorithm can access valuations only through two types of oracle queries:

* **Cut Query:** $\mathrm{Cut}_i(x,\alpha)$ asks agent $i$ to identify a point $y\geq x$ such that $v_i([x,y])=\alpha$.

* **Eval Query:** $\mathrm{Eval}_i(x,y)$ asks agent $i$ to report the value $v_i([x,y])$.

The complexity of a cake-cutting algorithm is measured by the number of RW queries it performs.

### Known Results

* For two agents (cut-and-choose) and three agents (Selfridge--Conway), envy-free allocations can be found using a bounded number of RW queries.

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
