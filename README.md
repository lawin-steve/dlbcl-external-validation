# dlbcl-external-validation

External validation of gene-expression prognostic models in diffuse large B-cell lymphoma (DLBCL)
against the International Prognostic Index (IPI), across three public GEO cohorts.
Manuscript in preparation.

## Cohorts (all public, Gene Expression Omnibus)
- **GSE10846** — Lenz et al., training/reproduction cohort (rituximab-treated subset, n=233)
- **GSE181063** — HMRN population-based registry, primary external cohort (n=730 primary population)
- **GSE87371** — Dubois et al., secondary external cohort (non-PMBL, n=201)
- Screened and excluded (no machine-readable survival): GSE117556, GSE31312

## Notebooks (run order)
1. `dlbcl-notebook2.ipynb` — data acquisition and processing (GEO download, probe→gene mapping, clinical parsing)
2. `dlbcl-validation-clean.ipynb` — main analysis: frozen models, external validation, sensitivity analyses
3. `dlbcl-revision-A1-A3.ipynb` — CV-tuned model specification, reverse-direction experiment, multiple imputation
4. `dlbcl-jcocci-additions.ipynb` — signature-length sweep, cautionary path-end analysis, Lenz reproduction figure, Alizadeh 2011 two-gene model (LMO2/TNFRSF9), equivalence framing, reverse-genes + IPI, and the C0–C5 pre-submission reruns (frozen-preprocessing sensitivity, MI with Nelson-Aalen, reverse-KM follow-up, final figures, `requirements.txt`)

All notebooks run on Kaggle (free tier, CPU) from public data; end-to-end reproduction ≈ 30–40 min.

## Key files
- `lenz_signatures.py` — verbatim Lenz 2008 signature gene lists and model coefficients (source: US Patent 9,970,059), with legacy→HGNC symbol aliases
- `ANALYSIS_PLAN.md` — pre-defined analysis plan and prospectively deposited addendum
- `outputs/` — derived tables and figures
