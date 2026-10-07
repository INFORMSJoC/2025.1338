# PROPEL Supply Chain Planning Sample Instances

This directory contains **sample Supply Chain Planning (SCP) instances**.
They are synthesized samples similar in structure and scale to the instances
used in the paper. The paper generates 500 instances for supervised training and
100 for the deep reinforcement learning component (plus the test instances) from
20 base snapshots, following the procedure in Section 8.1. Readers can apply
that procedure to generate additional instances of the same kind.

## Data origin

The instances used in the paper are based on proprietary industrial data
provided by Kinaxis. Because of data-privacy restrictions associated with that
data (as noted in the paper), the original instances cannot be released.
Instead, we provide these synthesized samples, which are similar in structure and
scale to the instances used in the paper. The original data source and the
instance-generation procedure are described in the paper (see the
Acknowledgements and Section 8.1). If you reuse these instances, please cite
both the paper and this repository (see the Cite section in the root
[`README.md`](../README.md), including DOIs
`10.1287/ijoc.2025.1338` and `10.1287/ijoc.2025.1338.cd`).

## Constraint labeling

Each instance is a minimization MIP with general integer and continuous
variables (0 binary). The decision variables, constraints, and objective follow
the SCP model in Section 7 of the paper (Figures 2 and 3).

- **Demand constraints** (Eq. (14)): labeled with the string `Demand` in the MPS
  row names (e.g., `Demand0`, `Demand1`, …). These are the constraints whose
  right-hand sides are perturbed when generating new instances (Section 8.1).
- **All other constraints** (balance, capacity, etc.): remain obfuscated (e.g.,
  `R0`, `R1`, …) for data-privacy reasons.

## Files

The samples are distributed inside a single archive, `Propel_synt_snapshots.zip`,
which expands to:

| File | Format | Size (uncompressed) |
| --- | --- | --- |
| `Propel_instance_0.mps` | MPS (text) | ~226 MB |
| `Propel_instance_1.mps` | MPS (text) | ~204 MB |
| `Propel_instance_2.mps` | MPS (text) | ~181 MB |

The files are zipped because each uncompressed `.mps` file exceeds GitHub's
100 MB per-file limit. Extract the archive (`unzip Propel_synt_snapshots.zip`)
before using the instances.

## Instance statistics

| Instance | Rows | Columns | Nonzeros | Integer vars | Continuous vars | Demand rows |
| --- | --- | --- | --- | --- | --- | --- |
| `Propel_instance_0` | 1,221,701 | 1,883,573 | 6,402,481 | 468,798 | 1,414,775 | 1,501 |
| `Propel_instance_1` | 1,110,876 | 1,701,601 | 5,760,748 | 417,634 | 1,283,967 | 1,359 |
| `Propel_instance_2` |   999,954 | 1,516,990 | 5,108,882 | 364,355 | 1,152,635 | 1,171 |

## Usage

The instances are in standard MPS format and can be loaded by any
MPS-compatible MIP solver (Gurobi, CPLEX, SCIP, HiGHS, COIN-OR CBC, etc.). To
generate new instances, identify the demand constraints by their `Demand` row
names and apply the perturbation procedure in Section 8.1. The solver
configuration and solution methods are described in Sections 5, 6, and 8 of
the paper.
