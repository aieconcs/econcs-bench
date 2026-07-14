# econcs-bench

Benchmark suite of open research challenges in Economics and Computation (EconCS). This repository is associated with the workshop on [AI-Driven Research in EconCS](https://sites.google.com/corp/view/aieconcs26/) held at [EC 2026](https://ec26.sigecom.org/).

## Contributing

Open problems can be submitted directly via pull requests to the GitHub repository.

Each open problem has a folder with a descriptive name, and within it a `PROBLEM.md` file describing the problem. Each file should have preamble metadata in YAML format. The name of the problem is expected, but the contributor and rating fields are optional. For example:

```yaml
---
name: Submodular Welfare Maximization with Demand Oracle
contributor: Renato Paes Leme
rating: Challenging
---
```

### Rating Rubric

Submitters can optionally include a `rating` field in the metadata to indicate the difficulty of the problem. The rating levels are as follows:

| Level | Submitter's Perspective | Expected Effort | Technical Barrier |
| :--- | :--- | :--- | :--- |
| **Approachable** | "The path forward seems relatively clear, but it needs focused execution." | A solid graduate student project or short paper. | Low. Likely solvable with known techniques. |
| **Challenging** | "This will require a dedicated, full-scale research effort." | A standard main-track conference paper. | Medium. Needs novel combinations of existing tools. |
| **Hard** | "I suspect our current standard tools are insufficient for this. In my view, this touches on foundational barriers..." | A major, sustained effort. Unpredictable. | High to Very High. Requires inventing new techniques or a new paradigm. |
| **Unspecified** | Rating not provided. | N/A | N/A |

## Benchmark Problems

| Problem Name | Contributor | Folder / Details |
| :--- | :--- | :--- |
| Bayesian Security Games | Vincent Conitzer | [bayesian-security-games](bayesian-security-games/PROBLEM.md) |
| Black-Box Reductions to DSIC Mechanism Design | Brendan Lucier | [black-box-dsic-mechanism-design](black-box-dsic-mechanism-design/PROBLEM.md) |
| Complexity of Envy-Free Cake Cutting | Ariel Procaccia | [envy-free-cake-cutting-complexity](envy-free-cake-cutting-complexity/PROBLEM.md) |
| Computing the Meaning of a Game | Christos Papadimitriou | [meaning-of-a-game](meaning-of-a-game/PROBLEM.md) |
| Deterministic CA for Subadditive Bidders | Shahar Dobzinski | [deterministic-subadditive-ca](deterministic-subadditive-ca/PROBLEM.md) |
| Disproving Strong MSP | Anonymous Contribution | [disproving-strong-msp](disproving-strong-msp/PROBLEM.md) |
| DSIC Mechanisms for Multi-Unit Auctions | Noam Nisan | [multi-unit-dsic](multi-unit-dsic/PROBLEM.md) |
| EFX Approximation and Charity | Simina Branzei | [efx-approximation-and-charity](efx-approximation-and-charity/PROBLEM.md) |
| EFX for Additive Valuations | Simina Branzei and Ariel Procaccia | [efx-additive-existence](efx-additive-existence/PROBLEM.md) |
| Existence of PMMS and Epistemic PMMS for Additive Valuations | Michal Feldman | [existence-of-pmms-and-epistemic-pmms-for-additive-valuations](existence-of-pmms-and-epistemic-pmms-for-additive-valuations/PROBLEM.md) |
| Informational Substitutes and Complements | Yiling Chen | [informational-substitutes-complements](informational-substitutes-complements/PROBLEM.md) |
| Matroid Intersection Prophet Inequalities | Matt Weinberg | [matroid-intersection-prophet-inequality](matroid-intersection-prophet-inequality/PROBLEM.md) |
| MMS Approximation and Truthful Fair Allocation | Moshe Babaioff | [mms-approximation-and-truthful-fair-allocation](mms-approximation-and-truthful-fair-allocation/PROBLEM.md) |
| Online Submodular Welfare in Random Order | Vahab Mirrokni | [online-submodular-welfare-in-random-order](online-submodular-welfare-in-random-order/PROBLEM.md) |
| PCP for PPAD | Aviad Rubinstein | [pcp-for-ppad](pcp-for-ppad/PROBLEM.md) |
| Prophet Inequality for Subadditive CA | Paul Duetting | [prophet-inequality-for-subadditive-ca](prophet-inequality-for-subadditive-ca/PROBLEM.md) |
| Query Complexity of Tarski Fixed Points | Aviad Rubinstein | [query-complexity-of-tarski](query-complexity-of-tarski/PROBLEM.md) |
| Revelation Gap for MHR Pricing from One Sample | Jason Hartline | [revelation-gap-mhr-pricing](revelation-gap-mhr-pricing/PROBLEM.md) |
| Revelation Gap for Public-Budget Welfare Maximization | Jason Hartline | [revelation-gap-public-budget-welfare](revelation-gap-public-budget-welfare/PROBLEM.md) |
| Revenue Optimal DSIC Auction | Yanchen Jiang, David Parkes, Tonghan Wang | [revenue-optimal-dsic-auction](revenue-optimal-dsic-auction/PROBLEM.md) |
| Signal-Preserving 2/3-Approximation for Explainable Linear Information Design | Yiling Chen and Tao Lin | [signal-preserving-explainable-information-design](signal-preserving-explainable-information-design/PROBLEM.md) |
| Static Posted Pricing for Multi-Unit Combinatorial Auctions | Brendan Lucier | [posted-pricing-multi-unit-xos](posted-pricing-multi-unit-xos/PROBLEM.md) |
| Submodular Welfare Maximization with Demand Oracle | Renato Paes Leme | [submodular-welfare-maximization-with-demand-oracle](submodular-welfare-maximization-with-demand-oracle/PROBLEM.md) |
| Truthful Mechanism for Submodular CA | Sebastien Lahaie | [truthful-mechanism-for-submodular-ca](truthful-mechanism-for-submodular-ca/PROBLEM.md) |