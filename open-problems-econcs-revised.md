# **Main**

**Open Problems in EconCS**

**Contributed Problems**

* [Online Submodular Welfare in Random Order]()  
  Contributed by Vahab Mirrokni  
* [Prophet Inequality for Subadditive CA]()  
  Contributed by Paul Duetting  
* [Truthful Mechanism for Submodular CA]()  
  Contributed by Sebastien Lahaie  
* [Submodular Welfare Maximization with Demand Oracle](https://docs.google.com/document/d/1fjcbAtJXXljguuqyXFG1BaSndEyaSICOJrPaiXbS6F4/edit?resourcekey=0-RTLC7gldSbU6upatQFH5tA&tab=t.o71s2fnq0fmo)  
  Contributed by Renato Paes Leme  
* [Disproving Strong MSP]()  
  Anonymous Contribution  
* [Revenue Optimal DSIC Auction]()  
  Contributed by Jeff Jiang, David Parkes and Tonghan Wang.  
* [Bayesian Security Games]()  
  Contributed by Vincent Conitzer. See [blog post](https://aifails.substack.com/p/more-on-ai-and-math-two-open-problems).  
* [EFX]()  
  Contributed by Simina Branzei  
* [DSIC Mechanisms for Multi-Unit Auctions]()  
  Contributed by Noam Nisan  
* [Deterministic CA for Subadditive Bidders]()  
  Contributed by Shahar Dobzinski  
* [PCP for PPAD]()  
  Contributed by Aviad Rubinstein  
* [Query Complexity of Tarski Fixed Points]()  
  Contributed by Aviad Rubinstein  
* [Computing the Meaning of a Game]()  
  Contributed by Christos Papadimitriou

**Solved\!**

* [Optimal Deterministic Budget-Balanced Mechanisms](https://docs.google.com/document/d/1fjcbAtJXXljguuqyXFG1BaSndEyaSICOJrPaiXbS6F4/edit?resourcekey=0-RTLC7gldSbU6upatQFH5tA&tab=t.73tvqghfwtr6)  
  Contributed by Vincent Conitzer. [Solution here](https://aifails.substack.com/p/even-more-on-ai-and-math-solution).

Warning: The problems have been reformatted and lightly edited by AI after the submission by the original authors. If you spot some inaccuracies or want to suggest corrections, please email [aieconcs26@googlegroups.com](mailto:aieconcs26@googlegroups.com) or submit a pull request.

**~~Other sample Problems~~**

* [~~PolyRegret for One-Bit Feedback Bilateral Trade~~](https://docs.google.com/document/d/1fjcbAtJXXljguuqyXFG1BaSndEyaSICOJrPaiXbS6F4/edit?resourcekey=0-RTLC7gldSbU6upatQFH5tA&tab=t.0)  
* [~~Polynomial Regret Cutting-Plane~~](https://docs.google.com/document/d/1fjcbAtJXXljguuqyXFG1BaSndEyaSICOJrPaiXbS6F4/edit?resourcekey=0-RTLC7gldSbU6upatQFH5tA&tab=t.aq8aqypxq8v1)  
* [~~Anonymous Reserves~~](https://docs.google.com/document/d/1fjcbAtJXXljguuqyXFG1BaSndEyaSICOJrPaiXbS6F4/edit?resourcekey=0-RTLC7gldSbU6upatQFH5tA&tab=t.9lqzzzss2c91)  
* [~~L\_2 Calibration~~](https://docs.google.com/document/d/1fjcbAtJXXljguuqyXFG1BaSndEyaSICOJrPaiXbS6F4/edit?resourcekey=0-RTLC7gldSbU6upatQFH5tA&tab=t.iruuqjxyqfqi)

# PolyRegret for One-Bit Feedback Bilateral Trade

**\# Open Research Challenge: Polynomial Regret for One-Bit Feedback Gains from Trade under Per-Step Budget Balance**

**\#\# 1\. Background & Motivation**

In the paper \[Contextual Online Bilateral Trade (arXiv:2602.12903)\](https://arxiv.org/abs/2602.12903), the authors investigate repeated bilateral trade where agents' valuations are contextual.

At each time step $t \= 1, \\dots, T$:  
\- The learner (platform) observes a context vector $x\_t \\in \\mathbb{R}^d$ (normalized to $\\|x\_t\\|\_2 \\le 1$).  
\- The seller and buyer have private valuations parameterized by unknown, fixed vectors $s, b \\in \\mathbb{R}^d$ (with $\\|s\\|\_2, \\|b\\|\_2 \\le 1$):  
 $$s\_t \= \\langle s, x\_t \\rangle, \\quad b\_t \= \\langle b, x\_t \\rangle$$  
\- The learner posts two prices: $p\_t$ to the seller and $q\_t$ to the buyer.  
\- Trade occurs if and only if both agents accept their prices, i.e., $s\_t \\le p\_t$ and $q\_t \\le b\_t$.  
\- The learner's objective is to maximize economic efficiency, measured by the cumulative **\*\*Gain from Trade (GFT)\*\***:  
 $$\\text{GFT}\_t(p\_t, q\_t) \= (b\_t \- s\_t) \\cdot \\mathbb{I}\\{s\_t \\le p\_t\\} \\cdot \\mathbb{I}\\{q\_t \\le b\_t\\}$$  
\- Regret is measured against the optimal omniscient dynamic pricing benchmark, which achieves $\\sum\_{t=1}^T (b\_t \- s\_t)\_+$.

\---

**\#\# 2\. The Feedback & Budget Balance Models**

The problem exhibits different regret regimes depending on the feedback structure and the constraints placed on the platform's budget:

1\. **\*\*Two-Bit Feedback\*\***: The learner observes separately whether each agent accepts their price ($\\mathbb{I}\\{s\_t \\le p\_t\\}$ and $\\mathbb{I}\\{q\_t \\le b\_t\\}$). Here, the authors establish an optimal $O(d \\log d)$ regret bound while strictly enforcing **\*\*per-step budget balance\*\*** ($p\_t \\le q\_t$ for all $t$).  
2\. **\*\*One-Bit Feedback with Budget Violation\*\***: The learner only observes the binary trade outcome ($\\mathbb{I}\\{s\_t \\le p\_t\\} \\cdot \\mathbb{I}\\{q\_t \\le b\_t\\}$). If the learner is permitted to occasionally post $p\_t \> q\_t$ (violating per-step budget balance) but maintaining an overall bounded deficit of $O(d \\log d)$, it can still achieve $O(d \\log d)$ regret.  
3\. **\*\*One-Bit Feedback with Per-Step Budget Balance\*\***: When the learner is restricted to one-bit feedback AND must strictly satisfy per-step budget balance ($p\_t \\le q\_t, \\forall t$), the authors provide a randomized algorithm (Algorithm 2\) that achieves regret **\*\*independent of the time horizon $T$\*\***, but **\*\*exponential in the dimension $d$\*\***:  
  $$\\text{Regret} \\le O\\left(d 6^d\\right)$$

\---

**\#\# 3\. The Open Research Question**

\> **\*\*Open Problem:\*\*** Can we design an online learning algorithm for Contextual Bilateral Trade with One-Bit Feedback under strict Per-Step Budget Balance ($p\_t \\le q\_t$) that achieves **\*\*$\\text{poly}(d)$ regret\*\***?  
\> Alternatively, is there an information-theoretic or geometric lower bound showing that exponential dependence on $d$ is strictly necessary in this regime?

\---

**\#\# 4\. Key Technical Challenges**

**\#\#\# The Ambiguity of No-Trade**  
In the one-bit feedback model under per-step budget balance ($p\_t \\le q\_t$), a "no-trade" outcome is fundamentally ambiguous. The learner observes that trade failed, but cannot determine whether:  
\- The seller rejected $p\_t$ ($s\_t \> p\_t$),  
\- The buyer rejected $q\_t$ ($b\_t \< q\_t$), or  
\- Both agents rejected their prices.

**\#\#\# Non-Convex Uncertainty Regions**  
Because of this ambiguity, directly incorporating no-trade feedback yields non-convex uncertainty regions for the ground-truth parameters $(s, b)$, which are computationally and analytically intractable to maintain.

**\#\#\# The Cost of Randomized Exploration**  
To bypass non-convexity without violating budget balance, the state-of-the-art approach relies on a randomized pricing strategy that updates confidence regions *\*only\** when trade successfully occurs (since a successful trade unambiguously implies $s\_t \\le p\_t$ and $q\_t \\le b\_t$). However, relying on uniform randomization over the projected uncertainty intervals results in a very slow rate of potential decrease per successful trade, which ultimately manifests as the $6^d$ factor in the regret bound.

# Polynomial Regret Cutting-Plane

**\# Open Research Challenge: Polynomial Regret Cutting-Plane Algorithms for Strong Separation Oracles**

**\#\# 1\. Background & Motivation**

In the paper \[Contextual Recommendations and Low-Regret Cutting-Plane Algorithms (arXiv:2106.04819)\](https://arxiv.org/abs/2106.04819), the authors investigate a natural variant of contextual linear bandits motivated by routing in navigational engines and recommendation systems.

**\#\#\# Contextual Recommendations**  
\- A learner seeks to identify a hidden $d$-dimensional value vector $w^\* \\in \\mathbb{R}^d$ (normalized to $\\|w^\*\\|\_2 \\le 1$).  
\- In each round $t \= 1, \\dots, T$, the learner is presented with a menu of possible actions $\\mathcal{X}\_t \\subseteq \\mathbb{R}^d$.  
\- The learner recommends an action $x\_t \\in \\mathcal{X}\_t$ and receives utility $\\langle x\_t, w^\* \\rangle$.  
\- Instead of observing numerical reward feedback, the learner only observes the identity of the optimal action $x\_t^\* \= \\arg\\max\_{x \\in \\mathcal{X}\_t} \\langle x, w^\* \\rangle$.  
\- The goal is to minimize cumulative recommendation regret:  
 $$\\text{Regret}\_T \= \\sum\_{t=1}^T \\langle x\_t^\* \- x\_t, w^\* \\rangle$$

\---

**\#\# 2\. The Geometric Reduction: Low-Regret Cutting-Plane Algorithms**

To solve the contextual recommendation problem, the authors establish a reduction to a purely geometric online learning problem called the **\*\*Low-Regret Cutting-Plane Problem\*\***.

At each round $t \= 1, \\dots, T$:  
\- The hidden point $w^\*$ lies in a known bounded convex set $\\mathcal{W}\_0 \\subset \\mathbb{R}^d$.  
\- The learner selects a query point $p\_t \\in \\mathbb{R}^d$.  
\- A separation oracle returns a halfspace containing $w^\*$. Specifically, it returns a unit vector $v\_t \\in \\mathbb{R}^d$ such that $\\langle w^\*, v\_t \\rangle \\ge \\langle p\_t, v\_t \\rangle$.  
\- The geometric "regret" of the cutting-plane query is defined as the distance from $w^\*$ to the separating hyperplane passing through $p\_t$:  
 $$r\_t \= \\langle w^\* \- p\_t, v\_t \\rangle$$  
\- The goal is to minimize total cutting-plane regret $\\sum\_{t=1}^T \\langle w^\* \- p\_t, v\_t \\rangle$.

\---

**\#\# 3\. Strong vs. Weak Separation Oracles**

The difficulty of the cutting-plane problem depends heavily on the power of the separation oracle:

1\. **\*\*Weak Separation Oracle\*\***: At the beginning of round $t$, an adversary fixes a direction $u\_t \\in \\mathbb{R}^d$ *\*before\** observing the learner's query point $p\_t$. The oracle simply returns $v\_t \= u\_t$ or $v\_t \= \-u\_t$ depending on the sign of $\\langle w^\* \- p\_t, u\_t \\rangle$.  
2\. **\*\*Strong Separation Oracle\*\***: The oracle observes the learner's query point $p\_t$ *\*first\**, and can adversarially choose the separating normal vector $v\_t$ in response to $p\_t$ (subject only to the validity constraint $\\langle w^\* \- p\_t, v\_t \\rangle \\ge 0$).

\---

**\#\# 4\. State of the Art (arXiv:2106.04819)**

For **\*\*weak separation oracles\*\***, the authors design an algorithm achieving $O(\\text{poly}(d))$ regret, completely independent of the time horizon $T$.

For **\*\*strong separation oracles\*\***, the authors provide two distinct algorithms exhibiting a sharp trade-off:  
\- An algorithm achieving regret $O(d \\log T)$ (logarithmic in $T$, polynomial in $d$).  
\- An algorithm achieving regret $\\exp(O(d \\log d))$ (independent of $T$, but exponential in $d$).

\---

**\#\# 5\. The Open Research Question**

\> **\*\*Open Problem:\*\*** Can we design a cutting-plane algorithm for **\*\*Strong Separation Oracles\*\*** that achieves **\*\*$\\text{poly}(d)$ regret without any dependence on $T$\*\***?  
\> Alternatively, can we establish an information-theoretic lower bound proving that for strong separation oracles, any algorithm must suffer either $\\Omega(\\log T)$ regret or exponential dependence on the dimension $d$?

\---

**\#\# 6\. Key Technical Obstacles**

**\#\#\# Adversarial Direction Selection**  
Under a strong separation oracle, when the learner queries a point $p\_t$, the oracle can inspect the current geometry of the learner's confidence region $\\mathcal{W}\_t$ and select a normal $v\_t$ that minimizes the volume reduction of the set while maximizing the immediate geometric regret $\\langle w^\* \- p\_t, v\_t \\rangle$.

**\#\#\# Centroid Approximations and Asymmetry**  
Standard cutting-plane methods (like the ellipsoid method or Vaidya's cutting-plane method) query the volumetric center or gravitational centroid of $\\mathcal{W}\_t$. While querying the exact centroid guarantees a constant fraction of volume reduction, it does not guarantee low regret in all directions because convex bodies can be highly asymmetric. If the oracle chooses a direction pointing along a thin, elongated "spike" of the convex body, the distance $\\langle w^\* \- p\_t, v\_t \\rangle$ can remain large for many rounds.

**\#\#\# Steiner Centroids and Intrinsic Volumes**  
To mitigate asymmetry, the authors in arXiv:2106.04819 introduce query points based on Steiner centroids and intrinsic volumes. However, maintaining these geometric invariants under arbitrary adversarial cuts currently forces a loose approximation that scales exponentially with dimension if one demands zero dependence on $T$.

# Anonymous Reserves

**\# Open Research Challenge: Bounding the Gap Between Myerson Optimal Auctions and Anonymous Reserves**

**\#\# 1\. Background & Motivation**

In single-item Bayesian mechanism design, consider $n$ bidders with values $v\_i$ drawn independently from (potentially non-identical) regular distributions $F\_1, \\dots, F\_n \\in \\mathcal{R}$.

We define the competitive ratio $\\rho$ as the maximum factor by which the Myerson optimal auction ($\\text{Rev}(\\text{OPT})$) outperforms the best Second-Price Auction with an Anonymous Reserve ($\\text{Rev}(\\text{AR})$):

$$\\rho \= \\sup\_{F\_1, \\dots, F\_n \\in \\mathcal{R}^n} \\frac{\\mathbb{E}\_{\\mathbf{v} \\sim \\prod F\_i} \[\\text{Rev}(\\text{OPT}, \\mathbf{v})\]}{\\sup\_{r} \\mathbb{E}\_{\\mathbf{v} \\sim \\prod F\_i} \[\\text{Rev}(\\text{SPA}\_r, \\mathbf{v})\]}$$

where $\\text{SPA}\_r$ denotes a second-price auction with a single anonymous reserve price $r$ applied to all bidders.

\---

**\#\# 2\. State of the Art**

\- **\*\*The Hartline-Roughgarden Conjecture (2009)\*\***: For over a decade, it was widely conjectured that $\\rho \= 2$ for all independent regular distributions.  
\- **\*\*Current Lower Bound ($\\approx 2.15$)\*\***: *\*Jin, Jiang, Lu, and Zhang (2022)\** disproved the conjecture by constructing a set of asymmetric distributions—leveraging a discretization technique—where the optimal revenue exceeds anonymous reserve revenue by a factor of $2.15$.  
\- **\*\*Current Upper Bound ($\\approx 2.62$)\*\***: The best-known upper bound remains $2.62$, largely derived from relating anonymous pricing to prophet inequalities and sequential posted price mechanisms.

\---

**\#\# 3\. The Open Research Question**

\> **\*\*Open Problem:\*\*** Given the significant gap between the established lower bound of **\*\*2.15\*\*** and the upper bound of **\*\*2.62\*\***, can we refine these results to determine the true worst-case competitive ratio $\\rho$?

\---

**\#\# 4\. Key References**

\- **\*\*Hartline, J. D., & Roughgarden, T. (2009).\*\*** *\*Simple versus Optimal Mechanisms.\**  
\- **\*\*Jin, Y., Jiang, P., Lu, P., & Zhang, J. (2022).\*\*** *\*Tight Revenue Gaps among Multi-Unit Mechanisms.\** SIAM Journal on Computing.  
\- **\*\*Alaei, S. (2014).\*\*** *\*Bayesian Combinatorial Auctions: Expanding Prophet Inequalities to Multiple Items.\** (Context for the 2.62 bound).

# L\_2 Calibration

**\# Research Prompt: Breaking Calibration Bounds via Direct Optimization**

**\#\# Goal**

Design a **\*\*direct optimization approach\*\*** — using gradient descent, mirror descent, or online convex optimization on a suitable potential function, possibly with adaptive step sizes, epoch structures, or regularization tricks — to achieve one or both of the following:

1\. **\*\*Break the $T^{2/3}$ barrier for $\\ell\_1$ calibration error\*\*** in online binary sequential forecasting, achieving $o(T^{2/3})$ (i.e., $O(T^{2/3 \- \\varepsilon})$ for some $\\varepsilon \> 0$).  
2\. **\*\*Break the $T^{1/3}$ barrier for $\\ell\_2$ (squared) calibration error\*\***, achieving $o(T^{1/3})$.

\> \[\!IMPORTANT\]  
\> The approach must **\*\*not\*\*** rely on combinatorial game reductions such as the **\*\*Sign Preservation (SP)\*\*** game of Qiao & Valiant (2021) or the **\*\*Sign Preservation with Reuse (SPR)\*\*** game of Dagan, Daskalakis, Fishelson, Golowich, Kleinberg & Okoroafor (2024). We seek a "clean" analytical approach that works directly in the calibration problem's native space.

\---

**\#\# Problem Setup**

**\#\#\# Online Binary Calibration with Distributional Predictions**

A forecaster interacts with an adversary (oblivious or adaptive) over $T$ rounds. In each round $t \= 1, \\ldots, T$:

1\. The forecaster outputs a **\*\*probability density\*\*** $p\_t : \[0, 1\] \\to \\mathbb{R}\_{\\geq 0}$ satisfying $\\int\_0^1 p\_t(x)\\, dx \= 1$ and $p\_t(x) \\geq 0$.  
2\. The adversary reveals a binary outcome $y\_t \\in \\{0, 1\\}$.

The forecaster's prediction $p\_t$ is a full probability distribution over the interval $\[0, 1\]$, representing the forecaster's "spread" of belief. The classical point-prediction setting is recovered as the special case $p\_t \= \\delta\_{q\_t}$ (a Dirac delta at some $q\_t \\in \[0,1\]$).

**\#\#\# The Signed Error Function and Total Weight Function**

Define two central objects. The **\*\*signed cumulative error function\*\*** $S\_T : \[0, 1\] \\to \\mathbb{R}$:

$$S\_T(x) \= \\sum\_{t=1}^{T} p\_t(x)\\,(y\_t \- x)$$

and the **\*\*total weight function\*\*** $N\_T : \[0, 1\] \\to \\mathbb{R}\_{\\geq 0}$:

$$N\_T(x) \= \\sum\_{t=1}^{T} p\_t(x)$$

which records how much total density was placed at each point $x$ across all rounds. The **\*\*weighted average outcome\*\*** at $x$ is:

$$\\bar{y}(x) \= \\frac{\\sum\_{t=1}^{T} y\_t \\, p\_t(x)}{N\_T(x)}$$

Perfect calibration requires $\\bar{y}(x) \= x$ for all $x$ where $N\_T(x) \> 0$, i.e., the weighted average outcome at each point equals the point itself.

Both evolve incrementally: after round $t$,  
$$S\_t(x) \= S\_{t-1}(x) \+ p\_t(x)\\,(y\_t \- x), \\qquad N\_t(x) \= N\_{t-1}(x) \+ p\_t(x)$$

**\#\#\# Calibration Error Definitions**

The calibration error at point $x$ is $|x \- \\bar{y}(x)|$. Weighting by total density and integrating:

**\*\*$\\ell\_1$ Calibration Error:\*\***  
$$\\text{CalErr}\_1 \= \\int\_0^1 N\_T(x)\\left|x \- \\bar{y}(x)\\right| dx \= \\int\_0^1 \\left| S\_T(x) \\right| dx$$

The second equality follows because $N\_T(x)(x \- \\bar{y}(x)) \= \\sum\_t p\_t(x)(x \- y\_t) \= \-S\_T(x)$, so $N\_T(x)|x \- \\bar{y}(x)| \= |S\_T(x)|$.

**\*\*$\\ell\_2^2$ Calibration Error (Squared):\*\***  
$$\\text{CalErr}\_2^2 \= \\int\_0^1 N\_T(x)\\left(x \- \\bar{y}(x)\\right)^2 dx \= \\int\_0^1 \\frac{S\_T(x)^2}{N\_T(x)}\\, dx$$

The second equality follows because $N\_T(x)(x \- \\bar{y}(x))^2 \= \\frac{(N\_T(x)(x \- \\bar{y}(x)))^2}{N\_T(x)} \= \\frac{S\_T(x)^2}{N\_T(x)}$.

**\*\*$\\ell\_2$ Calibration Error:\*\***  
$$\\text{CalErr}\_2 \= \\sqrt{\\int\_0^1 \\frac{S\_T(x)^2}{N\_T(x)}\\, dx}$$

\> \[\!WARNING\]  
\> **\*\*The $\\ell\_2^2$ error is NOT $\\|S\_T\\|\_{L^2}^2 \= \\int S\_T(x)^2\\,dx$.\*\*** The correct formula has a $1/N\_T(x)$ denominator. This is the continuous analogue of $\\sum\_i s\_i^2/n\_i$ in the binned setting. The denominator $N\_T(x)$ is **\*\*endogenous\*\*** — it depends on the forecaster's past choices. This makes the $\\ell\_2$ case fundamentally harder than minimizing $\\|S\_T\\|\_{L^2}$: the forecaster simultaneously controls both the numerator $S\_T(x)^2$ and the denominator $N\_T(x)$, and there is a tension between making $N\_T(x)$ large (which decreases $S\_T^2/N\_T$) and keeping $|S\_T(x)|$ small.

\> \[\!NOTE\]  
\> **\*\*Relationship to the classical (binned) setting.\*\*** In the binned setting with point predictions $p\_t \= \\delta\_{q\_t}$, if bin $B\_i$ has $n\_i$ predictions and signed error $s\_i$, then $\\text{CalErr}\_1 \= \\sum\_i |s\_i|$ and $\\text{CalErr}\_2^2 \= \\sum\_i s\_i^2/n\_i$. The distributional formulation recovers these exactly in the appropriate limit and is strictly more general: it **\*\*eliminates discretization bias entirely\*\*** and allows the forecaster to spread mass continuously.

**\#\#\# The Forecaster's Strategy Space**

At each round $t$, the forecaster chooses $p\_t$ from the space of probability densities on $\[0, 1\]$:  
$$\\mathcal{P} \= \\left\\{ p : \[0,1\] \\to \\mathbb{R}\_{\\geq 0} \\;\\middle|\\; \\int\_0^1 p(x)\\, dx \= 1 \\right\\}$$

This is an infinite-dimensional simplex (the space of probability measures on $\[0,1\]$). The forecaster's strategy is a mapping from the current state $S\_{t-1}(\\cdot)$ (and possibly the full history) to a new density $p\_t \\in \\mathcal{P}$.

**\#\#\# Key Structural Properties**

1\. **\*\*Linearity in $p\_t$:\*\*** For fixed $y\_t$, the increment $S\_t(x) \- S\_{t-1}(x) \= p\_t(x)(y\_t \- x)$ is **\*\*linear\*\*** in the forecaster's choice $p\_t$. This makes the problem amenable to online linear optimization / mirror descent.

2\. **\*\*The constraint $\\int p\_t \= 1$ links all points $x$.\*\*** Unlike the binned setting where the forecaster picks one bin, here the forecaster allocates a unit budget of probability mass across the continuum. Placing more mass at $x$ means placing less elsewhere.

3\. **\*\*The adversary's move is scalar.\*\*** $y\_t \\in \\{0,1\\}$ determines the function $x \\mapsto (y\_t \- x)$, which is a fixed affine function of $x$. When $y\_t \= 1$, the increment is $p\_t(x)(1 \- x) \\geq 0$; when $y\_t \= 0$, it is $\-p\_t(x) \\cdot x \\leq 0$. The sign of the increment at $x$ depends only on $y\_t$ and whether $x \< y\_t$ or $x \> y\_t$.

\---

**\#\# Known Results (State of the Art)**

**\#\#\# Upper Bounds**

| Metric | Best Known Rate | Method | Reference |  
|:-------|:---------------|:-------|:----------|  
| $\\ell\_1$ CalErr | $O(T^{2/3})$ | Blackwell approachability / potential function | Foster & Vohra (1998) |  
| $\\ell\_1$ CalErr | $O(T^{2/3 \- \\varepsilon})$ for some $\\varepsilon \> 0$ | SPR game algorithm | Dagan et al. (2024) |  
| $\\ell\_2^2$ CalErr | $\\tilde{O}(T^{2/3})$ | Swap regret minimization | Multiple works |  
| $\\ell\_2$ CalErr | $\\tilde{O}(T^{1/3})$ | Via $\\ell\_2^2$ bound | Follows from above |

**\#\#\# Lower Bounds**

| Metric | Best Known Lower Bound | Adversary Type | Reference |  
|:-------|:----------------------|:---------------|:----------|  
| $\\ell\_1$ CalErr | $\\Omega(T^{1/2})$ | General | Folklore |  
| $\\ell\_1$ CalErr | $\\Omega(T^{0.528})$ | Oblivious | Qiao & Valiant (2021) |  
| $\\ell\_1$ CalErr | $\\Omega(T^{0.544})$ | Oblivious | Dagan et al. (2024) |

**\#\#\# The Gap**

For $\\ell\_1$: The truth lies somewhere in $\[T^{0.544}, T^{2/3 \- \\varepsilon}\]$.  
For $\\ell\_2$: The truth lies somewhere in $\[\\widetilde{\\Omega}(T^{1/4}), \\tilde{O}(T^{1/3})\]$ (rough bounds).

\---

**\#\# Why $T^{2/3}$ Arises and How the Distributional Formulation Changes Things**

Understanding *\*why\** the $T^{2/3}$ barrier exists in the classical setting — and how the distributional formulation may circumvent it — is critical.

**\#\#\# The Classical Bias-Variance Tradeoff (Binned Setting)**

In the standard point-prediction setting with $K$ bins:

1\. **\*\*Bias Error (Discretization):\*\*** Rounding to bin centers costs $\\leq T/(2K)$.  
2\. **\*\*Variance Error (Random Walk):\*\*** Each bin's signed error grows as $\\sqrt{n\_i}$. Total: $\\approx \\sqrt{KT}$.  
3\. **\*\*Tradeoff:\*\*** $\\text{CalErr}\_1 \\lesssim T/K \+ \\sqrt{KT}$. Optimizing: $K \= T^{1/3}$, giving $O(T^{2/3})$.

**\#\#\# What Changes with Distributional Predictions**

The distributional formulation **\*\*eliminates the discretization bias entirely\*\*** since $p\_t$ is a continuous density — there are no bins to round to. The entire error is now "variance-type," arising from the stochastic evolution of $S\_t(x)$.

However, a new tradeoff emerges:

1\. **\*\*Concentration vs. Spread:\*\*** If the forecaster concentrates $p\_t$ near a single point (approaching the point-prediction limit), $S\_t(x)$ is large near that point and zero elsewhere. If the forecaster spreads $p\_t$ uniformly, $S\_t(x)$ is nonzero everywhere but each increment is small ($\\sim 1/1 \= 1$ uniformly).

2\. **\*\*The natural bound:\*\*** If $p\_t$ is roughly uniform (density $\\sim 1$), then $|S\_T(x)| \\lesssim \\sqrt{T}$ for each $x$ (random walk), so $\\text{CalErr}\_1 \\lesssim \\int\_0^1 \\sqrt{T}\\, dx \= \\sqrt{T}$. But the forecaster is **\*\*not forced\*\*** to play uniformly — and the adversary can exploit any fixed strategy.

3\. **\*\*The adversary's power:\*\*** Since $y\_t \\in \\{0,1\\}$, the increment at $x$ is $p\_t(x)(y\_t \- x)$. The adversary chooses the entire function $x \\mapsto (y\_t \- x)$ via a single bit. This is a severe constraint on the adversary but still allows it to drive $S\_T$ in consistent directions.

\> \[\!NOTE\]  
\> **\*\*The key question:\*\*** In the distributional formulation, does the $T^{2/3}$ barrier persist, or does the ability to spread mass continuously allow the forecaster to achieve $o(T^{2/3})$ — or even $O(T^{1/2})$? The distributional formulation may be **\*\*strictly easier\*\*** than the point-prediction formulation because the forecaster has more flexibility (a full density vs. a single point). If so, breaking the bounds in this formulation is a natural first step.

\> \[\!IMPORTANT\]  
\> **\*\*The crux for the distributional setting:\*\*** The forecaster must choose $p\_t \\in \\mathcal{P}$ to minimize $\\int |S\_T(x)|\\,dx$ (for $\\ell\_1$) or $\\int S\_T(x)^2/N\_T(x)\\,dx$ (for $\\ell\_2^2$), where each round adds $p\_t(x)(y\_t \- x)$ to $S\_t(x)$ and $p\_t(x)$ to $N\_t(x)$. The $\\ell\_2$ case is especially rich because the forecaster controls both the signed error and its normalizing weight. The functional nature of $S\_t$ opens the door to: (a) Hilbert space techniques for the (unnormalized) squared case and surrogate bounds, (b) infinite-dimensional mirror descent on $\\mathcal{P}$, (c) kernel methods that capture correlations between nearby $x$ values, and (d) spectral decomposition of the error operator.

\---

**\#\# Why Existing Approaches Use Combinatorial Games**

Dagan et al. (2024) broke the $T^{2/3}$ barrier by:

1\. Defining the **\*\*Sign Preservation with Reuse (SPR)\*\*** combinatorial game — an abstraction where a player must assign $\+/-$ signs to "cover up" accumulated errors across cells.  
2\. Proving a **\*\*bidirectional equivalence\*\*** between SPR and calibration: algorithms for SPR translate to calibration algorithms, and SPR lower bounds translate to calibration lower bounds.  
3\. Solving SPR via a **\*\*recursive strategy\*\*** that reuses covered signs, yielding an $O(T^{2/3 \- \\varepsilon})$ calibration algorithm.

**\*\*The key insight we want to replicate without the SPR game:\*\*** The forecaster can deliberately bias predictions to "cancel out" past calibration errors in specific bins. This "error reuse / error cancellation" mechanism is what breaks the $T^{2/3}$ barrier. The question is whether this can be captured directly via a potential function and optimization dynamics.

**\#\# References**

1\. **\*\*Foster & Vohra (1998).\*\*** "Asymptotic Calibration." *\*Biometrika.\** — Established the $O(T^{2/3})$ upper bound via Blackwell approachability.  
2\. **\*\*Qiao & Valiant (2021).\*\*** "Stronger Calibration Lower Bounds via Sidestepping." *\*STOC 2021.\** — Introduced the Sign Preservation game, proved $\\Omega(T^{0.528})$ lower bound.  
3\. **\*\*Dagan, Daskalakis, Fishelson, Golowich, Kleinberg & Okoroafor (2024).\*\*** "Breaking the $T^{2/3}$ Barrier for Sequential Calibration." *\*arXiv:2406.13668, STOC 2025.\** — Introduced SPR game, proved bidirectional equivalence, achieved $O(T^{2/3\-\\varepsilon})$ upper bound and $\\Omega(T^{0.544})$ lower bound.  
4\. **\*\*Hart & Mas-Colell (2001).\*\*** "A General Class of Adaptive Strategies." — Potential function approach to approachability and calibration.  
5\. **\*\*Abernethy, Bartlett & Hazan (2011).\*\*** "Blackwell Approachability and No-Regret Learning are Equivalent." *\*COLT 2011.\** — Equivalence between approachability and online learning.

\---

**\#\# Specific Technical Directions to Explore**

**\#\#\# Direction 1: Potential Functions for the True $\\ell\_2^2$ Calibration Error**

The true $\\ell\_2^2$ calibration error is $\\int S\_T(x)^2/N\_T(x)\\,dx$, which is **\*\*not\*\*** a simple norm of $S\_T$. This makes direct potential-function analysis challenging because $N\_T(x)$ is endogenous. Two sub-approaches:

**\*\*Approach 1a: Surrogate via unnormalized $L^2$ potential.\*\*** Use $\\Phi\_t \= \\|S\_t\\|\_{L^2}^2 \= \\int S\_t(x)^2\\,dx$ as a **\*\*surrogate upper bound\*\***. Since $N\_T(x) \\leq T \\cdot \\|p\\|\_\\infty$ but also $N\_T(x) \\geq 0$, we have $\\text{CalErr}\_2^2 \= \\int S\_T^2/N\_T \\geq \\|S\_T\\|\_{L^2}^2 / \\max\_x N\_T(x)$, so bounding $\\|S\_T\\|\_{L^2}^2$ gives a lower bound on the denominator needed. Conversely, if the forecaster ensures $N\_T(x) \\geq c$ uniformly (by spreading mass), then $\\text{CalErr}\_2^2 \\leq \\|S\_T\\|\_{L^2}^2 / c$.

The drift of the surrogate is:  
$$\\Phi\_{t} \- \\Phi\_{t-1} \= 2\\int\_0^1 S\_{t-1}(x)\\, p\_t(x)(y\_t \- x)\\, dx \+ \\int\_0^1 p\_t(x)^2(y\_t \- x)^2\\, dx$$

The first term is **\*\*linear in $p\_t$\*\*** and can be made negative. The second is always positive (variance cost).

**\*\*Approach 1b: Direct potential with $N\_t$ in the denominator.\*\*** Define the true potential:  
$$\\Psi\_t \= \\int\_0^1 \\frac{S\_t(x)^2}{N\_t(x)}\\, dx$$

The one-step drift $\\Psi\_t \- \\Psi\_{t-1}$ involves the change in both $S\_t$ and $N\_t$. Using $S\_t \= S\_{t-1} \+ p\_t(y\_t \- \\cdot)$ and $N\_t \= N\_{t-1} \+ p\_t$:

$$\\frac{S\_t(x)^2}{N\_t(x)} \- \\frac{S\_{t-1}(x)^2}{N\_{t-1}(x)} \= \\frac{S\_{t-1}(x)^2 \+ 2S\_{t-1}(x)p\_t(x)(y\_t-x) \+ p\_t(x)^2(y\_t-x)^2}{N\_{t-1}(x) \+ p\_t(x)} \- \\frac{S\_{t-1}(x)^2}{N\_{t-1}(x)}$$

This can be rearranged as:  
$$\= \\frac{2S\_{t-1}(x)p\_t(x)(y\_t-x)\\,N\_{t-1}(x) \+ p\_t(x)^2(y\_t-x)^2\\,N\_{t-1}(x) \- S\_{t-1}(x)^2\\,p\_t(x)}{N\_{t-1}(x)(N\_{t-1}(x) \+ p\_t(x))}$$

The **\*\*third term in the numerator is negative\*\***: adding density $p\_t(x)$ to the denominator $N\_t(x)$ "dilutes" the existing error $S\_{t-1}(x)^2$, reducing the calibration error even without changing the signed error. This dilution effect is unique to the $\\ell\_2$ case and provides a natural mechanism for improvement.

**\*\*Key questions:\*\***  
\- Can the dilution effect (the $\-S\_{t-1}^2 p\_t / (N\_{t-1}(N\_{t-1}+p\_t))$ term) be leveraged to achieve a strictly better rate than the surrogate approach?  
\- Is there an optimal balance between "cancellation" (making $S\_t$ small via the drift term) and "dilution" (making $N\_t$ large by spreading mass)?  
\- Does the minimax value of $\\Psi\_T$ over the adversary's sequence give $o(T^{1/3})$?  
\- Can one use **\*\*RKHS (Reproducing Kernel Hilbert Space)\*\*** structure to regularize $p\_t$ and exploit smoothness of $S\_t$?

**\#\#\# Direction 2: Infinite-Dimensional Mirror Descent on $\\mathcal{P}$**

Run **\*\*mirror descent\*\*** directly on the space of probability densities $\\mathcal{P}$, treating calibration as an online convex optimization problem in function space:

\- **\*\*Loss function at round $t$:\*\*** After observing $y\_t$, define the "linearized calibration loss" as  
 $$\\ell\_t(p) \= \\int\_0^1 S\_{t-1}(x)\\, p(x)(y\_t \- x)\\, dx$$  
 This is the first-order contribution of $p$ to $\\|S\_t\\|\_{L^2}^2$ (the surrogate). For the true $\\ell\_2^2$ error, additional terms from the $N\_t$ denominator appear but are second-order.

\- **\*\*Mirror map:\*\*** Use the **\*\*negative entropy\*\*** $\\Omega(p) \= \\int\_0^1 p(x) \\log p(x)\\, dx$ (yielding multiplicative-weights / entropic mirror descent on the infinite-dimensional simplex), or the **\*\*$L^2$ regularizer\*\*** $\\Omega(p) \= \\frac{1}{2}\\int\_0^1 p(x)^2\\, dx$ (yielding projected gradient descent).

\- **\*\*Update rule (entropic):\*\***  
 $$p\_{t+1}(x) \\propto p\_t(x) \\cdot \\exp\\left(-\\eta \\cdot S\_t(x)(y\_t \- x)\\right)$$  
 followed by renormalization. This naturally shifts mass away from regions where $S\_t$ is growing and toward regions where errors can be cancelled.

**\*\*Key questions:\*\***  
\- What regret bound does entropic mirror descent achieve on $\\mathcal{P}$? The standard $O(\\sqrt{T \\log(1/\\delta)})$ regret for $\\delta$-discretized distributions — does it survive in the continuous limit?  
\- Does the entropic regularizer provide an implicit "spreading" effect that avoids the variance blowup of point predictions?  
\- Can one combine mirror descent with a **\*\*time-varying step size\*\*** $\\eta\_t$ that adapts to $\\|S\_t\\|$?

**\#\#\# Direction 3: Spectral / Fourier Decomposition of the Error**

Decompose $S\_t(x)$ in an orthonormal basis of $L^2(\[0,1\])$ (e.g., Fourier, Legendre, or wavelets):

$$S\_t(x) \= \\sum\_{k=0}^{\\infty} \\hat{S}\_t^{(k)}\\, e\_k(x)$$

where $\\hat{S}\_t^{(k)} \= \\langle S\_t, e\_k \\rangle$. Then $\\|S\_T\\|\_{L^2}^2 \= \\sum\_k |\\hat{S}\_T^{(k)}|^2$ (for the surrogate). The true $\\ell\_2^2$ error $\\int S\_T^2/N\_T$ is harder to decompose spectrally because of the $x$-dependent weight $1/N\_T(x)$, but if $N\_T(x)$ is approximately uniform, the spectral analysis of the surrogate transfers.

The increment in each coefficient is:  
$$\\hat{S}\_t^{(k)} \- \\hat{S}\_{t-1}^{(k)} \= \\langle p\_t(\\cdot)(y\_t \- \\cdot), e\_k \\rangle \= y\_t \\langle p\_t, e\_k \\rangle \- \\langle x \\cdot p\_t(x), e\_k \\rangle$$

The forecaster controls the projection of $p\_t$ onto each basis function, subject to $p\_t \\in \\mathcal{P}$.

**\*\*Key questions:\*\***  
\- Can the forecaster keep all Fourier coefficients $|\\hat{S}\_T^{(k)}|$ small simultaneously? Are the low-frequency modes harder to control than high-frequency ones?  
\- Is there a **\*\*frequency-dependent strategy\*\*** where the forecaster allocates "cancellation effort" to different modes at different rates?  
\- Does truncating to the first $M$ modes and running a finite-dimensional strategy give $\\|S\_T\\|\_{L^2} \= O(\\sqrt{M \\cdot T / M}) \= O(\\sqrt{T})$ for any $M$? Combined with a strategy that keeps $N\_T(x)$ roughly uniform, this would give $\\text{CalErr}\_2 \= O(\\sqrt{T}/\\sqrt{c}) \= O(T^{1/2 \- \\alpha})$ for appropriate spreading.  
\- For the $L^1$ case, can Parseval's inequality or interpolation between $L^1$ and $L^2$ give useful bounds?

**\#\#\# Direction 4: Functional Potential with Cross-Point Coupling**

Design a potential functional $\\Phi\[S\_t\]$ on $L^2(\[0,1\])$ that couples the error at different points:

$$\\Phi\[S\_t\] \= \\int\_0^1 \\phi(S\_t(x))\\, dx \+ \\lambda \\iint\_{\[0,1\]^2} K(x, x')\\, S\_t(x)\\, S\_t(x')\\, dx\\, dx'$$

where $\\phi$ is a per-point penalty (e.g., $|\\cdot|^q$ for some $q \\in \[1,2\]$) and $K(x, x')$ is a **\*\*kernel\*\*** that captures the correlation structure. Natural choices:

\- $K(x, x') \= \\mathbf{1}\[|x \- x'| \\leq \\delta\]$ — local coupling (errors at nearby points can cancel).  
\- $K(x, x') \= \\min(x, x') \- xx'$ — Brownian bridge covariance (natural for the constraint structure).  
\- $K(x, x') \= e^{-|x-x'|/\\sigma}$ — Ornstein-Uhlenbeck kernel.

The cross-term $\\iint K \\cdot S\_t \\cdot S\_t'$ is a **\*\*quadratic form\*\*** and its drift can be computed exactly. The idea is that positive correlations in $S\_t$ across nearby $x$ values can be exploited by the forecaster to cancel errors efficiently.

**\*\*Key questions:\*\***  
\- For which kernels $K$ does the negative drift from cross-point cancellation dominate the positive drift from variance?  
\- Is there an optimal $\\phi$ that interpolates between $|\\cdot|$ (for $\\ell\_1$) and $|\\cdot|^2$ (for $\\ell\_2$) and gives the best rate?  
\- Can the kernel $K$ be adapted over time (learned from the trajectory of $S\_t$)?

**\#\#\# Direction 5: Epoch-Based Strategy with Functional Error Recycling**

Design an algorithm with an **\*\*epoch structure\*\*** operating on the error function $S\_t(\\cdot)$:

\- **\*\*Within-epoch:\*\*** Run mirror descent on $\\mathcal{P}$ to minimize a smoothed $L^1$ or $L^2$ norm of the error function: $\\int\_0^1 \\phi\_\\eta(S\_t(x))\\, dx$.  
\- **\*\*Across-epoch:\*\*** At the end of each epoch, the error function $S\_t(\\cdot)$ is not reset. In the next epoch, the forecaster deliberately concentrates mass in regions where $S\_t(x)$ has the "wrong sign" relative to the expected outcome, thereby **\*\*recycling / cancelling\*\*** past errors.  
\- **\*\*The recycling mechanism in continuous form:\*\*** If $S\_t(x) \> 0$ for $x$ near $0.3$, the forecaster can place mass near $x \= 0.3$ and hope that a $y\_{t+1} \= 0$ outcome will push $S\_{t+1}(0.3)$ downward (since the increment is $p\_{t+1}(0.3)(0 \- 0.3) \< 0$).

**\*\*Key questions:\*\***  
\- Does the continuous structure allow more efficient recycling than the discrete (binned) case, because the forecaster can target exact regions rather than coarse bins?  
\- Can one show that recycling across $R$ epochs gives $\\|S\_T\\|\_{L^1} \= O(T^{2/3 \- f(R)})$ for some increasing $f$?  
\- What is the optimal epoch length and the optimal density $p\_t$ within each epoch for the recycling strategy?

**\#\#\# Direction 6: Stochastic PDE / Infinite-Dimensional SDE Approach**

Model the error function $S\_t(x)$ as a solution to a **\*\*stochastic PDE\*\*** (SPDE) in the continuous-time limit:

$$\\partial\_t S(x, t) \= p(x, t)(y(t) \- x)$$

where $p(\\cdot, t) \\in \\mathcal{P}$ is the forecaster's control and $y(t) \\in \\{0, 1\\}$ is the adversary's control. The calibration error is $\\|S(\\cdot, T)\\|\_{L^1}$ or $\\|S(\\cdot, T)\\|\_{L^2}$.

This is a **\*\*controlled infinite-dimensional dynamical system\*\*** (or a stochastic evolution equation if $y(t)$ is modeled stochastically). The value function $V\[S, t\]$ is now a **\*\*functional\*\*** satisfying an infinite-dimensional HJB equation.

**\*\*Key questions:\*\***  
\- Does the infinite-dimensional HJB equation have tractable solutions (e.g., quadratic functionals of $S$ for the $L^2$ case)?  
\- Can the controller achieve $\\text{CalErr}\_2 \= (\\int S^2/N\\, dx)^{1/2} \= o(T^{1/3})$ by solving the HJB? Note the HJB must track both $S$ and $N$ as state variables.  
\- Is the problem equivalent to controlling a **\*\*heat equation with adversarial forcing\*\*** (if one adds a smoothing/diffusion term as regularization)?  
\- Can viscosity solution theory for infinite-dimensional HJB equations provide existence results?

**\#\#\# Direction 7: Direct Online Convex Optimization in Function Space**

Frame the problem as **\*\*online linear optimization\*\*** over the infinite-dimensional simplex $\\mathcal{P}$:

\- At each round $t$, the forecaster picks $p\_t \\in \\mathcal{P}$.  
\- The adversary reveals $y\_t$ and the loss is $\\ell\_t(p\_t) \= \\Phi\[S\_t\] \- \\Phi\[S\_{t-1}\]$ for some potential functional $\\Phi$.  
\- Since $\\ell\_t$ is linear in $p\_t$ (for the first-order term), standard OCO regret bounds apply.

The total calibration error is bounded by: $\\text{CalErr} \\leq \\Phi\[S\_T\] \\leq \\Phi\[S\_0\] \+ \\sum\_t \\ell\_t(p\_t)$, and the regret bound gives $\\sum\_t \\ell\_t(p\_t) \\leq \\min\_{p^\*} \\sum\_t \\ell\_t(p^\*) \+ R\_T$ where $R\_T$ is the regret.

**\*\*Key questions:\*\***  
\- For which potential $\\Phi$ is $\\min\_{p^\*} \\sum\_t \\ell\_t(p^\*)$ small (i.e., the best fixed density in hindsight has low calibration error)?  
\- What regret bound does FTRL with $\\Omega(p) \= \\int p \\log p$ achieve over $\\mathcal{P}$? Standard theory gives $R\_T \= O(\\sqrt{T \\cdot D\_{\\mathrm{KL}}})$, but $D\_{\\mathrm{KL}}$ can be infinite in the continuous case — how to handle this?  
\- Can one use a **\*\*finite-dimensional approximation\*\*** (e.g., restrict to piecewise-constant densities with $K$ pieces) and take $K \\to \\infty$ at the right rate to get the best of both worlds (no discretization bias, finite regret)?

\---

**\#\# Constraints and Desiderata**

1\. **\*\*No combinatorial game reductions.\*\*** The proof should work directly with $S\_t(x)$, $N\_t(x)$, the forecaster's density $p\_t \\in \\mathcal{P}$, and the calibration error $\\int|S\_T|\\,dx$ or $\\int S\_T^2/N\_T\\,dx$ — not via equivalence to SP or SPR games.  
2\. **\*\*Explicit algorithm.\*\*** The result should yield a concrete, implementable forecasting strategy: a mapping from the current state $(S\_{t-1}(\\cdot), N\_{t-1}(\\cdot))$ (or a finite-dimensional summary) to $p\_t \\in \\mathcal{P}$.  
3\. **\*\*Clean potential-function proof.\*\*** The analysis should follow the template: define a potential functional $\\Phi\[S\_t, N\_t\]$, bound $\\mathbb{E}\[\\Phi\[S\_t, N\_t\] \- \\Phi\[S\_{t-1}, N\_{t-1}\] \\mid \\mathcal{F}\_{t-1}\]$ (expected drift), and telescope to get a bound on $\\mathbb{E}\[\\text{CalErr}\]$.  
4\. **\*\*Works against an oblivious adversary\*\*** (the adversary's sequence $y\_1, \\ldots, y\_T$ is fixed before the game starts, but unknown to the forecaster). Adaptive adversary results are a bonus.  
5\. **\*\*Ideally achieves a polynomial improvement\*\*** $O(T^{2/3 \- \\varepsilon})$ for $\\text{CalErr}\_1 \= \\int|S\_T|\\,dx$, or $O(T^{1/3 \- \\varepsilon})$ for $\\text{CalErr}\_2 \= (\\int S\_T^2/N\_T\\,dx)^{1/2}$, not just a polylogarithmic improvement.

\---

**\#\# Useful Structural Observations**

1\. **\*\*The error function has a global constraint.\*\*** Integrating $S\_T(x)$ over $\[0, 1\]$:  
  $$\\int\_0^1 S\_T(x)\\, dx \= \\sum\_t \\int\_0^1 p\_t(x)(y\_t \- x)\\, dx \= \\sum\_t \\left(y\_t \- \\int\_0^1 x\\, p\_t(x)\\, dx\\right) \= \\sum\_t (y\_t \- \\mu\_t)$$  
  where $\\mu\_t \= \\mathbb{E}\_{x \\sim p\_t}\[x\]$ is the mean of $p\_t$. So $\\int S\_T \= \\sum\_t (y\_t \- \\mu\_t)$, a simple sum. This integral constraint links all values of $S\_T(x)$.

2\. **\*\*The increment $p\_t(x)(y\_t \- x)$ factors.\*\*** For fixed $y\_t$, the function $x \\mapsto (y\_t \- x)$ is **\*\*affine\*\*** and does not depend on $p\_t$. The forecaster controls the "shape" $p\_t(x)$ and the adversary controls the "direction" $(y\_t \- x)$. When $y\_t \= 1$: the increment is positive for all $x \< 1$. When $y\_t \= 0$: the increment is negative for all $x \> 0$. This means the adversary can only push $S\_t$ in one of two "directions" (globally positive or globally negative, modulated by $x$).

3\. **\*\*The $\\ell\_2$ case has a rich structure from the $N\_T(x)$ denominator.\*\*** The true $\\ell\_2^2$ error $\\int S\_T^2/N\_T\\,dx$ depends on the forecaster's history through both $S\_T$ and $N\_T$. The forecaster can reduce this error in two ways: (i) **\*\*cancellation\*\*** — making $|S\_T(x)|$ small by choosing $p\_t$ to drive $S\_t$ toward zero, and (ii) **\*\*dilution\*\*** — making $N\_T(x)$ large by spreading mass broadly, which decreases $S\_T^2/N\_T$ even without reducing $|S\_T|$. By contrast, the surrogate $\\|S\_T\\|\_{L^2}^2 \= \\int S\_T^2\\,dx$ only benefits from cancellation. The dilution mechanism is unique to the true $\\ell\_2$ metric and may be the key to breaking $T^{1/3}$.

4\. **\*\*The distributional formulation subsumes randomization.\*\*** In the classical setting, the forecaster randomizes over point predictions. Here, a "spread" density $p\_t$ already encodes this randomization. A density like $p\_t(x) \= \\text{Beta}(a, b)$ centered at the desired prediction but with controlled variance naturally hedges.

5\. **\*\*Connection to kernel operators.\*\*** The bilinear form $\\langle S\_t, p\_t(\\cdot)(y\_t \- \\cdot)\\rangle\_{L^2}$ that appears in the drift of $\\|S\_t\\|\_{L^2}^2$ can be written as $\\langle S\_t, A\_{y\_t} p\_t \\rangle$ where $A\_{y\_t}$ is the multiplication operator $\[A\_{y\_t} f\](x) \= f(x)(y\_t \- x)$. The spectral properties of $A\_{y\_t}$ (eigenvalues, eigenfunctions) may determine the optimal forecasting strategy.

6\. **\*\*The problem has a natural Banach space structure.\*\*** For the $\\ell\_1$ case, $S\_T \\in L^1(\[0,1\])$ and the dual space is $L^\\infty(\[0,1\])$. Mirror descent on $L^1$ with the entropy-like regularizer $\\int |S| \\log |S|$ could yield algorithms with good properties. For the $\\ell\_2$ case, $L^2$ is self-dual, making the analysis cleaner.

7\. **\*\*Smoothness of $S\_t$ can be exploited.\*\*** Since each increment $p\_t(x)(y\_t \- x)$ is as smooth as $p\_t$, if the forecaster uses smooth densities (e.g., bounded in $C^k$ or Sobolev $H^s$), then $S\_t$ inherits this smoothness. Smooth functions in $L^1$ or $L^2$ are easier to control (their mass cannot concentrate on small sets), which may help.

\---

**\#\# References**

1\. **\*\*Foster & Vohra (1998).\*\*** "Asymptotic Calibration." *\*Biometrika.\** — Established the $O(T^{2/3})$ upper bound via Blackwell approachability.  
2\. **\*\*Qiao & Valiant (2021).\*\*** "Stronger Calibration Lower Bounds via Sidestepping." *\*STOC 2021.\** — Introduced the Sign Preservation game, proved $\\Omega(T^{0.528})$ lower bound.  
3\. **\*\*Dagan, Daskalakis, Fishelson, Golowich, Kleinberg & Okoroafor (2024).\*\*** "Breaking the $T^{2/3}$ Barrier for Sequential Calibration." *\*arXiv:2406.13668, STOC 2025.\** — Introduced SPR game, proved bidirectional equivalence, achieved $O(T^{2/3\-\\varepsilon})$ upper bound and $\\Omega(T^{0.544})$ lower bound.  
4\. **\*\*Hart & Mas-Colell (2001).\*\*** "A General Class of Adaptive Strategies." — Potential function approach to approachability and calibration.  
5\. **\*\*Abernethy, Bartlett & Hazan (2011).\*\*** "Blackwell Approachability and No-Regret Learning are Equivalent." *\*COLT 2011.\** — Equivalence between approachability and online learning.

# Submodular Welfare Maximization with Demand Oracle

**\#\# Submodular Welfare Maximization with Demand Oracle: Breaking the $(1-1/e)$ Barrier**

**\#\#\# Problem Description**

In the **\*\*Submodular Welfare Maximization (SWM)\*\*** problem, we are given a set $M$ of $m$ indivisible items and $n$ agents. Each agent $i$ has a monotone submodular valuation function $v\_i : 2^M \\to \\mathbb{R}\_{\\geq 0}$ with $v\_i(\\emptyset) \= 0$. The goal is to find a partition (or allocation) of items $(S\_1, S\_2, \\ldots, S\_n)$ into $n$ disjoint subsets that maximizes the **\*\*social welfare\*\***:  
$$\\text{maximize} \\quad \\sum\_{i=1}^n v\_i(S\_i).$$

A function $v : 2^M \\to \\mathbb{R}\_{\\geq 0}$ is **\*\*monotone submodular\*\*** if:

\- **\*\*Monotonicity\*\***: $v(S) \\leq v(T)$ for all $S \\subseteq T \\subseteq M$.  
\- **\*\*Submodularity (diminishing returns)\*\***: $v(S \\cup \\{j\\}) \- v(S) \\geq v(T \\cup \\{j\\}) \- v(T)$ for all $S \\subseteq T \\subseteq M$ and $j \\notin T$.

The valuation functions are accessed through oracles. Two important oracle models are:

1\. **\*\*Value Oracle\*\***: Given a set $S \\subseteq M$, returns $v\_i(S).$  
2\. **\*\*Demand Oracle\*\***: Given a price vector $p \\in \\mathbb{R}^m\_{\\geq 0}$, returns the set $S^\* \\in \\arg\\max\_{S \\subseteq M} (v\_i(S) \- \\sum\_{j \\in S} p\_j)$ that maximizes the agent's utility (value minus total price).

The demand oracle is strictly more powerful than the value oracle: a demand oracle can simulate a value oracle with polynomial overhead, but the converse is not true.

**\#\#\# Known Results**

\- **\*\*Value Oracle Model\*\***: Vondr\\'{a}k (STOC 2008\) proved that the optimal approximation ratio for the SWM problem in the value oracle model is exactly $1 \- 1/e \\approx 0.6321$. This is achieved by the continuous greedy algorithm combined with pipage rounding, and no algorithm using only value queries can do better.

\- **\*\*Demand Oracle Model\*\***: Feige and Vondr\\'{a}k (Theory of Computing, 2010\) showed that the $1 \- 1/e$ barrier can be broken in the demand oracle model. They designed an algorithm achieving an approximation ratio of $(1 \- 1/e \+ \\epsilon)$ for some small constant $\\epsilon \> 0$. Their approach combines the continuous greedy algorithm with a "correction" phase that uses demand queries to improve upon the $(1\-1/e)$-approximate solution. The improvement $\\epsilon$ obtained in their work is very small (roughly $\\epsilon \\approx 10^{-6}$ or smaller).

**\#\#\# Research Goal**

Design an algorithm for the **\*\*Submodular Welfare Maximization\*\*** problem using **\*\*demand oracle queries\*\*** that achieves an approximation ratio of at least $1 \- 1/e \+ 0.01 \\approx 0.642$. That is, for any instance of SWM with monotone submodular valuations, the algorithm must output an allocation $(S\_1, \\ldots, S\_n)$ such that:  
$$\\mathbb{E}\\left\[\\sum\_{i=1}^n v\_i(S\_i)\\right\] \\geq (1 \- 1/e \+ 0.01) \\cdot \\text{OPT},$$  
where $\\text{OPT} \= \\max\_{(T\_1, \\ldots, T\_n)} \\sum\_{i=1}^n v\_i(T\_i)$ is the value of the optimal allocation.

The algorithm should run in polynomial time in $n$ and $m$, using a polynomial number of demand oracle queries.

**\#\#\# Key Reference**

Download the paper at https://theory.stanford.edu/\~jvondrak/data/submod-improve.pdf and read it carefully before proceeding. This paper (Feige and Vondr\\'{a}k, "The Submodular Welfare Problem with Demand Queries", Theory of Computing, 2010\) establishes the current state of the art and describes the algorithmic framework you should build upon.

Also consult:  
\- Vondr\\'{a}k, "Optimal Approximation for the Submodular Welfare Problem in the Value Oracle Model" (STOC 2008\) — for the $1 \- 1/e$ upper bound in the value oracle model and the continuous greedy algorithm.

# Online Submodular Welfare  in Random Order

**\#\# Online Submodular Welfare Maximization in Random Order: Breaking the $1/2$ Barrier**

**\#\#\# Problem Description**

In the **\*\*Online Submodular Welfare Maximization\*\*** problem, we are given $m$ agents, each with a monotone submodular valuation function $v\_\\ell : 2^{\[n\]} \\to \\mathbb{R}\_{\\geq 0}$ with $v\_\\ell(\\emptyset) \= 0$. A set of $n$ items arrives **\*\*one at a time\*\*** in an online fashion. When item $j$ arrives, the algorithm must make an **\*\*immediate, irrevocable\*\*** decision about which agent to assign it to, without knowledge of future items.

A function $v : 2^{\[n\]} \\to \\mathbb{R}\_{\\geq 0}$ is **\*\*monotone submodular\*\*** if:  
\- **\*\*Monotonicity\*\***: $v(S) \\leq v(T)$ for all $S \\subseteq T$.  
\- **\*\*Submodularity (diminishing returns)\*\***: $v(S \\cup \\{j\\}) \- v(S) \\geq v(T \\cup \\{j\\}) \- v(T)$ for all $S \\subseteq T$ and $j \\notin T$.

The goal is to maximize the **\*\*social welfare\*\*** $\\sum\_{\\ell\=1}^m v\_\\ell(S\_\\ell)$, where $S\_\\ell$ is the set of items assigned to agent $\\ell$.

**\*\*Arrival order models:\*\***  
\- **\*\*Adversarial order\*\***: The adversary chooses both the instance and the arrival order. In this model, no algorithm can achieve a competitive ratio better than $1/2$ for general monotone submodular valuations.  
\- **\*\*Random order\*\***: The adversary chooses the instance (items and valuation functions), but the items arrive in a **\*\*uniformly random permutation\*\***. This is the model we study.

The **\*\*competitive ratio\*\*** of an online algorithm $\\text{ALG}$ is:  
$$\\rho \= \\inf\_{\\text{instances}} \\frac{\\mathbb{E}\[\\text{ALG}\]}{\\text{OPT}},$$  
where $\\text{OPT}$ is the optimal offline social welfare and the expectation is over the random arrival order (and any randomness of the algorithm).

**\#\#\# Known Results**

\- **\*\*Adversarial order\*\***: The simple greedy algorithm (assign each arriving item to the agent with the highest marginal value) achieves a competitive ratio of $1/2$, and this is tight for adversarial order.

\- **\*\*Random order\*\***: Korula, Mirrokni, and Zadimoghaddam (2017) showed that the greedy algorithm achieves a competitive ratio of at least $0.505$ in the random order model, resolving a longstanding open problem of whether the $1/2$ barrier could be broken. For special cases (weighted matching, weighted coverage, "second-order supermodular" functions), they achieve $0.51$.

\- **\*\*Secretary-style algorithms\*\***: The problem is closely related to the $m$-secretary problem and online matching. For the special case of unit-demand (matching) valuations, better ratios are known.

**\#\#\# Research Goal**

Design an algorithm for the **\*\*Online Submodular Welfare Maximization\*\*** problem in the **\*\*random order model\*\*** that achieves a competitive ratio of at least $1/2 \+ 0.01 \= 0.51$. That is, for any instance with monotone submodular valuations, the algorithm must produce an allocation satisfying:  
$$\\mathbb{E}\\left\[\\sum\_{\\ell\=1}^m v\_\\ell(S\_\\ell)\\right\] \\geq 0.51 \\cdot \\text{OPT},$$  
where the expectation is over the uniformly random arrival order and any internal randomness of the algorithm.

The algorithm may use the greedy approach as a starting point, but significant new ideas will likely be needed. Possible directions include:  
\- Improved analysis of greedy or modified greedy algorithms.  
\- Sample-and-optimize approaches (use an initial fraction of items as a "sample" to learn the instance, then optimize over the remaining items).  
\- Primal-dual or LP-relaxation-based approaches adapted to the online random-order setting.  
\- Combining greedy with randomized rounding of a fractional solution.

**\#\#\# Key Reference**

Download the paper at https://arxiv.org/pdf/1712.05450 and read it carefully before proceeding. This paper (Korula, Mirrokni, and Zadimoghaddam, "Online Submodular Welfare Maximization: Greedy Beats 1/2 in Random Order", 2017\) establishes the current state of the art and provides the analytical framework you should build upon.

# Prophet Inequality for Subadditive CA

**\#\# Constant-Factor Prophet Inequality for Subadditive Combinatorial Auctions via Static Item Pricing**

**\#\#\# Problem Description**

Consider a combinatorial auction with a set $M$ of $m$ items and a set $N$ of $n$ buyers. Each buyer $i \\in N$ has a valuation function $v\_i : 2^M \\to \\mathbb{R}\_{\\geq 0}$. We assume that each $v\_i$ is drawn independently from a known prior distribution $\\mathcal{D}\_i$. The buyers arrive online in a fixed (or adversarial) order.

We focus on **\*\*subadditive\*\*** valuations, meaning that for any buyer $i$ and any two bundles $S, T \\subseteq M$, $v\_i(S \\cup T) \\leq v\_i(S) \+ v\_i(T)$.

The seller wishes to post **\*\*static item prices\*\*** $p \\in \\mathbb{R}\_{\\geq 0}^m$. When buyer $i$ arrives, they observe the remaining set of unsold items $M\_i \\subseteq M$ and the prices $p$, and select a bundle $S\_i \\subseteq M\_i$ that maximizes their quasi-linear utility:  
$$S\_i \\in \\arg\\max\_{S \\subseteq M\_i} \\left( v\_i(S) \- \\sum\_{j \\in S} p\_j \\right)$$

The benchmark is the expected offline optimal social welfare: $\\mathbb{E}\[\\text{OPT}\] \= \\mathbb{E}\\left\[\\max\_{(O\_1, \\dots, O\_n)} \\sum\_{i \\in N} v\_i(O\_i)\\right\]$, where $(O\_1, \\dots, O\_n)$ is a valid partition of the items.

**\#\#\# Research Goal**

Does there exist a universal constant $C \> 0$ such that, for any set of items $M$ and any set of independent subadditive valuation distributions $\\{\\mathcal{D}\_i\\}\_{i \\in N}$, there exists a static item price vector $p \\in \\mathbb{R}\_{\\geq 0}^m$ guaranteeing an expected social welfare of at least $\\frac{1}{C} \\mathbb{E}\[\\text{OPT}\]$?

**\*\*Qualifications and Assumptions:\*\***

\- **\*\*(a) Arrival Order:\*\*** The problem is open even for a fixed and known arrival order. Most results typically work for any (worst-case) arrival order, and some also under adversarial arrival order.  
\- **\*\*(b) Computational Tractability:\*\*** For the core of this open problem, we are entirely unconcerned with computational tractability. The question is purely existential: does such a price vector exist?  
\- **\*\*(c) Tie-Breaking Rules:\*\*** Because buyers may have multiple utility-maximizing bundles, a tie-breaking rule must be specified. Ideally, the pricing scheme should be robust enough that *\*any\** tie-breaking rule (even adversarial) works. However, resolving the problem affirmatively under specific assumptions (e.g., lexicographical tie-breaking, or seller-favorable tie-breaking) would still be highly interesting and a significant step forward, while a negative result that only holds for specific tie-breaking rules would be weaker.

**\#\#\# Known Results**

\- **\*\*Constant-Factor for XOS via Static Pricing:\*\*** Feldman, Gravin, and Lucier (2014) demonstrate a constant-factor approximation for the narrower class of XOS (fractionally subadditive) valuations using static posted prices. This serves as the blueprint for the type of result we hope to achieve (or refute) for general subadditive valuations. The factor 2 impossibility from the classic single-item prophet inequality is the best known impossibility. Showing a stronger lower bound would be interesting as well.

\- **\*\*SOTA Static Pricing for Subadditive:\*\*** If we restrict ourselves strictly to static posted pricing, the current state-of-the-art for subadditive valuations yields an $\\mathcal{O}(\\log \\log m)$ approximation (Dütting, Feldman, Kesselheim, and Lucier, 2020).

\- **\*\*Constant-Factor for Subadditive (Non-Static):\*\*** A breakthrough by Correa and Cristi (2023) gives an $\\mathcal{O}(1)$ prophet inequality for subadditive valuations. However, this result is not achieved via static posted pricing, but rather relies on more complex dynamic pricing mechanisms.

\- **\*\*General Reductions to Posted Prices:\*\*** Recent work (Dütting et al., 2023\) establishes a general reduction that can turn prophet inequalities into posted-price mechanisms. However, this reduction inherently relies on dynamic pricing and does not guarantee the existence of *\*static\** prices.

\- **\*\*Polynomial-Time Results for XOS:\*\*** While our open problem suspends computational constraints, it is worth noting that for XOS valuations, constant-factor approximations via static pricing can be achieved in polynomial time given suitable oracle access to the valuations (Dütting, Feldman, Kesselheim, and Lucier, 2016).

**\#\#\# Key References**

Download the following papers read them carefully before proceeding.

1\. Feldman, Gravin, and Lucier, "Combinatorial Auctions via Posted Prices" (2014). Available at https://arxiv.org/pdf/1411.4916 — establishes the constant-factor result for XOS via static pricing.

2\. Dütting, Feldman, Kesselheim, and Lucier, "Prophet Inequalities Made Easy" (2020). Available at https://arxiv.org/pdf/2004.09784 — current state-of-the-art $\\mathcal{O}(\\log \\log m)$ approximation for subadditive via static pricing.

3\. Correa and Cristi, "Prophet Inequalities for Subadditive Combinatorial Auctions" (2023). Available at https://www.dii.uchile.cl/\~jcorrea/papers/Manuscripts/2023CC.pdf — breakthrough $\\mathcal{O}(1)$ prophet inequality for subadditive (non-static).

Also consult:  
\- "Prophet Inequalities vs. Posted-Price Mechanisms" (2023). Available at https://livrepository.liverpool.ac.uk/3177238/1/Prophet\_Pricing\_Accepted.pdf — general reduction from prophet inequalities to dynamic posted prices.  
\- Dütting, Feldman, Kesselheim, and Lucier, "Polynomial-Time Approximation Schemes for XOS Combinatorial Auctions" (2016). Available at https://arxiv.org/pdf/1612.03161 — polynomial-time results for XOS.

# Truthful Mechanism for Submodular CA

**\#\# Truthful Mechanism for Submodular Combinatorial Auctions: Closing the Gap to $O(\\log \\log m)$**

**\#\#\# Problem Description**

In a **\*\*combinatorial auction\*\***, there is a set $M$ of $m$ indivisible items and a set $N$ of $n$ bidders. Each bidder $i \\in N$ has a **\*\*monotone submodular\*\*** valuation function $v\_i : 2^M \\to \\mathbb{R}\_{\\geq 0}$ with $v\_i(\\emptyset) \= 0$, satisfying:  
\- **\*\*Monotonicity\*\***: $v\_i(S) \\leq v\_i(T)$ for all $S \\subseteq T \\subseteq M$.  
\- **\*\*Submodularity (diminishing returns)\*\***: $v\_i(S \\cup \\{j\\}) \- v\_i(S) \\geq v\_i(T \\cup \\{j\\}) \- v\_i(T)$ for all $S \\subseteq T \\subseteq M$ and $j \\notin T$.

The goal is to find an allocation $(S\_1, S\_2, \\ldots, S\_n)$ that is a partition of the items among the bidders, maximizing the **\*\*social welfare\*\***:  
$$\\text{maximize} \\quad \\sum\_{i=1}^n v\_i(S\_i).$$

The valuations are private information of the bidders, accessed through **\*\*demand oracle queries\*\***: given a price vector $p \\in \\mathbb{R}^m\_{\\geq 0}$, the oracle for bidder $i$ returns $S^\* \\in \\arg\\max\_{S \\subseteq M} \\left(v\_i(S) \- \\sum\_{j \\in S} p\_j\\right)$.

A mechanism is **\*\*(universally) truthful\*\*** if it is a probability distribution over deterministic truthful mechanisms—i.e., no bidder can improve their outcome by misreporting their valuation, regardless of the mechanism's random coins.

The **\*\*approximation ratio\*\*** of a truthful mechanism is the worst-case ratio between the expected social welfare achieved by the mechanism and the optimal social welfare $\\text{OPT} \= \\max\_{(S\_1, \\ldots, S\_n)} \\sum\_{i=1}^n v\_i(S\_i)$.

**\#\#\# Known Results**

\- **\*\*Non-Truthful Algorithms:\*\*** Without the truthfulness constraint, monotone submodular welfare maximization can be approximated to within a factor of $1 \- 1/e \\approx 0.632$ using the continuous greedy algorithm with value queries (Vondrák, STOC 2008). This is tight in the value oracle model.

\- **\*\*Known Truthful Mechanisms:\*\*** The quest for truthful mechanisms with good approximation ratios has a long history:  
 \- $O(\\sqrt{m})$-approximation (Dobzinski, Nisan, and Schapira, 2005\)  
 \- $O(\\log^2 m)$-approximation (Dobzinski, Nisan, and Schapira, 2006\)  
 \- $O(\\log m \\cdot \\log \\log m)$-approximation (Dobzinski, 2007\)  
 \- $O(\\log m)$-approximation (Krysta and Vöcking, 2012\)  
 \- $O(\\sqrt{\\log m})$-approximation (Dobzinski, 2016\)  
 \- $O((\\log \\log m)^3)$-approximation (Assadi, Kesselheim, and Singla, 2021))

For the special case of **\*\*submodular\*\*** bidders, an improved analysis yields an $O((\\log \\log m)^2)$-approximation. This is the current state of the art.

**\#\#\# Research Goal**

Design a **\*\*(universally) truthful\*\*** mechanism for combinatorial auctions with **\*\*monotone submodular valuations\*\*** that achieves an $O(\\log \\log m)$-approximation to the optimal social welfare, using a polynomial number of demand oracle queries. That is, construct a mechanism such that for any instance:  
$$\\mathbb{E}\\left\[\\sum\_{i=1}^n v\_i(S\_i)\\right\] \\geq \\Omega\\left(\\frac{1}{\\log \\log m}\\right) \\cdot \\text{OPT},$$  
where the expectation is over the mechanism's internal randomness.

This would improve upon the current best $O((\\log \\log m)^2)$-approximation of Assadi, Kesselheim, and Singla (SODA 2021\) by removing one $\\log \\log m$ factor. Possible directions include:  
\- Tightening the analysis of the existing mechanism from Assadi, Kesselheim, and Singla, which loses a $\\log \\log m$ factor in bounding the welfare contribution across "levels" of their hierarchical grouping scheme.  
\- Designing a new mechanism with a refined hierarchical decomposition or bundling strategy that avoids the extra logarithmic loss.  
\- Combining ideas from the non-truthful $O(\\log \\log m)$-approximation algorithms (which exist for the broader subadditive class via prophet inequality techniques) with truthfulness-preserving reductions.

**\#\#\# Key References**

Download the following paper and read it carefully before proceeding.

1\. Assadi, Kesselheim, and Singla, "Improved Truthful Mechanisms for Subadditive Combinatorial Auctions: Breaking the Logarithmic Barrier" (SODA 2021). Available at https://arxiv.org/pdf/2010.01420 — establishes the current-best $O((\\log \\log m)^3)$ approximation for subadditive and $O((\\log \\log m)^2)$ for submodular bidders.

Also consult:  
\- Dobzinski, "Breaking the Logarithmic Barrier for Truthful Combinatorial Auctions with Submodular Bidders" (STOC 2016). Available at https://arxiv.org/pdf/1602.08194 — the $O(\\sqrt{\\log m})$ predecessor mechanism.  
\- Vondrák, "Optimal Approximation for the Submodular Welfare Problem in the Value Oracle Model" (STOC 2008\) — the non-truthful $1 \- 1/e$ benchmark.  
\- Dughmi and Vondrák, "Limitations of Randomized Mechanisms for Combinatorial Auctions" (Games and Economic Behavior, 2015). Available at https://arxiv.org/pdf/1011.3321 — impossibility results for truthful mechanisms.

# Disproving Strong MSP

**\#\# Disproving the Strong Matroid Secretary Conjecture**

**\#\#\# Problem Description**

A **\*\*matroid\*\*** $\\mathcal{M} \= (E, \\mathcal{I})$ consists of a finite ground set $E$ with $|E| \= n$ and a collection $\\mathcal{I} \\subseteq 2^E$ of *\*independent sets\** satisfying:  
\- **\*\*Hereditary\*\***: $\\emptyset \\in \\mathcal{I}$, and if $A \\subseteq B \\in \\mathcal{I}$ then $A \\in \\mathcal{I}$.  
\- **\*\*Exchange\*\***: If $A, B \\in \\mathcal{I}$ with $|A| \< |B|$, there exists $e \\in B \\setminus A$ with $A \\cup \\{e\\} \\in \\mathcal{I}$.

The *\*rank\** $r \= r(\\mathcal{M})$ is the size of any maximal independent set (called a *\*base\**). The **\*\*uniform matroid\*\*** $U\_{n,k}$ has ground set of size $n$ and independent sets $\\mathcal{I} \= \\{S \\subseteq E : |S| \\leq k\\}$.

In the **\*\*Matroid Secretary Problem (MSP)\*\***, each element $e \\in E$ has a non-negative weight $w(e) \\geq 0$. The elements arrive in a **\*\*uniformly random order\*\*** — a permutation $\\sigma$ drawn uniformly from $S\_n$. Upon arrival of element $e$, the algorithm observes $w(e)$ and must immediately and irrevocably decide to **\*\*accept\*\*** or **\*\*reject\*\*** $e$. The constraint is that the set of accepted elements must remain independent in $\\mathcal{M}$ at all times. The objective is to maximize the total weight of accepted elements.

The **\*\*competitive ratio\*\*** of an algorithm $\\mathcal{A}$ on matroid $\\mathcal{M}$ is:  
$$\\alpha(\\mathcal{A}, \\mathcal{M}) \= \\inf\_{w : E \\to \\mathbb{R}\_{\\geq 0}} \\frac{\\mathbb{E}\_\\sigma\[\\mathcal{A}(\\mathcal{M}, w, \\sigma)\]}{\\mathrm{OPT}(\\mathcal{M}, w)}$$

where $\\mathrm{OPT}(\\mathcal{M}, w) \= \\max\_{B \\in \\mathcal{B}} \\sum\_{e \\in B} w(e)$ is the maximum weight of any base, and the expectation is over the random arrival order $\\sigma$. The **\*\*optimal competitive ratio\*\*** for matroid $\\mathcal{M}$ is:  
$$\\alpha^\*(\\mathcal{M}) \= \\sup\_{\\mathcal{A}} \\alpha(\\mathcal{A}, \\mathcal{M}).$$

**\#\#\# The Conjectures**

**\*\*Matroid Secretary Conjecture (MSC)\*\*** (Babaioff, Immorlica, and Kleinberg, 2007): There exists a universal constant $c \> 0$ such that for every matroid $\\mathcal{M}$, $\\alpha^\*(\\mathcal{M}) \\geq c$.

**\*\*Strong Matroid Secretary Conjecture (SMSC)\*\***: For every matroid $\\mathcal{M}$, $\\alpha^\*(\\mathcal{M}) \\geq 1/e$.

The SMSC generalizes the classical secretary problem: for $U\_{n,1}$ (the rank-1 uniform matroid — pick at most one element), the optimal competitive ratio is exactly $1/e$ as $n \\to \\infty$, achieved by the classic "wait-then-pick" algorithm that rejects the first $\\lfloor n/e \\rfloor$ elements and then accepts the first element exceeding all previously seen values. Since any matroid contains $U\_{n,1}$ as a restriction (by considering a single element), $1/e$ is the best possible target for a universal guarantee.

**\#\#\# Known Results**

**\*\*General algorithms (upper bounds on achievable ratio):\*\***

| Algorithm | Competitive Ratio | Reference |  
|:----------|:-----------------|:----------|  
| Greedy sampling | $O(1/\\log r)$ | Babaioff, Immorlica, Kleinberg (2007) |  
| Improved greedy | $O(1/\\sqrt{\\log r})$ | Chakraborty and Lachish (2012) |  
| Hierarchical sampling | $O(1/\\log \\log r)$ | Lachish (2014) |  
| Simpler hierarchical | $O(1/\\log \\log r)$ (better constant) | Feldman, Svensson, Zenklusen (2015) |

The best known competitive ratio for general matroids is $\\Omega(1/\\log \\log r)$. The MSC (even the weak $O(1)$ version) remains open.

**\*\*Specific matroid classes with $O(1)$-competitive algorithms:\*\***

| Matroid Class | Best Known Ratio | Reference |  
|:-------------|:----------------|:----------|  
| Uniform $U\_{n,k}$ | $1/e$ (as $n \\to \\infty$, fixed $k/n$) | Kleinberg (2005) |  
| Partition matroids | $O(1)$ | Babaioff, Immorlica, Kleinberg (2007) |  
| Graphic matroids | $\\approx 3.95$ | Korula and Pál (2009); improved in subsequent work |  
| Transversal matroids | $O(1)$ | Dimitrov and Plaxton (2012); Kesselheim et al. (2013) |  
| Laminar matroids | $O(1)$ | Im and Wang (2011); Jaillet, Soto, Zenklusen (2013) |  
| Regular matroids | $O(1)$ | Dinitz and Kortsarz (2014) |  
| Gammoids | $O(1)$ | Soto (2011) |

**\*\*Lower bounds (impossibility results):\*\***  
\- The classical secretary problem gives $\\alpha^\*(U\_{n,1}) \= 1/e$, which is **\*\*tight\*\***: no algorithm achieves competitive ratio $\> 1/e$ for $U\_{n,1}$, and the optimal algorithm matches this.  
\- There are **\*\*no known impossibility results\*\*** ruling out a $1/e$-competitive algorithm when the matroid is known. The SMSC is neither proved nor disproved.

**\#\#\# Research Goal**

**\*\*Primary Goal:\*\*** Disprove the Strong Matroid Secretary Conjecture by exhibiting a  matroid $\\mathcal{M}$ for which no online algorithm can achieve competitive ratio $1/e$. Formally, show that there exists a matroid $\\mathcal{M}$ and a constant $\\varepsilon \> 0$ such that:  
$$\\alpha^\*(\\mathcal{M}) \\leq \\frac{1}{e} \- \\varepsilon.$$

That is, for every algorithm $\\mathcal{A}$, there exists a weight function $w$ such that:  
$$\\frac{\\mathbb{E}\_\\sigma\[\\mathcal{A}(\\mathcal{M}, w, \\sigma)\]}{\\mathrm{OPT}(\\mathcal{M}, w)} \\leq \\frac{1}{e} \- \\varepsilon.$$

**\*\*A Potentially Easier Goal (Ordinal MSP):\*\*** Disprove the SMSC in the ordinal (comparison-based) model, where the algorithm only observes relative orderings between element weights, not their actual values. This is described in detail below.

\---

**\#\#\# The Ordinal Matroid Secretary Problem**

In the **\*\*ordinal MSP\*\***, the algorithm does not see numerical weights. Instead, upon arrival of element $e\_t$ at time $t$, the algorithm learns only the **\*\*relative ranking\*\*** of $e\_t$ among all elements seen so far: i.e., it knows the total order on $\\{e\_{\\sigma(1)}, \\ldots, e\_{\\sigma(t)}\\}$ induced by $w$, but not the values $w(e\_{\\sigma(i)})$ themselves.

An **\*\*ordinal algorithm\*\*** is one whose accept/reject decisions depend only on:  
\- The matroid $\\mathcal{M}$,  
\- The set of previously seen elements and their relative order,  
\- The rank of the current element among those seen so far,  
\- Internal randomness.

The **\*\*ordinal competitive ratio\*\*** is:  
$$\\alpha^\*\_{\\mathrm{ord}}(\\mathcal{M}) \= \\sup\_{\\mathcal{A} \\text{ ordinal}} \\;\\inf\_{w : E \\to \\mathbb{R}\_{\\geq 0}} \\;\\frac{\\mathbb{E}\_\\sigma\[\\mathcal{A}(\\mathcal{M}, w, \\sigma)\]}{\\mathrm{OPT}(\\mathcal{M}, w)}.$$

Since ordinal algorithms are a subset of all algorithms, $\\alpha^\*\_{\\mathrm{ord}}(\\mathcal{M}) \\leq \\alpha^\*(\\mathcal{M})$ for all $\\mathcal{M}$.

**\*\*Key observation for rank 1:\*\*** For $U\_{n,1}$, the classical optimal algorithm ("skip $\\lfloor n/e \\rfloor$, then pick the next record") is inherently ordinal — it uses only comparisons, never actual values. Therefore $\\alpha^\*\_{\\mathrm{ord}}(U\_{n,1}) \= \\alpha^\*(U\_{n,1}) \= 1/e$, and there is no separation between ordinal and cardinal algorithms for rank 1\.

**\*\*Why ordinal is easier to attack for higher rank:\*\*** For matroids of rank $r \\geq 2$, cardinal algorithms can use the actual numerical weights to set thresholds, estimate the optimal value, or calibrate acceptance probabilities — strategies unavailable to ordinal algorithms. An ordinal algorithm that must select multiple elements faces an inherent information bottleneck: knowing only that element $e$ is the "3rd best seen so far" provides no information about how $w(e)$ compares to the maximum weight, which affects how much accepting $e$ costs in the competitive ratio.

**\*\*Goal for the ordinal version:\*\*** Find a matroid $\\mathcal{M}$ of rank $r \\geq 2$ such that:  
$$\\alpha^\*\_{\\mathrm{ord}}(\\mathcal{M}) \< \\frac{1}{e}.$$

This means showing that for every ordinal algorithm $\\mathcal{A}$, there exists a weight vector $w$ (consistent with the orderings the algorithm might observe) such that $\\mathbb{E}\[\\mathcal{A}\]/\\mathrm{OPT} \< 1/e \- \\varepsilon$.

\> \[\!NOTE\]  
\> An ordinal impossibility result would not directly disprove the SMSC (which allows cardinal algorithms), but it would:  
\> 1\. Establish a **\*\*separation\*\*** between ordinal and cardinal algorithms for the MSP, which is unknown today.  
\> 2\. Show that the $1/e$ barrier of the classical secretary problem is **\*\*not robust\*\*** to matroid constraints under ordinal information.  
\> 3\. Provide key structural insights about which matroids are hard and why, potentially guiding attacks on the full (cardinal) SMSC.

**\#\#\# Key References**

1\. Babaioff, Immorlica, and Kleinberg, "Matroids, Secretary Problems, and Online Mechanisms" (SODA 2007, JACM 2018). Available at https://arxiv.org/abs/0709.4432 — introduced the MSP and both the MSC and SMSC.

2\. Feldman, Svensson, and Zenklusen, "A Simple $O(\\log\\log(\\mathrm{rank}))$-Competitive Algorithm for the Matroid Secretary Problem" (SODA 2015, Math. Oper. Res. 2018). Available at https://arxiv.org/abs/1404.4473 — current best general algorithm.

3\. Lachish, "O(log log Rank) Competitive Ratio for the Matroid Secretary Problem" (FOCS 2014). Available at https://arxiv.org/abs/1411.4700 — first $O(\\log\\log r)$ algorithm.

4\. Kleinberg, "A Multiple-Choice Secretary Algorithm with Applications to Online Auctions" (SODA 2005). — The $k$-secretary problem for uniform matroids.

5\. Korula and Pál, "Algorithms for Secretary Problems on Graphs and Hypergraphs" (ICALP 2009). — $O(1)$-competitive algorithms for graphic matroids.

6\. Dinitz and Kortsarz, "Matroid Secretary for Regular and Decomposable Matroids" (ICALP 2014, SICOMP 2014). — Extended to regular matroids via Seymour's decomposition.

7\. Soto, "Matroid Secretary Problem in the Random-Assignment Model" (SODA 2011, SICOMP 2013). Available at https://arxiv.org/abs/1107.2462 — results for gammoids and the random-assignment variant.

8\. Feldman, Svensson, and Zenklusen, "Online Contention Resolution Schemes" (SODA 2016, SICOMP 2021). Available at https://arxiv.org/abs/1508.00142 — OCRSs and their connection to the MSP.

9\. Dynkin, "The Optimum Choice of the Instant for Stopping a Markov Process" (Soviet Math. Doklady, 1963). — The classical $1/e$ result for the secretary problem.

# Revenue Optimal DSIC Auction

**\#\# Provably Revenue Optimal DSIC Sealed-Bid Auctions**

**\#\#\# Problem Description**

We consider **\*\*sealed-bid auctions\*\*** with a set of $n$ bidders,  
$N=\\{1,\\ldots,n\\}$, and $m$ items, $M=\\{1,\\ldots,m\\}$, with $m\>1$ and $n\>1$.  
Bidder $i$ has a valuation function $v\_i:2^M\\rightarrow \\mathbb{R}\_{\\ge 0}$.  
Valuations are continuous. We consider both **\*\*additive valuations\*\***, where  
$v\_i(S)=\\sum\_{j\\in S}v\_i(j)$, and **\*\*unit-demand valuations\*\***, where  
$v\_i(S)=\\max\_{j\\in S}v\_i(j)$.

Valuation $v\_i$ is drawn independently from a known distribution $F\_i$ over  
$V\_i$, with $v\_i(j)\\in\[0,v\_{\\max}\]$ for all $i,j$. Let $\\bm F=(F\_1,\\ldots,F\_n)$,  
$V=\\prod\_i V\_i$, and write $\\bm v\_i=(v\_i(1),\\ldots,v\_i(m))$.

An auction is a pair $(g,p)$, where $g:V\\rightarrow \\mathcal X$ is a feasible  
allocation rule and $p\_i:V\\rightarrow \\mathbb{R}\_{\\ge 0}$ is bidder $i$'s  
payment rule. Let $g\_i(\\bm b)\\subseteq M$ denote the bundle allocated to bidder  
$i$ at bid profile $\\bm b=(b\_1,\\ldots,b\_n)$. Bidder $i$'s utility is  
$u\_i(v\_i;\\bm b)=v\_i(g\_i(\\bm b))-p\_i(\\bm b)$. In full generality, the allocation  
rule may be randomized.

The auction is **\*\*dominant-strategy incentive compatible (DSIC)\*\***, or  
*\*strategy-proof (SP)\**, if $u\_i(v\_i;(v\_i,\\bm b\_{-i}))\\geq u\_i(v\_i;(b\_i,\\bm  
b\_{-i}))$ for all $i\\in N$, $v\_i,b\_i\\in V\_i$, and $\\bm b\_{-i}\\in V\_{-i}$. It is  
*\*individually rational (IR)\** if $u\_i(v\_i;(v\_i,\\bm b\_{-i}))\\geq 0$ for all $i\\in  
N$, $v\_i\\in V\_i$, and $\\bm b\_{-i}\\in V\_{-i}$.

The optimal auction design problem is to identify a DSIC and IR auction  
maximizing expected revenue:

$\\mathcal{R}(\\bm F)=\\sup\_{(g,p)\\in \\mathrm{DSIC}\\cap \\mathrm{IR}}\\mathbb{E}\_{\\bm  
v\\sim \\bm F}\\left\[\\sum\_{i=1}^n p\_i(\\bm v)\\right\]$.

**\#\#\# Research Goal**

(1) **\*\*Computational Goal\*\***: For some continuous distribution $\\bm F$, some $n\>1$  
   and $m\>1$, learn an auction $(g^\\star,p^\\star)$ expressed by neural networks  
   or other representations such that $\\mathbb{E}\_{\\bm v\\sim \\bm F}\\left\[\\sum\_i  
   p\_i^\\star(\\bm v)\\right\]=\\mathcal{R}(\\bm F)$, together with a rigorous proof  
   of DSIC, IR, and revenue optimality.  
(2) **\*\*Characterization Goal\*\***: For some continuous distribution $\\bm F$, some  
   $n\>1$ and $m\>1$, give an explicit characterization of a revenue-optimal DSIC  
   and IR auction $(g^\\star,p^\\star)$.

**\#\#\# Challenges**

Myerson’s seminal work (1981) characterizes optimal auctions for the sale of a  
single item. Within the class of DSIC, multi-item auctions, the only analytical  
results of which we are aware pertain either to variants of the single-bidder  
setting, including Daskalakis et al., 2015; Giannakopoulos and Koutsoupias,  
2014; Manelli and Vincent, 2006; Pavlov, 2010, or to the setting with two items  
whose value distributions each have support of size two (Yao, 2017). Obtaining  
provably revenue-optimal DSIC auctions in multi-bidder, multi-item settings,  
with continuous value distributions, remains a long-standing open challenge.

**\#\#\# Relation to Known Results**

Neural mechanism design methods, termed "differentiable economics," such as  
RochetNet (Dütting et al., 2024), GemNet (Wang, Jiang, and Parkes, 2024),  
Lottery AMA (Curry, Sandholm, and Dickerson, 2023), AMenuNet (Duan et al.,  
2023), and MenuNet (Shen, Tang, and Zuo, 2019\) can search directly over exactly  
strategy-proof auction classes and produce interpretable candidate mechanisms.  
There is also progress on neural computation methods for computing dual  
certificates on optimal revenue (Jiang, Parkes, and Wang, 2026). The open  
challenge, for the $m\>1, n\>1$ case, is to turn such AI-discovered mechanisms  
into provably optimal results, through either a computational or  
characterization-based path.

**\#\#\# Key References**

\*   Cai, Yang, Constantinos Daskalakis, and S. Matthew Weinberg. "An algorithmic  
   characterization of multi-dimensional mechanisms." Proceedings of the  
   forty-fourth annual ACM symposium on Theory of computing. 2012\.  
\*   Curry, Michael, Tuomas Sandholm, and John Dickerson. "Differentiable  
   economics for randomized affine maximizer auctions." Proceedings of the  
   Thirty-Second International Joint Conference on Artificial Intelligence.  
   2023\.  
\*   Daskalakis, Constantinos, Alan Deckelbaum, and Christos Tzamos. "Strong  
   duality for a multiple-good monopolist." Proceedings of the Sixteenth ACM  
   Conference on Economics and Computation. 2015\.  
\*   Duan, Zhijian, Haoran Sun, Yurong Chen, and Xiaotie Deng. "A scalable neural  
   network for DSIC affine maximizer auction design." Advances in Neural  
   Information Processing Systems 36 (2023): 56169-56185.  
\*   Dütting, Paul, Zhe Feng, Harikrishna Narasimhan, David C. Parkes, and Sai  
   Srivatsa Ravindranath. "Optimal auctions through deep learning: Advances in  
   differentiable economics." Journal of the ACM 71.1 (2024): 1-53.  
\*   Giannakopoulos, Yiannis, and Elias Koutsoupias. "Duality and optimality of  
   auctions for uniform distributions." Proceedings of the fifteenth ACM  
   conference on Economics and computation. 2014\.  
\*   Jiang, Yanchen, David C. Parkes, and Tonghan Wang. "Duality for Optimal  
   Multi-Item, Multi-Bidder Auction Design: Revenue Certificates through Deep  
   Learning." Proceedings of the 27th ACM Conference on Economics and  
   Computation. 2026\.  
\*   Manelli, Alejandro M., and Daniel R. Vincent. "Bundling as an optimal  
   selling mechanism for a multiple-good monopolist." Journal of Economic  
   Theory 127.1 (2006): 1-35.  
\*   Myerson, Roger B. "Optimal auction design." Mathematics of operations  
   research 6.1 (1981): 58-73.  
\*   Pavlov, Gregory. "Optimal mechanism for selling two goods." The B.E. Journal  
   of Theoretical Economics 11.1 (2011).  
\*   Rochet, Jean-Charles. "A necessary and sufficient condition for  
   rationalizability in a quasi-linear context." Journal of Mathematical  
   Economics 16.2 (1987): 191-200.  
\*   Shen, Weiran, Pingzhong Tang, and Song Zuo. "Automated Mechanism Design via  
   Neural Networks." Proceedings of the 18th International Conference on  
   Autonomous Agents and MultiAgent Systems. 2019\.  
\*   Wang, Tonghan, Yanchen Jiang, and David C. Parkes. "GemNet: Menu-Based,  
   Strategy-Proof Multi-Bidder Auctions Through Deep Learning." Proceedings of  
   the 25th ACM Conference on Economics and Computation. 2024\.  
\*   Yao, Andrew Chi-Chih. "Dominant-strategy versus bayesian multi-item  
   auctions: Maximum revenue determination and comparison." Proceedings of the  
   2017 ACM Conference on Economics and Computation. 2017\.

# Optimal Deterministic Budget-Balanced Mechanisms

**\#\# Computing Optimal Deterministic Budget-Balanced Mechanisms**

**\#\#\# Problem Description**

We consider the **\*\*automated mechanism design\*\*** problem for a finite set of agents $\\{1,\\ldots,k\\}$. Each agent $i$ has a finite set of types $\\Theta\_i$ with a prior distribution $P\_i$, and there is a finite set of outcomes $O$ (e.g., allocations). Each agent $i$ has a utility function $u\_i:\\Theta\_i\\times O\\rightarrow \\mathbb{Q}$.

A **\*\*deterministic direct-revelation mechanism\*\*** consists of an outcome function $f:\\Theta\_1\\times\\cdots\\times\\Theta\_k\\rightarrow O$ and, for each agent $i$, a payment function $\\pi\_i:\\Theta\_1\\times\\cdots\\times\\Theta\_k\\rightarrow \\mathbb{Q}$ (negative if the agent pays). Let $P$ denote the joint prior over type profiles $\\theta\=(\\theta\_1,\\ldots,\\theta\_k)$.

The mechanism $(f,\\pi)$ must satisfy:  
\- **\*\*Strong budget balance\*\***: $\\sum\_{i=1}^k \\pi\_i(\\theta)=0$ for all $\\theta$.  
\- **\*\*Ex-post individual rationality (IR)\*\***: $\\pi\_i(\\theta)+u\_i(\\theta\_i,f(\\theta))\\geq 0$ for all $i$ and $\\theta$.  
\- **\*\*Dominant-strategy incentive compatibility (DSIC)\*\***: $\\pi\_i(\\theta)+u\_i(\\theta\_i,f(\\theta))\\geq \\pi\_i(\\theta\_{-i},\\theta\_i')+u\_i(\\theta\_i,f(\\theta\_{-i},\\theta\_i'))$ for all $i$, $\\theta$, and $\\theta\_i'\\in\\Theta\_i$.

The objective is to maximize expected social welfare:  
$$\\max\_{f,\\pi}\\;\\sum\_{\\theta}P(\\theta)\\sum\_{i=1}^k u\_i(\\theta\_i,f(\\theta))$$  
subject to the above constraints and the integrality constraint $f(\\theta)\\in O$ for all $\\theta$ (i.e., the mechanism is deterministic).

**\#\#\# Research Goal**

Determine the computational complexity of computing an optimal deterministic mechanism satisfying strong budget balance, ex-post IR, and DSIC, for a constant number of agents $k$. Specifically:

(1) Is the problem solvable in polynomial time (in the sizes of $\\Theta\_i$ and $O$)?

(2) If not, is it NP-hard, and what is the best achievable approximation ratio?

**\#\#\# Known Results**

\- **\*\*Randomized case\*\***: If the mechanism is allowed to randomize over outcomes, the problem reduces to a **\*\*linear program\*\*** (by relaxing the integrality constraint on outcome selection) and is solvable in polynomial time for constant $k$ (Conitzer and Sandholm, 2002; 2004).

\- **\*\*Without payments\*\***: Computing the optimal deterministic mechanism that maximizes social welfare without payments is **\*\*NP-hard\*\***, even for a single agent (Conitzer, 2006).

\- **\*\*Without budget balance\*\***: If payments can be collected by an outside party (e.g., a seller) and need not balance, the problem is trivially solvable in polynomial time via VCG mechanisms.

\- **\*\*Weak budget balance\*\***: The variant where the mechanism may run a surplus, but the surplus is treated as a welfare loss (i.e., money is burned), leads to nontrivial mechanism design problems (Guo and Conitzer, 2008; 2009; Moulin, 2009; de Clippel, Naroditskiy, and Greenwald, 2009).

**\#\#\# Challenges**

The core difficulty is the **\*\*integrality constraint\*\***: the outcome must be selected deterministically for each type profile, turning what would be a linear program into a **\*\*mixed integer linear program\*\***. The interaction between this integrality constraint and the strong budget balance and DSIC constraints makes the problem structurally different from both the randomized mechanism design case (polynomial) and the no-payment case (NP-hard). It remains open whether the presence of payments and budget balance makes the deterministic problem easier or harder than the no-payment variant.

**\#\#\# Key References**

\* Conitzer, Vincent, and Tuomas Sandholm. "Complexity of mechanism design." Proceedings of the 18th Annual Conference on Uncertainty in Artificial Intelligence (UAI). 2002\.  
\* Conitzer, Vincent, and Tuomas Sandholm. "Self-interested automated mechanism design and implications for optimal combinatorial auctions." Proceedings of the ACM Conference on Electronic Commerce (EC). 2004\.  
\* Conitzer, Vincent. "Computational aspects of preference aggregation." PhD thesis, Carnegie Mellon University. 2006\.  
\* de Clippel, Geoffroy, Victor Naroditskiy, and Amy Greenwald. "Destroy to save." Proceedings of the ACM Conference on Electronic Commerce (EC). 2009\.  
\* Guo, Mingyu, and Vincent Conitzer. "Better redistribution with inefficient allocation in multi-unit auctions with unit demand." Proceedings of the ACM Conference on Electronic Commerce (EC). 2008\.  
\* Guo, Mingyu, and Vincent Conitzer. "Worst-case optimal redistribution of VCG payments in multi-unit auctions." Games and Economic Behavior 67.1 (2009): 69-98.  
\* Moulin, Hervé. "Almost budget-balanced VCG mechanisms to assign multiple objects." Journal of Economic Theory 144.1 (2009): 96-119.

# Bayesian Security Games

**\#\# Computing Nash Equilibria in Bayesian Security Games**

**\#\#\# Problem Description**

A **\*\*Bayesian simple security game\*\*** consists of:  
\- A set of **\*\*targets\*\*** $T$.  
\- A number of **\*\*defensive resources\*\*** $r\\leq |T|$ for the defender.  
\- A set of **\*\*attacker types\*\*** $\\Theta$ with a probability distribution over them.  
\- For every target $t\\in T$: defender utilities $u\_1^0(t)$ and $u\_1^1(t)$ with $u\_1^0(t)\\leq u\_1^1(t)$ (the defender prefers that an attacked target is defended), and for every attacker type $\\theta\\in\\Theta$: attacker utilities $u\_2^0(\\theta,t)$ and $u\_2^1(\\theta,t)$ with $u\_2^0(\\theta,t)\\geq u\_2^1(\\theta,t)$ (the attacker prefers that the attacked target is undefended).

The game proceeds as follows. The **\*\*defender\*\*** chooses a subset of $r$ targets to assign her resources to. The **\*\*attacker\*\***, after learning his type $\\theta$, chooses a target $t$ to attack. If no defensive resource was assigned to $t$, the defender and attacker receive utilities $u\_1^0(t)$ and $u\_2^0(\\theta,t)$, respectively. If a defensive resource was assigned to $t$, they receive $u\_1^1(t)$ and $u\_2^1(\\theta,t)$, respectively.

A **\*\*(Bayes-)Nash equilibrium\*\*** is a pair of strategies — a mixed strategy for the defender over subsets of $r$ targets, and a mapping from attacker types to (mixed) target choices — such that neither player can improve their expected utility by unilateral deviation.

**\#\#\# Research Goal**

Determine whether a (Bayes-)Nash equilibrium can be computed in **\*\*polynomial time\*\*** for Bayesian simple security games.

**\#\#\# Known Results**

\- **\*\*Stackelberg vs. Nash\*\***: In the security games literature, the standard solution concept is a **\*\*Stackelberg mixed strategy\*\***, where the defender commits to a mixed strategy first and the attacker best-responds. For general two-player normal-form games, computing Stackelberg equilibria can be done in polynomial time (Conitzer and Sandholm, 2006; von Stengel and Zamir, 2010), while computing Nash equilibria is PPAD-complete (Daskalakis, Goldberg, and Papadimitriou, 2009; Chen, Deng, and Teng, 2009).

\- **\*\*Reversed complexity landscape\*\***: In simple security games — where the normal form has exponential size but the game has compact structure — the situation appears reversed. Computing **\*\*Stackelberg\*\*** mixed strategies is **\*\*NP-hard\*\*** (Li, Korzhyk, Conitzer, and Parr), while Nash equilibrium computation appears easier.

\- **\*\*Non-Bayesian multi-resource variant\*\***: For a simpler, non-Bayesian variant where the attacker has multiple resources, a polynomial-time algorithm for Nash equilibrium exists (Korzhyk, Conitzer, and Parr, 2011).

\- **\*\*Interchangeability\*\***: The (Bayes-)Nash equilibria of these games satisfy the **\*\*interchangeability property\*\***, so equilibrium selection is not an issue — all equilibria yield the same payoffs.

\- **\*\*Algorithmic status\*\***: A seemingly fast algorithm for Bayesian Nash equilibrium exists (Li, Korzhyk, Conitzer, and Parr), but its worst-case polynomial running time has not been established.

**\#\#\# Challenges**

The key difficulty is the **\*\*exponential-size strategy space\*\*** of the defender: the number of pure strategies is $\\binom{|T|}{r}$, which is exponential in $r$. Despite the compact game representation, standard equilibrium computation methods do not directly apply. The existing algorithm exploits the game's structure but its worst-case complexity remains unresolved. The Bayesian aspect (multiple attacker types) further complicates the analysis compared to the non-Bayesian case, where polynomial-time algorithms are known.

**\#\#\# Key References**

\* Chen, Xi, Xiaotie Deng, and Shang-Hua Teng. "Settling the complexity of computing two-player Nash equilibria." Journal of the ACM 56.3 (2009).  
\* Conitzer, Vincent, and Tuomas Sandholm. "Computing the optimal strategy to commit to." Proceedings of the ACM Conference on Electronic Commerce (EC). 2006\.  
\* Daskalakis, Constantinos, Paul Goldberg, and Christos H. Papadimitriou. "The complexity of computing a Nash equilibrium." SIAM Journal on Computing 39.1 (2009): 195-259.  
\* Kiekintveld, Christopher, Manish Jain, Jason Tsai, James Pita, Fernando Ordóñez, and Milind Tambe. "Computing optimal randomized resource allocations for massive security games." Proceedings of the Eighth International Joint Conference on Autonomous Agents and Multi-Agent Systems (AAMAS). 2009\.  
\* Korzhyk, Dmytro, Vincent Conitzer, and Ronald Parr. "Security games with multiple attacker resources." Proceedings of the Twenty-Second International Joint Conference on Artificial Intelligence (IJCAI). 2011\.  
\* von Stengel, Bernhard, and Shmuel Zamir. "Leadership games with convex strategy sets." Games and Economic Behavior 69 (2010): 446-457.

# **EFX**

**\#\# Envy-Freeness up to Any Good (EFX): Approximations, Charity, and Chores**

**\#\#\# Problem Description**

In the **\*\*fair division of indivisible resources\*\***, there is a set $M=\\{1,\\ldots,m\\}$ of items and a set $N=\\{1,\\ldots,n\\}$ of agents. Each agent $i\\in N$ has a valuation function $v\_i:2^M\\rightarrow \\mathbb{R}\_{\\geq 0}$ (for goods) or a cost function $c\_i:2^M\\rightarrow \\mathbb{R}\_{\\geq 0}$ (for chores), typically assumed to be monotone. Common classes of valuations include additive, submodular, and subadditive.

An allocation $A=(A\_1,A\_2,\\ldots,A\_n)$ is a partition of the items among the agents. Because exact envy-freeness is generally unattainable with indivisible items (e.g., allocating a single diamond to two agents), the literature focuses on relaxations. The most promising candidate solution concept is **\*\*Envy-Free up to Any Good (EFX)\*\***.

An allocation is **\*\*EFX for goods\*\*** if no agent envies another after the hypothetical removal of any single good from the envied agent's bundle:  
$$v\_i(A\_i) \\geq v\_i(A\_j \\setminus \\{g\\}) \\quad \\text{for all } i, j \\in N \\text{ and for all } g \\in A\_j.$$

Symmetrically, an allocation is **\*\*EFX for chores\*\*** if an agent's envy toward another is eliminated if any single chore is removed from their own bundle:  
$$c\_i(A\_i \\setminus \\{g\\}) \\leq c\_i(A\_j) \\quad \\text{for all } i, j \\in N \\text{ and for all } g \\in A\_i.$$

Because exact EFX allocations are not guaranteed to exist for all valuation classes, several meaningful variants are studied:

\- **\*\*$\\alpha$-Approximate EFX\*\***: For goods, an allocation is $\\alpha$-EFX (for $\\alpha\\in\[0,1\]$) if $v\_i(A\_i)\\geq \\alpha\\cdot v\_i(A\_j\\setminus\\{g\\})$ for all $i,j\\in N$ and $g\\in A\_j$.

\- **\*\*EFX with Charity\*\***: A partial allocation where a subset of items $C\\subset M$ is left unallocated (donated to "charity"), ensuring the allocation of the remaining items is exactly EFX, while minimizing the size of the charity $|C|$.

**\#\#\# Known Results**

**\*\*Positive Results and Algorithms:\*\***

\- Exact EFX allocations are guaranteed to exist for any number of agents with identical valuations, and for 3 agents with additive valuations (Chaudhury, Garg, and Mehlhorn, 2024).  
\- $1/2$-EFX allocations exist for subadditive valuations (Plaut and Roughgarden, 2020).  
\- For additive valuations, an exact EFX allocation exists that leaves at most $n-2$ items unallocated to charity (Berger et al., 2022). The existence of $(1\-\\varepsilon)$-EFX allocations with $O((n/\\varepsilon)^{1/2})$ charity for additive valuations has also been established (Akrami et al., 2024).  
\- Simulated annealing finds exact EFX allocations for additive valuations with random instances in experiments.

**\*\*Impossibility Results:\*\***

\- Akrami, Mayorov, Mehlhorn, Srinivas, and Weidenbach (2026) used SAT-solving to construct a counterexample showing that exact EFX allocations do not always exist for $n\\geq 3$ agents and $m\\geq n+5$ items with submodular (and general monotone) valuations. They also proved EFX does always exist for 3 agents with up to 7 items.  
\- Mackenzie and Suzuki (2026) provided a compact, human-verifiable, and highly symmetric counterexample for 3 agents and 8 items, refuting EFX existence for the well-structured class of weighted coverage (submodular) valuations.

**\*\*Limits of Approximation:\*\***

\- While $1/2$-EFX allocations are known to exist for subadditive valuations, Mackenzie and Suzuki (2026) established that no universally guaranteed $\\alpha$-EFX allocation exists for any $\\alpha \> 2^{-1/6} \\approx 0.891$ under monotone subadditive valuations.

**\#\#\# Research Goal**

Even though there are now counterexamples demonstrating that exact EFX allocations do not universally exist for non-additive valuations, the quest to identify the limits of fair division remains very rich. Key research directions include:

(1) **\*\*Closing the Approximation Gap\*\***: For monotone submodular and subadditive valuations, the best universal guarantee lies somewhere between $1/2$ (the known constructive lower bound) and $\\approx 0.891$ (the impossibility upper bound). What is the tightest universally guaranteed approximation ratio $\\alpha$?

(2) **\*\*Minimizing Charity\*\***: Design an allocation mechanism that guarantees exact EFX while strictly bounding the number of items given to charity. What is the theoretical minimum number of items that must be given to charity to achieve EFX for submodular valuations?

(3) **\*\*The Additive Frontier\*\***: Do exact EFX allocations always exist for the canonical case of additive valuations for $n\\geq 4$ agents? The existing counterexamples explicitly rely on submodular/subadditive complementarities.

(4) **\*\*EFX for Chores\*\***: Translate these existence questions and approximation barriers to the domain of indivisible chores. Do exact EFX allocations exist for chores under additive costs? What is the best possible approximation ratio $\\alpha$, and what is the minimal charity required to reach exact EFX for chores?

**\#\#\# Key References**

\* Akrami, Hannaneh, Noga Alon, Bhaskar Ray Chaudhury, Jugal Garg, Kurt Mehlhorn, and Ruta Mehta. "EFX: a simpler approach and an (almost) optimal guarantee via rainbow cycle number." Operations Research (2024).  
\* Akrami, Hannaneh, Ivan Mayorov, Kurt Mehlhorn, S. Srinivas, and Christoph Weidenbach. "A Counterexample to EFX: $n \\ge 3$ Agents, $m \\ge n+5$ Items, Submodular Valuations via SAT-Solving." arXiv Preprint (2026). Available at https://arxiv.org/abs/2604.18216.  
\* Amanatidis, Georgios, Haris Aziz, Georgios Birmpas, Aris Filos-Ratsikas, Bo Li, Hervé Moulin, Alexandros A. Voudouris, and Xiaowei Wu. "Fair division of indivisible goods: Recent progress and open questions." Artificial Intelligence (2023).  
\* Chaudhury, Bhaskar Ray, Jugal Garg, and Kurt Mehlhorn. "EFX Exists for Three Agents." Journal of the ACM (2024).  
\* Chaudhury, Bhaskar Ray, Telikepalli Kavitha, Kurt Mehlhorn, and Alkmini Sgouritsa. "A Little Charity Guarantees Almost Envy-Freeness." SIAM Journal on Computing (2021).  
\* Mackenzie, Simon, and Mashbat Suzuki. "Counterexamples to EFX for Submodular and Subadditive Valuations." arXiv Preprint (2026).  
\* Plaut, Benjamin, and Tim Roughgarden. "Almost Envy-Freeness with General Valuations." SIAM Journal on Discrete Mathematics 34.2 (2020): 1039-1068.

# **Multi Unit DSIC**

**\#\# Dominant-Strategy Incentive-Compatible Mechanisms for Multiunit Auctions**

**\#\#\# Problem Description**

**\#\#\#\# Basic Setting**

In a **\*\*multiunit auction\*\*** $m$ identical indivisible items are being auctioned among $n$ bidders.  We are thinking of $n$ as a small number and of $m$ as a very large number, where we would want the running time to be polynomial in $n$ and in the description size of $m$, i.e., in $log(m)$.  Each bidder $i$ has a **\*\*valuation function\*\*** $v\_i : \\{1…m\\} \\rightarrow \\Re\_\+$ that is monotone, $v\_i(j+1) \\ge v\_i(j)$ for every $1 \\le j \< m$.  The goal is to find an allocation $(m\_1, m\_2, …, m\_n)$ with $\\sum\_i m\_i \\le m$, that maximizes **\*\*social welfare\*\***, $\\sum\_i v\_i(m\_i)$.

**\#\#\#\# Model of Computation**

The “input size” here is $m$ real numbers for each of the $n$ players.  As we view $m$ as large we want algorithms whose running time is **\*\*sublinear\*\*** in the input size.  There are various possible models here, the most general of which is the communication complexity model where we count bits of communication between the bidders and the mechanism.  We will proceed in a related simpler model for which the problem is still interesting, the **\*\*value query\*\*** model where the algorithm/mechanism is allowed to query for the value of $v\_i(j)$ of any player $i$ and number of items $j$, and our complexity measure is the total number of queries made.

**\#\#\#\# Incentive Compatibility**

We are looking for a **\*\*deterministic, dominant strategy incentive compatible (DSIC) mechanism\*\***.  A deterministic mechanism $M$ receives as input the valuations $v\_1…v\_n$ and produces as output an allocation $m\_1…m\_n$ (with $\\sum\_i m\_i \\le m$) and payment amounts $p\_1…p\_n$ from the bidders to the auctioneer.  DSIC means that for every player $i$, every valuation $v\_i$ of player $i$, every possible valuations of the other players $v\_{-i}$, and every possible \`\`fake bid’’ $v’\_i$ of player $i$, if we denote by $(m\_i, p\_i)$ the outcome of the mechanism for player $i$ on inputs $(v\_i,v\_{-i})$ and denote by $(m’\_i, p’\_i)$ the outcome of the mechanism for player $i$ on inputs $(v’\_i,v\_{-i})$ then we have $v\_i(m\_i)-p\_i \\ge v\_i(m’\_i)-p’\_i$.

**\#\#\# What is known**

**\#\#\#\# Computational Status**

In terms of pure computation, ignoring any incentive issues, a number of queries that is linear in $m$ (i.e. exponential in $\\log m$) is required to produce the exact welfare-maximizing allocation.  An $\\alpha\=(1\-\\epsilon)$ approximation, for every $\\epsilon\>0$ can be done with polynomially (in $n$ and $\\log m$) many value queries. 

**\#\#\#\# Possibility Results**

\* The case of **\*\*downward sloping\*\*** valuations (where $v\_i(j+2)-v\_i(j+1) \\le v\_i(j+1)-v\_i(j)$ for all $i$ and $j$) as originally studied by Vickrey can be solved exactly with polynomially (in $n$ and $\\log m$) many queries and thus the VCG mechanism gives an optimal allocation for this subcase.

\* For the general case, there exists a DSIC mechanism that uses polynomially (in $n$ and $\\log m$) many value queries and produces an **\*\*$\\alpha\=1/2$ approximation\*\*** \[Dobzinski and Nisan 2007\]. 

\* For the case of **\*\*single minded bidders\*\***, there exists a DSIC mechanism that runs in polynomial (in $n$ and $\\log m$) time and produces an $\\alpha\=(1\-\\epsilon)$ approximation for any $\\epsilon\>0$ \[Briest, Krysta, and Vocking 2011\].

\* If we allow **\*\*randomized\*\*** DSIC mechanisms then there exist such mechanisms that use polynomially (in $n$ and $\\log m$) many value queries and produces an $\\alpha\=(1\-\\epsilon)$ approximation for any $\\epsilon\>0$ \[Dobzinski and Dughmi 2009\] and even universally-truthful ones \[Vocking, 2012\].

\* If we change our computation model and consider complexity where the input is presented in certain simple bidding languages, then an $\\alpha\=(1\-\\epsilon)$ approximation for any $\\epsilon\>0$ is possible in time polynomial in the input size \[Dobzinski and Nisan 2007\].

**\#\#\#\# Impossibility Results**

\* For the case of exactly 2 bidders, DSIC mechanisms that **\*\*always allocate all items\*\***, $m\_1\+m\_2\=m$, cannot produce an $\\alpha$-approximation for any $\\alpha\>1/2$ with $poly(n, \\log m)$ queries \[Lavi, Mu’alem and Nisan 2003\].

\* **\*\*Maximal in Range\*\*** mechanisms (those that fully optimize over a subset of the range of possible allocations) cannot produce an $\\alpha$-approximation for any $\\alpha\>1/2$ with $poly(n, \\log m)$ queries \[Dobzinski and Nisan 2007\].

\* **\*\*Scalable Mechanisms\*\*** (those that are invariant to \`\`units’’:  multiplying all valuations by a constant does not change the allocation) cannot produce an $\\alpha$-approximation for any $\\alpha\>1/2$ with $poly(n, \\log m)$ queries \[Dobzinski and Nisan 2011\].

**\#\#\# Research Goal**

Does there exist a deterministic DSIC mechanism for multiunit auctions that makes at most $poly(n, \\log m)$ value queries on each input and has an approximation factor better than 1/2?  I.e., that for some $\\alpha \> 1/2$ and every $v\_1…v\_n$ satisfies $\\sum\_i v\_i(m\_i) \\ge \\alpha \\sum\_i v\_i(opt\_i)$, where $(m\_1…m\_n)$ is the allocation produced by the mechanism for input $(v\_1…v\_n)$ and $(opt\_1…opt\_n)$ is the welfare-maximizing allocation for $(v\_1…v\_n)$.

This is probably the simplest concrete open problem that directly studies the clash between computational complexity and incentive compatibility which comes into play in cases where exact optimization is not computationally tractable but decent approximations are so.  This class of problems is arguably the most basic class of open problems in the field of Algorithmic Mechanism Design.  The question was asked more or less in this form in \[Dobzinski and Nisan, 2007\] and the same type of question for combinatorial auctions was already mentioned in \[Lehmann, O‘callaghan and Shoham, 2002\].

**\#\#\# Key References**

The following survey contains a detailed description of many of the results stated above and all references.

\* “Algorithmic Mechanism Design: Through the lens of Multiunit auctions” by N. Nisan. In Handbook of Game Theory with Economic Applications, Volume 4, Pages: 477-515, Editors: H. Peyton Young, Shmuel Zamir, Elsevier, 2015\.

The latest impossibility result appears in the following paper.

\* "Multi-unit auctions: beyond Roberts." by S. Dobzinski and N. Nisan. In Proceedings of EC 2011\.

# **Deterministic Subadditive CA**

**\#\# Deterministic Incentive-Compatible Mechanisms for Combinatorial Auctions when Bidders have Subadditive Valuations**

**\#\#\# Problem Description**

**\#\#\#\# Basic Setting**

In a **\*\*combinatorial auction\*\*** $m$ indivisible items are being auctioned among  
$n$ bidders.  Each bidder $i$ has a **\*\*valuation function\*\*** $v\_i : 2^M  
\\rightarrow R$. Each valuation function is monotone (for each item j and bundle  
S, v\_i(S+{j})\\geq v\_i(S)) and normalized (v\_i(\\emptyset)=0). The goal is to find  
an allocation $(S\_1, S\_2, …, S\_n)$ (if i\\neq j then S\_i\\cap S\_j=\\emptyset) that  
maximizes **\*\*social welfare\*\***, $\\sum\_i v\_i(S\_i)$.

**\#\#\#\# Model of Computation**

Our main interest is in the communication complexity model where we count the  
number of bits the bidders need to transfer in order to determine the output. We  
are interested in algorithms with communication complexity poly(m,n).

We consider only deterministic mechanisms.

**\#\#\#\# Incentive Compatibility**

We are looking for a \*\*deterministic, dominant strategy incentive compatible  
(DSIC) mechanism\*\*.  A deterministic mechanism $M$ receives as input the  
valuations $v\_1…v\_n$ and produces as output an allocation $(S\_1…S\_n)$ and  
payments $p\_1…p\_n$ that the participants pay.  DSIC means that for every player  
$i$, every valuation $v\_i$ of player $i$, every possible valuations of the other  
players $v\_{-i}$, and every other possible $v’\_i$ of player $i$, if we denote by  
$(S\_i, p\_i)$ the outcome of the mechanism for player $i$ on inputs  
$(v\_i,v\_{-i})$ and denote by $(S’\_i, p’\_i)$ the outcome of the mechanism for  
player $i$ on inputs $(v’\_i,v\_{-i})$ then we have $v\_i(S\_i)-p\_i \\ge  
v\_i(S’\_i)-p’\_i$.

**\#\#\# What is known**

**\#\#\#\# Computational Status**

Ignoring incentive issues, Feige (2006) provides a 2-approximation algorithm for  
this problem (that is, always finds a solution with social welfare at least half  
of the optimal social welfare). For every constant epsilon\>0, an approximation  
ratio of 2-epsilon requires exponential communication (Dobzinski, Nisan,  
Schapira, 2005)..

**\#\#\#\# Possibility Results**

\*   Dobzinski, Nisan, and Schapira (2005) provide a deterministic DSIC mechanism  
   that provides an approximation ratio of O(sqrt(m)).  
\*   Qiu and Weinberg (2024) improve this ratio to O(sqrt(m/log m)).

**\#\#\#\# Impossibility Results**

\*   Dobzinski (2016) suggests the notion of **\*\*taxation complexity\*\*** of DSIC  
   mechanisms and shows two ways of proving impossibilities: one for two  
   players using simultaneous communication, and the other by showing that the  
   taxation complexity is a lower bound on the communication complexity and  
   utilizing this.  
\*   Assadi, Khandeparkar, Saxena, and Weinberg (2020) are the first to show a  
   separation between the communication complexity of truthful mechanisms and  
   non-truthful mechanisms for combinatorial auctions. They achieve this by  
   applying the taxation complexity framework via the simultaneous  
   communication path. Therefore, their separation is restricted to only two  
   players. Furthermore, it works only for a subclass of subadditive  
   valuations.  
\*   Ron, Thomas, Weinberg, and Zhang (2024) prove a separation for three players  
   mechanisms by giving a lower bound on the taxation complexity of  
   three-player mechanisms. However, the class of valuations they use also  
   includes non-subadditive valuations.

**\#\#\# Research Goal**

Prove or disprove: there is a deterministic DSIC mechanism for combinatorial  
auctions that uses poly(m,n) communication and achieves an approximation ratio  
of 2\.

**\#\#\# Key References**

\*   Shahar Dobzinski: Computational Efficiency Requires Simple Taxation. FOCS  
   2016: 209-218  
\*   Shahar Dobzinski, Noam Nisan, Michael Schapira: Approximation algorithms for  
   combinatorial auctions with complement-free bidders. STOC 2005: 610-618  
\*   Uriel Feige: On maximizing welfare when utility functions are subadditive.  
   STOC 2006: 41-50  
\*   Sepehr Assadi, Hrishikesh Khandeparkar, Raghuvansh R. Saxena, S. Matthew  
   Weinberg: Separating the communication complexity of truthful and  
   non-truthful combinatorial auctions. STOC 2020: 1073-1085  
\*   Shiri Ron, Clayton Thomas, S. Matthew Weinberg, Qianfan Zhang: Communication  
   Separations for Truthful Auctions: Breaking the Two-Player Barrier. FOCS  
   2024: 386-405

# **PCP for PPAD**

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
Papadimitriou, and Rubinstein, 2016\) asserts that the $(\\varepsilon,  
\\delta)$-**\*\*Generalized Circuit\*\*** problem — a relaxation of the standard  
PPAD-complete Generalized Circuit problem in which both the "almost-fixedness"  
and "closeness" parameters are allowed to be positive constants — remains  
PPAD-hard.

**\*\*The $(\\varepsilon, \\delta)$-Generalized Circuit Problem\*\***: Given a  
(succinctly described) arithmetic circuit $C$ over $\[0,1\]^n$ with Lipschitz  
constant at most $1$, find a point $x \\in \[0,1\]^n$ such that each gate $g$ of  
the circuit satisfies its defining constraint to within an additive  
$\\varepsilon$ error, and the output is within $\\delta$ of a fixed point. For  
$\\varepsilon \= \\delta \= 0$ this is the standard PPAD-complete problem. The  
conjecture is that the problem remains PPAD-hard for some constants $\\varepsilon,  
\\delta \> 0$.

**\#\#\# Known Results**

**\*\*Hardness results for Generalized Circuit (equivalently, Nash equilibrium):\*\***

The following results establish PPAD-hardness of the $(\\varepsilon,  
\\delta)$\-Generalized Circuit problem for progressively larger $\\varepsilon$.  
They are stated here in terms of GCircuit; via standard reductions they are  
essentially equivalent to analogous results for $\\varepsilon$-Nash equilibrium  
in constant-degree, constant-action polymatrix games.

\-   Daskalakis, Goldberg, and Papadimitriou (2009) proved PPAD-completeness for  
   $\\varepsilon \= 1/\\exp(n)$.  
\-   Chen, Deng, and Teng (2009) extended PPAD-completeness to  
   $\\varepsilon \= 1/\\mathrm{poly}(n)$.  
\-   Rubinstein (STOC 2015 / SICOMP 2018\) proved PPAD-hardness for  
   $\\varepsilon \= \\Theta(1)$.

**\*\*Partial progress toward a full PCP:\*\***

\-   Rubinstein (FOCS 2016\) proved a BFLS-type PCP for PPAD with query  
   complexity approximately $\\sqrt{n}$ — sublinear in $n$, but still much  
   more than the $O(1)$ queries expected from a full PCP theorem. As a  
   consequence, assuming the Exponential Time Hypothesis for PPAD (ETH for  
   PPAD), computing an $\\varepsilon$-approximate Nash equilibrium in  
   two-player games requires quasi-polynomial time. (Note: under ETH for PPAD  
   this problem provably cannot be PPAD-hard, so the result is a conditional  
   time lower bound rather than a PPAD-hardness reduction.)

**\*\*Motivations and consequences:\*\***  
\-   One of the original motivations for introducing the conjecture (Babichenko,  
   Papadimitriou, and Rubinstein, 2016\) was that it would imply  
   quasipolynomial-hardness, assuming ETH-for-PPAD,  
   of computing $\\varepsilon$-approximate Nash equilibria in two-player games.  
\-   In particular, the full conjecture would imply PPAD-hardness of computing  
   $\\varepsilon$-approximate equilibria in many economic models, including  
   Fisher markets with SPLC utilities, Hylland–Zeckhauser equilibria, and  
   competitive equilibria in exchange economies.  
\-   More broadly, it would give a unified framework for establishing hardness of  
   approximation within PPAD, paralleling the role of the PCP theorem for NP.  
\-   Several conditional hardness results (for markets, fair division, and  
   mechanism design) have been derived assuming the conjecture, demonstrating  
   its power and scope (see, e.g., Deligkas, Fearnley, Hollender, and  
   Melissourgos, 2026; Braverman, Liu, Xue, and Zhou, 2026).

**\#\#\# Research Goal**

Prove (or disprove) the PCP-for-PPAD conjecture: that the $(\\varepsilon,  
\\delta)$-Generalized Circuit problem is PPAD-hard for some constants  
$\\varepsilon, \\delta \> 0$.

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
for PPAD is achievable with $\\approx \\sqrt{n}$ query complexity, but bridging  
the gap to $O(1)$ queries — as the classical PCP theorem achieves for NP —  
remains wide open and appears to require fundamentally new ideas.

**\#\#\# Key References**

\*   Babichenko, Yakov, Christos Papadimitriou, and Aviad Rubinstein. "Can almost  
   everybody be almost happy? PCP for PPAD and the inapproximability of Nash."  
   Proceedings of the Innovations in Theoretical Computer Science Conference  
   (ITCS). 2016\.  
\*   Babichenko, Yakov. "Query complexity of approximate Nash equilibria." Journal  
   of the ACM (2016).  
\*   Babichenko, Yakov, and Aviad Rubinstein. "Communication complexity of  
   approximate Nash equilibria." Proceedings of the Annual ACM Symposium on  
   Theory of Computing (STOC). 2017\.  
\*   Braverman, Mark, Jingyi Liu, Eric Xue, and Chenghan Zhou. "Hardness of  
   approximate Hylland–Zeckhauser equilibria." arXiv preprint arXiv:2606.00951  
   (2026).  
\*   Chen, Xi, Xiaotie Deng, and Shang-Hua Teng. "Settling the complexity of  
   computing two-player Nash equilibria." Journal of the ACM (2009).  
\*   Daskalakis, Constantinos, Paul W. Goldberg, and Christos H. Papadimitriou.  
   "The complexity of computing a Nash equilibrium." SIAM Journal on Computing  
   (2009).  
\*   Deligkas, Argyrios, John Fearnley, Alexandros Hollender, and Themistoklis  
   Melissourgos. "Fisher markets with approximately optimal bundles and the need  
   for a PCP theorem for PPAD." Proceedings of the Annual ACM Symposium on  
   Theory of Computing (STOC). 2026\.  
\*   Göös, Mika, and Aviad Rubinstein. "Near-optimal communication lower bounds  
   for approximate Nash equilibria." SIAM Journal on Computing (2023).  
\*   Rubinstein, Aviad. "Inapproximability of Nash equilibrium." SIAM Journal on  
   Computing (2018). (Conference version: STOC 2015.)  
\*   Rubinstein, Aviad. "Settling the complexity of computing approximate  
   two-player Nash equilibria." Proceedings of the Annual Symposium on  
   Foundations of Computer Science (FOCS). 2016\.

# **Query Complexity of Tarski**

**\#\# Query Complexity of Tarski Fixed Points**

**\#\#\# Problem Description**

**\*\*Tarski's fixed point theorem\*\*** states that every monotone function $f: L  
\\rightarrow L$ on a complete lattice $L$ has a fixed point; moreover, the set of  
fixed points itself forms a complete lattice (and in particular has a least and a  
greatest element). The theorem is among the most widely used existence results in  
economics (e.g., for equilibria of supermodular games), verification (e.g., for  
model checking), and mathematics.

Despite its ubiquity, the **\*\*computational complexity\*\*** of finding such fixed  
points has only recently received systematic study. The computational problem is  
formalized as follows:

**\*\*The Tarski Problem\*\***: Given black-box (query) access to a monotone function  
$f: \[N\]^d \\rightarrow \[N\]^d$ on the $d$-dimensional grid with side length $N$  
(where $x \\leq y$ iff $x\_i \\leq y\_i$ for all $i$), find a fixed point $x^\*$  
such that $f(x^\*) \= x^\*$.

Tarski's theorem guarantees that such a fixed point exists. The fundamental  
question is: \*\*How many queries to $f$ are necessary and sufficient to find a  
fixed point, as a function of $N$ and $d$?\*\*

**\#\#\# Known Results**

**\*\*Upper bounds:\*\***

\-   The naive algorithm based on iterating $f$ starting from the bottom of the  
   lattice requires $O(N^d)$ queries.  
\-   A recursive binary-search algorithm (Dang, Qi, and Ye, 2011\) finds a fixed  
   point in $O(\\log^d N)$ queries.  
\-   Chen and Li (2022) improved this to $O(\\log^{\\lceil (d+1)/2 \\rceil} N)$.  
\-   Chen, Li, and Yannakakis (2026) further improved this to $O(\\log^{\\lceil  
   (d-1)/3 \\rceil \+ 1} N)$ for constant $d$, using a new framework based on  
   safe partial-information functions.

**\*\*Lower bounds:\*\***

\-   Etessami, Papadimitriou, Rubinstein, and Yannakakis (2020) proved that any  
   (even randomized) algorithm requires $\\Omega(\\log^2 N)$ queries for $d \= 2$.  
   This lower bound immediately extends to all $d \\geq 2$.  
\-   Brânzei, Phillips, and Recker (2025) proved an $\\tilde{\\Omega}(d \\cdot  
   \\log^2 N)$ lower bound for general $d$ using a "herringbone" construction.

**\*\*Tight results for small dimensions:\*\***

\-   The query complexity is $\\Theta(\\log^2 N)$ for $d \= 2$ (Etessami et al.,  
   2020), $d \= 3$ (following immediately from the $d=2$ lower bound of Etessami  
   et al. combined with the upper bound of Chen, Li, and Yannakakis, 2026), and  
   $d \= 4$ (Chen, Li, and Yannakakis, 2026).

**\*\*Greatest/least fixed point:\*\***

\-   Finding the greatest or least fixed point requires $\\Theta(d \\cdot N)$  
   queries in the black-box model and is NP-hard in the white-box (circuit)  
   model (Etessami et al., 2020).

**\*\*Complexity-class placement (white-box model):\*\***

\-   In the white-box model (where $f$ is given as a Boolean circuit), the  
   general Tarski problem is in PLS $\\cap$ PPAD (Etessami et al., 2020).  
\-   The Unique Tarski problem (where $f$ is promised to have a unique fixed  
   point) has the same query complexity as the general problem (black-box  
   reduction).

**\*\*Connections to games:\*\***

\-   Computing equilibria of **\*\*supermodular games\*\*** is computationally equivalent  
   to the Tarski problem (Etessami et al., 2020). For two-player supermodular  
   games where one player's strategy space is one-dimensional, an equilibrium  
   can be found in $O(\\log N)$ queries.  
\-   Computing (approximating) the value of **\*\*Condon's stochastic games\*\*** and  
   **\*\*Shapley's stochastic games\*\*** reduces to the Tarski problem.

**\#\#\# Research Goal**

The central open problem is to determine the query complexity of the Tarski  
problem as a function of dimension $d$. It is known that the complexity is  
$\\Theta(\\log^2 N)$ for $d \\leq 4$ and, more generally, $O(\\log^{\\lceil (d-1)/3  
\\rceil \+ 1} N)$ — i.e., $\\Theta(\\log^d N)$ is **\*\*not\*\*** tight. The key question  
is:

**\*\*Is the query complexity $\\log^{\\Theta(d)}(N)$?\*\***

More specifically:

**\*\*(1) Prove stronger lower bounds\*\*** beyond the current $\\tilde{\\Omega}(d \\cdot  
\\log^2 N)$, ideally showing $\\Omega(\\log^{c \\cdot d} N)$ for some constant $c \>  
0$, or

**\*\*(2) Design algorithms with query complexity $\\text{poly}(\\log N)$\*\*** for every  
fixed $d$, breaking the $\\log^{\\Theta(d)} N$ barrier.

The current state of affairs leaves a significant gap: the lower bound is  
$\\tilde{\\Omega}(d \\cdot \\log^2 N)$ while the upper bound is $O(\\log^{\\lceil  
(d-1)/3 \\rceil \+ 1} N)$, which for large $d$ is roughly $O(\\log^{d/3} N)$.

**\#\#\# Challenges**

1\.  **\*\*The curse of dimensionality in lower bounds\*\***: The known $\\Omega(\\log^2  
   N)$ lower bound constructions (based on "herringbone" hard instances) do not  
   straightforwardly extend beyond $\\Theta(\\log^2 N)$. The adversarial  
   functions used exploit coupling between two coordinates, and scaling these  
   constructions to involve genuine $d$-dimensional interaction is the core  
   barrier.

2\.  **\*\*Algorithmic barriers\*\***: The recursive binary-search approach naturally  
   yields $O(\\log^d N)$ by peeling off one dimension at a time. Beating this  
   requires exploiting cross-dimensional structure in the monotone function —  
   recent algorithms do so via "safe partial-information" techniques, but the  
   improvements saturate at roughly $\\log^{d/3} N$.

3\.  **\*\*Unique vs. general Tarski\*\***: While the query complexities of the general  
   and unique-fixed-point versions are equivalent (by black-box reduction), the  
   unique version admits cleaner structural arguments. Understanding whether  
   the uniqueness promise can be leveraged algorithmically in the white-box  
   model is an open direction.

4\.  **\*\*White-box complexity\*\***: The problem lies in PLS $\\cap$ PPAD, but its exact  
   complexity-theoretic status (e.g., whether it is complete for CLS or some  
   other subclass of TFNP) remains unresolved. Resolving this would connect the  
   query-complexity question to circuit-complexity barriers.

**\#\#\# Key References**

\*   Brânzei, Simina, Reed Phillips, and Nicholas Recker. "Query complexity of  
   the Tarski fixed point problem in high dimensions." arXiv preprint (2025).  
\*   Chen, Xi, and Yuhao Li. "Improved upper bounds for finding Tarski fixed  
   points." Proceedings of the ACM Conference on Economics and Computation  
   (EC). 2022\.  
\*   Chen, Xi, Yuhao Li, and Mihalis Yannakakis. "The mystery deepens: On the  
   query complexity of Tarski fixed points." arXiv preprint arXiv:2604.00268  
   (2026).  
\*   Dang, Chuangyin, Qi Qi, and Yinyu Ye. "Computations and complexities of  
   Tarski's fixed points and supermodular games." arXiv preprint (2011).  
\*   Etessami, Kousha, Christos Papadimitriou, Aviad Rubinstein, and Mihalis  
   Yannakakis. "Tarski's theorem, supermodular games, and the complexity of  
   equilibria." Proceedings of the Innovations in Theoretical Computer  
   Science Conference (ITCS). 2020\.  
\*   Fearnley, John, Paul W. Goldberg, Alexandros Hollender, and Rahul Savani.  
   "The complexity of gradient descent: CLS \= PPAD $\\cap$ PLS." Journal of the  
   ACM (2023).

# **Meaning of a Game**

**\#\# Computing the Meaning of a Game**

**\#\#\# Problem Description**

The **\*\*Nash equilibrium\*\*** has been the dominant solution concept in game theory  
since Nash's 1950 existence proof. However, serious computational deficiencies  
have eroded confidence in it as "the meaning of the game": computing a Nash  
equilibrium is PPAD-complete even for two-player games, the multiplicity of  
equilibria resists principled selection, and — most critically — natural  
learning dynamics fail to converge to Nash equilibria. This last objection dates  
back to Shapley (1964), who exhibited a $3 \\times 3$ game in which fictitious  
play cycles, and has been significantly amplified since: it was recently proved  
that no dynamic — locally tractable or not — can converge to precisely the Nash  
equilibria under reasonable convergence requirements.

An alternative paradigm, proposed by Papadimitriou and Piliouras (2019) and  
developed in a series of subsequent works by Biggar, Piliouras, and  
Papadimitriou, redefines the meaning of a game in dynamical terms:

\> **\*\*The meaning of a game\*\*** $G$ is a function $\\mu\_G$ that maps any prior  
\> distribution over the mixed strategy profiles of $G$ to the posterior (limit)  
\> distribution over the **\*\*attractors\*\*** of the **\*\*replicator dynamic\*\*** in $G$.

That is, the meaning of a game is the way in which repeated play transforms the  
collective behavior of the players. The replicator dynamic — gradient descent  
on the players' utilities, equivalently the continuous-time limit of the  
multiplicative weights update algorithm — is a canonical choice, and the concept  
is robust to many other natural learning dynamics.

This reformulation leads to two concrete computational problems:

\> **\*\*(1) Attractor Computation\*\***: Given a game $G$ in normal form, compute a  
\> description of the attractors of the replicator dynamics in $G$.

\> **\*\*(2) Limit Prediction\*\***: Given a game $G$ and a mixed strategy profile $x$,  
\> compute the attractor to which the replicator dynamic converges starting at  
\> $x$.

**\#\#\# Known Results**

**\*\*The unlearnability of Nash equilibria:\*\***

\-   Shapley (1964) showed that fictitious play can cycle and fail to converge to  
   Nash equilibria in simple $3 \\times 3$ games.  
\-   Milionis, Papadimitriou, Piliouras, and Spendlove (PNAS, 2023\) proved an  
   impossibility theorem: there exists a game in which no dynamic whatsoever  
   — locally tractable or not — can converge globally and uniformly to the  
   Nash equilibria.  
\-   Biggar, Papadimitriou, and Piliouras (2026) showed that while two families  
   of Nash-convergent dynamics exist in non-degenerate games, both are  
   intractable to compute locally unless complexity classes collapse ($\\mathsf{P  
   } \= \\mathsf{PPAD}$ or $\\mathsf{NP} \= \\mathsf{RP}$, respectively).  
\-   They further proved that any uniformly Nash-convergent dynamic equipped with  
   a locally tractable Lyapunov function cannot be locally tractable unless  
   $\\mathsf{PPAD} \= \\mathsf{CLS}$, and formulated the \*\*Impossibility  
   Conjecture\*\*: if a locally tractable Nash-convergent dynamic exists for all  
   games, then $\\mathsf{P} \= \\mathsf{PPAD}$.

**\*\*Towards computing attractors:\*\***

\-   The **\*\*Fundamental Theorem of Dynamical Systems\*\*** (Conley, 1978\) guarantees  
   that every dynamical system on a compact space converges to its chain  
   recurrent components, guided by a Lyapunov function. In games, these  
   components — the attractors of the replicator dynamic — are the natural  
   candidates for the "answer" that replaces Nash equilibria.  
\-   Biggar and Shames (ALT, 2023; ALT, 2024\) characterized the attractor of the  
   replicator dynamic in zero-sum games via the *\*response graph\** and \*chain  
   components\*, providing structural descriptions of the limit behavior.  
\-   Biggar and Papadimitriou (ALT, 2026\) showed how to compute stable limit  
   cycles of learning in games, and established *\*sink equilibria\** as the  
   attractors of learning in a general framework.  
\-   Hakim, Milionis, Papadimitriou, and Piliouras (SAGT, 2024\) gave a  
   polynomial-time algorithm for an approximate version of the limit prediction  
   problem: given a game and a starting profile, computing (approximately)  
   which attractor the replicator dynamic converges to.

**\#\#\# Research Goal**

Determine whether the meaning of a game can be computed efficiently:

**\*\*(1)\*\*** Prove or disprove that there is a polynomial-time algorithm which, given  
any game $G$ in normal form, outputs a description of the attractors of the  
replicator dynamics in $G$.

**\*\*(2)\*\*** Prove or disprove that there is a polynomial-time algorithm which, given  
a game $G$ and a mixed strategy profile $x$, computes the limit attractor of  
the replicator dynamic starting at $x$.

**\#\#\# Key References**

\*   Biggar, Oliver, and Christos Papadimitriou. "Computing stable limit cycles  
   of learning in games." arXiv preprint arXiv:2602.11315 (2026).  
\*   Biggar, Oliver, and Christos Papadimitriou. "Sink equilibria and the  
   attractors of learning in games." Proceedings of The 37th International  
   Conference on Algorithmic Learning Theory (ALT). 2026\.  
\*   Biggar, Oliver, Christos Papadimitriou, and Georgios Piliouras. "On the  
   complexity of learning Nash equilibria." arXiv preprint arXiv:2602.16016  
   (2026).  
\*   Biggar, Oliver, and Iman Shames. "The replicator dynamic, chain components  
   and the response graph." Proceedings of The 34th International Conference  
   on Algorithmic Learning Theory (ALT). 2023\.  
\*   Biggar, Oliver, and Iman Shames. "The attractor of the replicator dynamic  
   in zero-sum games." Proceedings of The 35th International Conference on  
   Algorithmic Learning Theory (ALT). 2024\.  
\*   Conley, Charles C. Isolated Invariant Sets and the Morse Index. American  
   Mathematical Society, 1978\.  
\*   Daskalakis, Constantinos, Paul W. Goldberg, and Christos H. Papadimitriou.  
   "The complexity of computing a Nash equilibrium." SIAM Journal on Computing  
   39.1 (2009): 195–259.  
\*   Hakim, Rida, Jason Milionis, Christos Papadimitriou, and Georgios  
   Piliouras. "Swim till you sink: computing the limit of a game." International  
   Symposium on Algorithmic Game Theory (SAGT). 2024\.  
\*   Milionis, Jason, Christos Papadimitriou, Georgios Piliouras, and Kelly  
   Spendlove. "An impossibility theorem in game dynamics." Proceedings of the  
   National Academy of Sciences 120.41 (2023).  
\*   Papadimitriou, Christos, and Georgios Piliouras. "Game dynamics as the  
   meaning of a game." ACM SIGecom Exchanges 16.2 (2019): 53–63.  
\*   Shapley, Lloyd S. "Some topics in two-person games." Advances in Game  
   Theory. Annals of Mathematics Studies 52\. Princeton University Press, 1964\.

