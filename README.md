[![INFORMS Journal on Computing Logo](https://INFORMSJoC.github.io/logos/INFORMS_Journal_on_Computing_Header.jpg)](https://pubsonline.informs.org/journal/ijoc)

# PROPEL: Supervised and Reinforcement Learning for Large-Scale Supply Chain Planning

This archive is distributed in association with the [INFORMS Journal on
Computing](https://pubsonline.informs.org/journal/ijoc) under the [MIT License](LICENSE).

The data in this repository are a snapshot of the data that were used in the
research reported on in the paper
[PROPEL: Supervised and Reinforcement Learning for Large-Scale Supply Chain Planning](https://doi.org/10.1287/ijoc.2025.1338)
by V. Eghbal Akhlaghi, R. Zandehshahvar, and P. Van Hentenryck.

**Code availability.** The source code for the proposed method, including the
learning implementation and the scripts used to run the computational
experiments, cannot be released. It was developed under a nondisclosure
agreement with the industrial partner. Substantial implementation details are
provided in the paper and the online supplement to support reproducibility.

**This repository provides sample supply chain planning instances. These
synthetic benchmark instances are similar in structure and scale to the instances described
in Section 8.1 of the paper; they are not the same instances used in the
computational study.** The instances used in the paper are based on proprietary
industrial data provided by Kinaxis, which cannot be released due to data-privacy
restrictions associated with that data (as noted in the paper). These samples are
provided so that readers can inspect the structure and scale of such instances
and generate their own following the procedure in Section 8.1.

## Cite

To cite the contents of this repository, please cite both the paper and this repo, using their respective DOIs.

https://doi.org/10.1287/ijoc.2025.1338

https://doi.org/10.1287/ijoc.2025.1338.cd

Below is the BibTeX for citing this snapshot of the repository.

```
@misc{PROPELInstances,
  author =        {Eghbal Akhlaghi, Vahid and Zandehshahvar, Reza and Van Hentenryck, Pascal},
  publisher =     {INFORMS Journal on Computing},
  title =         {{PROPEL}: Supervised and Reinforcement Learning for Large-Scale Supply Chain Planning},
  year =          {2026},
  doi =           {10.1287/ijoc.2025.1338.cd},
  url =           {https://github.com/INFORMSJoC/2025.1338},
  note =          {Available for download at https://github.com/INFORMSJoC/2025.1338},
}
```

## Description

This repository releases sample Supply Chain Planning (SCP) Mixed-Integer
Programming (MIP) instances in MPS format. These anonymized instances are similar
in structure and scale to the proprietary industrial instances described in the
paper (see the Acknowledgements and Section 8.1). Each is a one-year
planning-horizon MIP with on the order of one million constraints and one-to-two
million variables.

In each instance, the demand constraints (Eq. (14) in Section 7) are labeled with
the string `Demand` in the MPS row names (e.g., `Demand0`, `Demand1`, …) so
that readers can identify them when generating new instances. All other
constraints remain obfuscated for data-privacy reasons.

The SCP optimization model these instances correspond to is given in Section 7
of the paper. Details on the instances and how to use them are provided in
[`data/README.md`](data/README.md).

## Repository layout

```
.
├── AUTHORS
├── LICENSE
├── README.md
└── data/
    ├── README.md                 # Instance details and statistics
    └── Propel_synt_snapshots.zip # Archive of synthetic benchmark .mps instances
```

## Data

The sample instances are distributed as a single compressed archive,
`data/Propel_synt_snapshots.zip`. After cloning the repository, extract it:

```
cd data
unzip Propel_synt_snapshots.zip
```

This yields `Propel_instance_0.mps`, `Propel_instance_1.mps`, and
`Propel_instance_2.mps`. Per-instance statistics are documented in
[`data/README.md`](data/README.md).

## Replicating

The instances are in standard MPS format and can be loaded by any
MPS-compatible MIP solver (Gurobi, CPLEX, SCIP, HiGHS, COIN-OR CBC, etc.).

To reproduce the additional instances used in the paper, follow the
instance-generation procedure in Section 8.1. The demand constraints can be
located in the MPS files by their `Demand` row names. The baseline and PROPEL
solution methods, including solver configuration, are described in Sections 5, 6,
and 8.

## Support

For questions about these instances, please open an issue on this repository.
