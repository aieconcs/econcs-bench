---
name: Revenue Gap Between Myerson and Anonymous Reserves
contributor: Jerry Anunrojwong
---

## Myerson Auction vs. Anonymous-Reserve Auction

### Problem Description

A seller has one item and $n$ risk-neutral bidders. Bidder $i$'s value
$v_i$ is drawn independently from a known regular distribution $F_i$;
the distributions need not be identical.

Let $\mathrm{OPT}(\mathbf F)$ denote the expected revenue of Myerson's optimal auction for $\mathbf F=(F_1,\ldots,F_n)$.

For a reserve $r\ge 0$, let $\mathrm{AR}_r(\mathbf F)$ denote the expected revenue of the second-price auction that uses the same reserve $r$ for every bidder, and define

$$\mathrm{AR}(\mathbf F) = \sup_{r\ge 0}\mathrm{AR}_r(\mathbf F).$$

The reserve may depend on the full distribution profile, but it must be
anonymous: every bidder faces the same reserve.

Define the worst-case revenue gap

$$\Gamma = \sup_{\substack{n\ge 1\\F_1,\ldots,F_n\ \mathrm{regular}}} \frac{\mathrm{OPT}(\mathbf F)}{\mathrm{AR}(\mathbf F)}.$$

The central question is:

> **What is the exact value of $\Gamma$?**

Equivalently, how much revenue can the fully discriminatory Myerson auction
gain over the best second-price auction constrained to use one common reserve?

With non-identical distributions, Myerson's auction is not generally just a
second-price auction with bidder-specific reserves: it ranks bidders by
distribution-dependent virtual values and can therefore award the item to a
bidder who does not submit the highest raw bid.

### Known Results

If the bidders are i.i.d. from a regular distribution, Myerson's auction is a
second-price auction with a common monopoly reserve, so the ratio is $1$.

For independent, non-identically distributed regular bidders, Hartline and
Roughgarden proved

$$2\le \Gamma\le 4.$$

The upper bound was later improved to $e$.

Jin, Lu, Tang, and Xiao constructed instances proving

$$\Gamma\ge 2.15,$$

disproving the conjecture that the two-bidder lower bound of $2$ was tight.
They also conjectured that the worst-case ratio may be approached only as the
number of bidders tends to infinity.

The best known upper bound follows from anonymous pricing. Let

$$\mathrm{AP}(\mathbf F) = \sup_{p\ge 0} p\left(1-\prod_i F_i(p)\right)$$

be the optimal anonymous posted-price revenue. An anonymous-reserve auction
with reserve $p$ earns at least the corresponding anonymous posted-price revenue, so

$$\mathrm{AR}(\mathbf F)\ge \mathrm{AP}(\mathbf F).$$

Jin, Lu, Qi, Tang, and Xiao proved the tight bound

$$\mathrm{OPT}(\mathbf F) \le \mathcal C^\ast\,\mathrm{AP}(\mathbf F), \qquad \mathcal C^\ast\approx 2.6202.$$

Therefore, the current bounds are

$$\boxed{2.15 \le \Gamma \le \mathcal C^\ast\approx 2.6202}.$$

The upper bound does not use the extra competition revenue that distinguishes
an anonymous-reserve auction from anonymous posted pricing.

### Research Goal

Determine the exact value of $\Gamma$, with matching upper- and lower-bound
constructions.

Related progress would include:

- improving either side of the interval $[2.15, 2.6202]$;
- determining the fixed-$n$ gap $\Gamma_n = \sup_{F_1,\ldots,F_n\ \mathrm{regular}} \frac{\mathrm{OPT}(\mathbf F)}{\mathrm{AR}(\mathbf F)}$;
- proving whether the global supremum requires an unbounded number of
  bidders; or
- reducing the extremal problem to a tractable family of regular
  distributions.

### Key References

- Hartline, Jason D., and Tim Roughgarden. "Simple versus Optimal Mechanisms."
  EC 2009.
  https://www.eecs.northwestern.edu/~hartline/papers/simple-auctions-EC-09.pdf

- Alaei, Saeed, Jason D. Hartline, Rad Niazadeh, Emmanouil Pountourakis, and
  Yang Yuan. "Optimal Auctions vs. Anonymous Pricing." *Games and Economic
  Behavior* 118 (2019): 494--510.
  https://arxiv.org/abs/1507.02615

- Jin, Yaonan, Pinyan Lu, Zhihao Gavin Tang, and Tao Xiao. "Tight Revenue Gaps
  among Simple Mechanisms." *SIAM Journal on Computing* 49.5 (2020):
  927--958.
  https://arxiv.org/abs/1804.00480

- Jin, Yaonan, Pinyan Lu, Qi Qi, Zhihao Gavin Tang, and Tao Xiao. "Tight
  Approximation Ratio of Anonymous Pricing." STOC 2019.
  https://arxiv.org/abs/1811.00763