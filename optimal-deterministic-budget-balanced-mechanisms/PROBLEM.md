---
name: Optimal Deterministic Budget-Balanced Mechanisms
contributor: Vincent Conitzer
---

**\#\# Computing Optimal Deterministic Budget-Balanced Mechanisms**

**\#\#\# Problem Description**

We consider the **\*\*automated mechanism design\*\*** problem for a finite set of agents $\{1,\ldots,k\}$. Each agent $i$ has a finite set of types $\Theta_i$ with a prior distribution $P_i$, and there is a finite set of outcomes $O$ (e.g., allocations). Each agent $i$ has a utility function $u_i:\Theta_i\times O\rightarrow \mathbb{Q}$.

A **\*\*deterministic direct-revelation mechanism\*\*** consists of an outcome function $f:\Theta_1\times\cdots\times\Theta_k\rightarrow O$ and, for each agent $i$, a payment function $\pi_i:\Theta_1\times\cdots\times\Theta_k\rightarrow \mathbb{Q}$ (negative if the agent pays). Let $P$ denote the joint prior over type profiles $\theta=(\theta_1,\ldots,\theta_k)$.

The mechanism $(f,\pi)$ must satisfy:
- **\*\*Strong budget balance\*\***: $\sum_{i=1}^k \pi_i(\theta)=0$ for all $\theta$.
- **\*\*Ex-post individual rationality (IR)\*\***: $\pi_i(\theta)+u_i(\theta_i,f(\theta))\geq 0$ for all $i$ and $\theta$.
- **\*\*Dominant-strategy incentive compatibility (DSIC)\*\***: $\pi_i(\theta)+u_i(\theta_i,f(\theta))\geq \pi_i(\theta_{-i},\theta_i')+u_i(\theta_i,f(\theta_{-i},\theta_i'))$ for all $i$, $\theta$, and $\theta_i'\in\Theta_i$.

The objective is to maximize expected social welfare:

$$
\max_{f,\pi}\;\sum_{\theta}P(\theta)\sum_{i=1}^k u_i(\theta_i,f(\theta))
$$

subject to the above constraints and the integrality constraint $f(\theta)\in O$ for all $\theta$ (i.e., the mechanism is deterministic).

**\#\#\# Research Goal**

Determine the computational complexity of computing an optimal deterministic mechanism satisfying strong budget balance, ex-post IR, and DSIC, for a constant number of agents $k$. Specifically:

(1) Is the problem solvable in polynomial time (in the sizes of $\Theta_i$ and $O$)?

(2) If not, is it NP-hard, and what is the best achievable approximation ratio?

**\#\#\# Known Results**

- **\*\*Randomized case\*\***: If the mechanism is allowed to randomize over outcomes, the problem reduces to a **\*\*linear program\*\*** (by relaxing the integrality constraint on outcome selection) and is solvable in polynomial time for constant $k$ (Conitzer and Sandholm, 2002; 2004).

- **\*\*Without payments\*\***: Computing the optimal deterministic mechanism that maximizes social welfare without payments is **\*\*NP-hard\*\***, even for a single agent (Conitzer, 2006).

- **\*\*Without budget balance\*\***: If payments can be collected by an outside party (e.g., a seller) and need not balance, the problem is trivially solvable in polynomial time via VCG mechanisms.

- **\*\*Weak budget balance\*\***: The variant where the mechanism may run a surplus, but the surplus is treated as a welfare loss (i.e., money is burned), leads to nontrivial mechanism design problems (Guo and Conitzer, 2008; 2009; Moulin, 2009; de Clippel, Naroditskiy, and Greenwald, 2009).

**\#\#\# Challenges**

The core difficulty is the **\*\*integrality constraint\*\***: the outcome must be selected deterministically for each type profile, turning what would be a linear program into a **\*\*mixed integer linear program\*\***. The interaction between this integrality constraint and the strong budget balance and DSIC constraints makes the problem structurally different from both the randomized mechanism design case (polynomial) and the no-payment case (NP-hard). It remains open whether the presence of payments and budget balance makes the deterministic problem easier or harder than the no-payment variant.

**\#\#\# Key References**

* Conitzer, Vincent, and Tuomas Sandholm. "Complexity of mechanism design." Proceedings of the 18th Annual Conference on Uncertainty in Artificial Intelligence (UAI). 2002\.
* Conitzer, Vincent, and Tuomas Sandholm. "Self-interested automated mechanism design and implications for optimal combinatorial auctions." Proceedings of the ACM Conference on Electronic Commerce (EC). 2004\.
* Conitzer, Vincent. "Computational aspects of preference aggregation." PhD thesis, Carnegie Mellon University. 2006\.
* de Clippel, Geoffroy, Victor Naroditskiy, and Amy Greenwald. "Destroy to save." Proceedings of the ACM Conference on Electronic Commerce (EC). 2009\.
* Guo, Mingyu, and Vincent Conitzer. "Better redistribution with inefficient allocation in multi-unit auctions with unit demand." Proceedings of the ACM Conference on Electronic Commerce (EC). 2008\.
* Guo, Mingyu, and Vincent Conitzer. "Worst-case optimal redistribution of VCG payments in multi-unit auctions." Games and Economic Behavior 67.1 (2009): 69-98.
* Moulin, Hervé. "Almost budget-balanced VCG mechanisms to assign multiple objects." Journal of Economic Theory 144.1 (2009): 96-119.
