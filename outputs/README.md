# outputs/

Derived tables and figures. Provenance:

| File | Produced by | Note |
|---|---|---|
| `fig1_flow.png` | `dlbcl-validation-clean.ipynb` | cohort flow diagram |
| `fig_forest.png` | `dlbcl-validation-clean.ipynb` | ΔC vs IPI forest plot |
| `fig_km_tertiles.png` | `dlbcl-validation-clean.ipynb` | KM by risk tertile |
| `fig_missing_ipi.png` | `dlbcl-validation-clean.ipynb` | included vs IPI-missing patients |
| `fig_signature_length_sweep.png` | `dlbcl-jcocci-additions.ipynb` | B1 |
| `fig_lenz_reproduction.png` | `dlbcl-jcocci-additions.ipynb` | B3 |
| `table1_cohorts.csv` | `dlbcl-validation-clean.ipynb` | cohort characteristics |
| `sweep_hmrn_trained.csv` | `dlbcl-jcocci-additions.ipynb` | B1, HMRN-trained direction |
| `sweep_gse10846_trained.csv` | `dlbcl-jcocci-additions.ipynb` | B1, GSE10846-trained direction |

| `hmrn_scores.csv` | `dlbcl-validation-clean.ipynb` | per-patient model scores, GSE181063 eval set |
| `gse87371_scores.csv` | `dlbcl-validation-clean.ipynb` | per-patient model scores, GSE87371 non-PMBL |

The sweep CSVs, score CSVs, and the two B1/B3 figures are the files saved by the
Kaggle kernel runs (downloaded via the Kaggle API). The four clean-notebook figures
were extracted from the PNGs embedded in the committed notebook outputs.
`table1_cohorts.csv` was transcribed from the table printed in the committed
notebook output; re-running `dlbcl-validation-clean.ipynb` regenerates it.
