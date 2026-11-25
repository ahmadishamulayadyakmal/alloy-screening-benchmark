# Composition screening before lab trials (C04)

## Industrial problem

Every trial heat costs time and material. A plant needs to rank candidate compositions by predicted property before melting, and to know how much to trust the ranking.

**Why it happens.** Small heterogeneous materials datasets make it easy to overfit with a random split; without an official benchmark, scores are not comparable.

## Data (no plant data)

Open data only: MatBench v0.1 (R08/D04, 13 tasks, official folds) and Materials Project (R02/D08, CC BY 4.0, academic use only). No proprietary alloy database.

> Only open datasets and published literature are used. No plant or proprietary data are held here; plant numbers quoted from papers are external literature, not independently reproduced results.

## Tool chain

`pymatgen`, `matminer`, scikit-learn, XGBoost, Automatminer reference, official 5-fold CV, MLflow, SHAP, model card.

## Journal references

- **R08** ([DOI](https://doi.org/10.1038/s41524-020-00406-3)) — official splits, Automatminer comparator, leaderboard framing.
- **R02** ([DOI](https://doi.org/10.1063/1.4812323)) — Materials Project data provenance and mandatory citation.
- **R04** ([DOI](https://doi.org/10.1038/s41524-017-0056-5)) — descriptor and UQ methodology.
- **R05** ([DOI](https://doi.org/10.1038/s41586-018-0337-2)) — ML pipeline: data -> representation -> model.
- **R06** — `pymatgen` library.
- **R07** ([DOI](https://doi.org/10.1016/j.commatsci.2018.05.018)) — `matminer` featurization.
- **D04** ([source](https://matbench.materialsproject.org/)) — MatBench download and version pinning.
- **D08** ([source](https://materialsproject.org/)) — Materials Project licence and citation.

## Deliverables

Benchmark harness; score table vs leaderboard; featurization report; model card; ranked shortlist of candidate compositions with intervals.

## Validation & claims

Official folds only; seed recorded; error bars reported; at least 3 tasks reproduce the published baseline within tolerance; discrepancies documented, not hidden.

## Limitations

DFT/derived targets are not plant heats. Domain shift to real alloys is flagged explicitly; no trial-heat claim.

## Repository layout

- `README.md` — case summary, data policy, method, results and limitations.
- `CONTRIBUTING.md` — how to propose changes.
- `docs/index.md` — documentation map.
- `docs/model_card.md` and `docs/vv_template.md` — reporting templates.
- `.github/workflows/ci.yml` — automated checks.

Only open data and published literature are used. No plant or proprietary data
are included. All artefacts are written in English.
