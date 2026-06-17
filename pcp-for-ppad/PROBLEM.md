---
name: **PCP for PPAD**
---

**\#\# A PCP Theorem for PPAD**

**\#\#\# Problem Description**

The **\*\*PCP (Probabilistically Checkable Proofs) Theorem\*\*** is one of the
cornerstones of computational complexity. It characterizes NP in terms of proof
systems where a verifier reads only a constant number of random bits and proof
bits, yet accepts valid proofs with certainty and rejects invalid proofs with
high probability. The theorem's deepest consequence is a sweeping theory of
**\*\*hardness of approximation\*\***: it implies that for many NP-hard optimization
problems, even finding an approximately optimal solution is NP-hard.

**\*\*PPAD\*\*** (Polynomial Parity Arguments on Directed graphs) is the complexity
class capturing the difficulty of total search problems whose existence is
guaranteed by a parity argument on directed graphs — most famously, computing a
Nash equilibrium. The foundational results of Daskalakis, Goldberg, and
Papadimitriou (2009) and Chen, Deng, and Teng (2009) established that finding an
exact Nash equilibrium in a two-player game is PPAD-complete.

A natural and far-reaching question is whether PPAD has its own analogue of the
PCP theorem:

\> **\*\*Does there exist a "PCP theorem for PPAD"\*\*** — i.e., a robust
\> characterization of PPAD showing that approximate versions of PPAD-complete
\> problems remain PPAD-hard?

More concretely, the **\*\*PCP-for-PPAD conjecture\*\*** (introduced by Babichenko,
Papadimitriou, and Rubinstein, 2016\) asserts that the $(\varepsilon,
\delta)$-**\*\*Generalized Circuit\*\*** problem — a relaxation of the standard
PPAD-complete Generalized Circuit problem in which both the "almost-fixedness"
and "closeness" parameters are allowed to be positive constants — remains
PPAD-hard.

**\*\*The $(\varepsilon, \delta)$-Generalized Circuit Problem\*\***: Given a
(succinctly described) arithmetic circuit $C$ over $[0,1]^n$ with Lipschitz
constant at most $1$, find a point $x \in [0,1]^n$ such that each gate $g$ of
the circuit satisfies its defining constraint to within an additive
$\varepsilon$ error, and the output is within $\delta$ of a fixed point. For
$\varepsilon = \delta = 0$ this is the standard PPAD-complete problem. The
conjecture is that the problem remains PPAD-hard for some constants $\varepsilon,
\delta > 0$.

**\#\#\# Known Results**

**\*\*Hardness of exact and near-exact computation:\*\***

-   Finding an exact Nash equilibrium in a two-player $n \times n$ game is
   PPAD-complete (Daskalakis, Goldberg, and Papadimitriou, 2009; Chen, Deng,
   and Teng, 2009).
-   Rubinstein (STOC 2015 / SICOMP 2018\) proved that computing an
   $\varepsilon$-approximate Nash equilibrium is PPAD-hard for
   $\varepsilon = \Omega(1)$ in many-player games.
-   Rubinstein (FOCS 2016\) extended this to two-player games, assuming the
   Exponential Time Hypothesis for PPAD, and proved a BFLS-type PCP for PPAD
   which requires query complexity approximately $\sqrt{n}$ — sublinear in
   $n$, but still much more than the $O(1)$ queries expected from a full PCP
   theorem.

**\*\*Consequences if the conjecture holds:\*\***

-   The conjecture would imply PPAD-hardness of computing $\varepsilon$-approximate
   equilibria in many economic models, including Fisher markets with SPLC
   utilities, Hylland–Zeckhauser equilibria, and competitive equilibria in
   exchange economies.
-   More broadly, it would give a unified framework for establishing hardness of
   approximation within PPAD, paralleling the role of the PCP theorem for NP.
-   Several conditional hardness results (for markets, fair division, and
   mechanism design) have been derived assuming the conjecture, demonstrating
   its power and scope (see, e.g., Deligkas, Fearnley, Hollender, and
   Melissourgos, 2026; Braverman, Liu, Xue, and Zhou, 2026).

**\#\#\# Research Goal**

Prove (or disprove) the PCP-for-PPAD conjecture: that the $(\varepsilon,
\delta)$-Generalized Circuit problem is PPAD-hard for some constants
$\varepsilon, \delta > 0$.

**\#\#\# Challenges**

The central difficulty is that PPAD is a class of **\*\*total search problems\*\*** —
a solution is guaranteed to exist — whereas the classical PCP theorem applies to
**\*\*decision problems\*\*** in NP. In the NP setting, the PCP theorem converts a
correct proof into one that is locally testable; an invalid proof is rejected
with high probability. In the PPAD setting, one must maintain the **\*\*totality\*\***
guarantee (the directed-graph parity argument must still ensure the existence of
a solution) while simultaneously introducing enough **\*\*robustness\*\*** that
approximate solutions cannot be found easily. Reconciling totality with local
testability is the core technical barrier.

The partial progress by Rubinstein (FOCS 2016\) demonstrates that a BFLS-type PCP
for PPAD is achievable with $\approx \sqrt{n}$ query complexity, but bridging
the gap to $O(1)$ queries — as the classical PCP theorem achieves for NP —
remains wide open and appears to require fundamentally new ideas.

**\#\#\# Key References**

*   Babichenko, Yakov, Christos Papadimitriou, and Aviad Rubinstein. "Can almost
   everybody be almost happy? PCP for PPAD and the inapproximability of Nash."
   Proceedings of the Innovations in Theoretical Computer Science Conference
   (ITCS). 2016\.
*   Babichenko, Yakov. "Query complexity of approximate Nash equilibria." Journal
   of the ACM (2016).
*   Babichenko, Yakov, and Aviad Rubinstein. "Communication complexity of
   approximate Nash equilibria." Proceedings of the Annual ACM Symposium on
   Theory of Computing (STOC). 2017\.
*   Braverman, Mark, Jingyi Liu, Eric Xue, and Chenghan Zhou. "Hardness of
   approximate Hylland–Zeckhauser equilibria." arXiv preprint arXiv:2606.00951
   (2026).
*   Chen, Xi, Xiaotie Deng, and Shang-Hua Teng. "Settling the complexity of
   computing two-player Nash equilibria." Journal of the ACM (2009).
*   Daskalakis, Constantinos, Paul W. Goldberg, and Christos H. Papadimitriou.
   "The complexity of computing a Nash equilibrium." SIAM Journal on Computing
   (2009).
*   Deligkas, Argyrios, John Fearnley, Alexandros Hollender, and Themistoklis
   Melissourgos. "Fisher markets with approximately optimal bundles and the need
   for a PCP theorem for PPAD." Proceedings of the Annual ACM Symposium on
   Theory of Computing (STOC). 2026\.
*   Göös, Mika, and Aviad Rubinstein. "Near-optimal communication lower bounds
   for approximate Nash equilibria." SIAM Journal on Computing (2023).
*   Rubinstein, Aviad. "Inapproximability of Nash equilibrium." SIAM Journal on
   Computing (2018). (Conference version: STOC 2015.)
*   Rubinstein, Aviad. "Settling the complexity of computing approximate
   two-player Nash equilibria." Proceedings of the Annual Symposium on
   Foundations of Computer Science (FOCS). 2016\.
