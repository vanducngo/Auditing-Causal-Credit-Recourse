# Auditing Causal Credit Recourse in Peer-to-Peer Lending

Code and results for the paper *Auditing Causal Credit Recourse in Peer-to-Peer Lending: Graph-Dependent Attribution and Modest Loan-Amount Effects*, using LendingClub debt consolidation loans. The notebook tests whether causal attribution rankings survive changes to the assumed graph, and whether contract-consistent recourse beats a negative control and agrees with Double Machine Learning.

## Contents

| Path | Description |
|---|---|
| `causal_recourse_audit_debt_consolidation.ipynb` | All experiments, with outputs |
| `results/` | Tables (CSV) and figures (PDF, PNG) written by the notebook |
| `requirements.txt` | Pinned package versions |

## Data

The data file is not included. Download `Loan_status_2007-2020Q3.gzip` from [Kaggle](https://www.kaggle.com/datasets/ethon0426/lending-club-20072020q1) and place it next to the notebook, or set `LENDINGCLUB_CSV` to its path. Despite the extension, the file is a plain CSV.

## Running

Python 3.13 is required, because DoWhy 0.14 does not support Python 3.14.

```
conda create -n causal_recourse python=3.13 -y
conda activate causal_recourse
pip install -r requirements.txt
```

Open the notebook, select this environment and run all cells. The code runs on CPU; a GPU gives no speed-up. Set the environment variable `FAST=1` for a reduced smoke run, whose numbers should not be reported.

## Scope

The data contain funded loans only, so results do not extend to applicants rejected by LendingClub. Estimates rest on observed covariates. See Section 10 of the notebook for limitations.
