# Pre-defined analysis plan

External validation of gene-expression prognostic models in DLBCL versus the IPI.
This plan was established prior to outcome analysis of the validation cohorts (dated 2026-08-30)
and is reproduced verbatim from the header of `dlbcl-validation-clean.ipynb`.

- **Design:** retrospective external-validation benchmarking, TRIPOD+AI-oriented.
- **Primary endpoint:** overall survival. **Primary metric:** Harrell's C; ΔC vs IPI with 95% paired-bootstrap CI (1,000 resamples).
- **Primary populations:** GSE10846 rituximab-treated (training); GSE181063 DLBCL, qc_fail==0, curative intent, CHOP-R ± CHOP-R/Bortezomib (primary external); GSE87371 non-PMBL (secondary external).
- **Reference comparator:** cohort-provided IPI where available (HMRN `ipi_score`; GSE87371 `ipi`); recomputed IPI as sensitivity.
- **Models:** (1) IPI; (2) COO+IPI Cox (trained GSE10846); (3) de novo genes-only elastic-net Cox (top-2000 variance genes, trained GSE10846); (4) two-stage clinical-LP + genes; (5) Lenz stromal-1/2 (reconstructed lists — subject to reproduction gate; verbatim lists pending).
- **Transfer rule (fixed):** gene-symbol intersection across platforms; per-cohort z-scoring; frozen coefficients; no re-tuning on validation data.
- **Success criterion (declared before external analysis):** a model "adds transferable value" if ΔC vs IPI > 0.02 with 95% CI excluding 0 in the primary external cohort, with directional support (ΔC > 0) in the secondary cohort.
- **Reproduction gate:** published signatures must reproduce expected behavior in training before external interpretation.
- Items listed at the time as pending before manuscript: verbatim Lenz 2008 gene lists; elastic-net alpha selected by internal CV; time-dependent AUC, calibration, decision curves; excluded-patient (missing-IPI) sensitivity.

# Addendum A1–A3 (deposited on OSF before execution)

<!-- TODO: replace this section with the deposited addendum text verbatim, and add the OSF link and deposit date. -->

Revision analyses implemented in `dlbcl-revision-A1-A3.ipynb`. Frozen models are rebuilt
deterministically (seeded) from the committed parquets.

- **A1 — CV-tuned genes-only as the sole de novo model.** Elastic-net alpha selected by 5-fold internal CV on GSE10846 R-CHOP; all external metrics recomputed for this specification.
- **A2 — Reverse direction.** Train the genes-only model on GSE181063 (HMRN primary population, n≈730) and validate on GSE10846 R-CHOP and GSE87371. Pre-stated prediction: ΔC vs IPI ≤ 0 in both.
- **A3 — Multiple imputation of IPI components** for all primary-population GSE181063 patients, to assess the excluded (IPI-missing) subgroup.

OSF deposit: [link pending]
