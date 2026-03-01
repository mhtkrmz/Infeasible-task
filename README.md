# AWARE-US: Preference-Aware Infeasibility Resolution in Tool-Calling Agents

**AWARE-US** is a benchmark for *preference-aware infeasibility handling* in tool-calling conversational agents that query structured databases. In real systems, agents often face (i) **underspecification** (missing constraints required to execute a query) and (ii) **infeasibility** (the fully specified query returns an empty set). AWARE-US focuses on the second problem: when the query is infeasible, the agent should relax the **least important** constraint, using preference cues expressed during the interaction, rather than returning “no results” or applying ad hoc relaxation rules.

This dataset accompanies the paper **“AWARE-US: Preference-Aware Infeasibility Resolution in Tool-Calling Agents”** (COLM 2026 submission / under review).

- 📄 **Paper (PDF):** [AWARE-US paper](https://arxiv.org/abs/2601.02643)
- 🧾 **Citation:** see the *Citation* section below

## What’s inside

Each example is persona-grounded and provides:
- a **base request** (underspecified slice of the database),
- a set of **elicited additional constraints** + **weights** (oracle importance profile),
- the **intended relaxation target** (the least-important constraint to drop/relax under infeasibility),
- and the **gold recommendation** after repair (a feasible item selected to align with the oracle preferences).

AWARE-US is constructed in the **car recommendation** domain over a structured car catalog (derived from the “Car Features and MSRP” dataset).  

## Configurations (S1 / S2 / S3)

This repo is organized into **three configurations** that correspond to controlled infeasibility regimes:

- **S1 (unique drop-one repair)**: 4 additional constraints; **exactly one** constraint must be relaxed to restore feasibility. (41 instances)
- **S2 (any-one repair)**: 4 additional constraints; **dropping any single** constraint restores feasibility. (41 instances)
- **S3 (any-one repair, smaller)**: 2 additional constraints; dropping either restores feasibility. (40 instances)

(Counts and setting definitions follow the paper’s dataset construction section and Table 1.)  

### Citation

```bibtex
@misc{kurmaz2026awareus,
  title        = {AWARE-US: Preference-Aware Infeasibility Resolution in Tool-Calling Agents},
  author       = {Mehmet Kurmaz},
  year         = {2026},
  note         = {COLM 2026 submission / under review},
  howpublished = {\url{https://arxiv.org/abs/2601.02643}}
}
