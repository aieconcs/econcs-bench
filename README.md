# econcs-bench

Benchmark suite of open research challenges in Economics and Computation (EconCS). This repository is associated with the workshop on [AI-Driven Research in EconCS](https://sites.google.com/corp/view/aieconcs26/) held at [EC 2026](https://ec26.sigecom.org/).

- [Benchmark Problems](#benchmark-problems)
- [Contributing](#contributing)

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
| Revenue Gap Between Myerson and Anonymous Reserves | Jerry Anunrojwong | [myerson-vs-anonymous-reserve](myerson-vs-anonymous-reserve/PROBLEM.md) |
| Revenue Optimal DSIC Auction | Yanchen Jiang, David Parkes, Tonghan Wang | [revenue-optimal-dsic-auction](revenue-optimal-dsic-auction/PROBLEM.md) |
| Signal-Preserving 2/3-Approximation for Explainable Linear Information Design | Yiling Chen and Tao Lin | [signal-preserving-explainable-information-design](signal-preserving-explainable-information-design/PROBLEM.md) |
| Static Posted Pricing for Multi-Unit Combinatorial Auctions | Brendan Lucier | [posted-pricing-multi-unit-xos](posted-pricing-multi-unit-xos/PROBLEM.md) |
| Submodular Welfare Maximization with Demand Oracle | Renato Paes Leme | [submodular-welfare-maximization-with-demand-oracle](submodular-welfare-maximization-with-demand-oracle/PROBLEM.md) |
| Truthful Mechanism for Submodular CA | Sebastien Lahaie | [truthful-mechanism-for-submodular-ca](truthful-mechanism-for-submodular-ca/PROBLEM.md) |

## Contributing

We welcome submissions of open research challenges in Economics and Computation from the community. Open problems can be submitted directly via pull requests to the GitHub repository.

### Step-by-Step Submission Guide

#### 1. Fork and Clone the Repository
1. Fork [aieconcs/econcs-bench](https://github.com/aieconcs/econcs-bench) on GitHub to your account.
2. Clone your fork locally and create a new feature branch:

```bash
git clone https://github.com/<your-username>/econcs-bench.git
cd econcs-bench
git checkout -b add-<problem-name>
```

#### 2. Create the Problem Directory and `PROBLEM.md`
1. Create a new directory using lowercase kebab-case (e.g., `submodular-welfare-maximization`):

```bash
mkdir <problem-name>
```

2. Inside that directory, create a `PROBLEM.md` file. Each file must include YAML frontmatter at the top (`name` is required; `contributor` and `rating` are optional):

```markdown
---
name: Problem Name
contributor: Contributor Name
rating: Approachable | Challenging | Hard
---

## Problem Title

### Problem Description
Describe the formal model, definitions, notations, and setting.

### Known Results
Summarize current state-of-the-art results, known upper/lower bounds, and relevant baselines.

### Research Goal
State the precise open question, target approximation ratio, or conjecture to prove/disprove.

### Key References
List references and paper links.
```

#### 3. Commit and Push
Stage your problem folder, commit, and push the branch to your fork:

```bash
git add <problem-name>/PROBLEM.md
git commit -m "Add <Problem Name> problem"
git push -u origin add-<problem-name>
```

#### 4. Open a Pull Request
1. Navigate to [aieconcs/econcs-bench](https://github.com/aieconcs/econcs-bench) on GitHub.
2. Click **Compare & pull request** for your branch.
3. Review your changes and submit the pull request.

### Rating Rubric

Submitters can optionally include a `rating` field in the metadata to indicate the difficulty of the problem. The rating levels are as follows:

| Level | Submitter's Perspective | Expected Effort | Technical Barrier |
| :--- | :--- | :--- | :--- |
| **Approachable** | "The path forward seems relatively clear, but it needs focused execution." | A solid graduate student project or short paper. | Low. Likely solvable with known techniques. |
| **Challenging** | "This will require a dedicated, full-scale research effort." | A standard main-track conference paper. | Medium. Needs novel combinations of existing tools. |
| **Hard** | "I suspect our current standard tools are insufficient for this. In my view, this touches on foundational barriers..." | A major, sustained effort. Unpredictable. | High to Very High. Requires inventing new techniques or a new paradigm. |
| **Unspecified** | Rating not provided. | N/A | N/A |