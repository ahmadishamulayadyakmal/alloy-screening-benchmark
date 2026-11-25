# C04 · Composition screening before lab trials — W14–W17

> **Real industrial case dossier.** Copied from the authoritative case card in
> `CASES.md` §4 so this repository stays self-contained after it is pushed to
> GitHub. Planning links: [`CASES.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/CASES.md) ·
> [`JOURNALS.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/JOURNALS.md) ·
> [`WEEKLY_PLAN.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/WEEKLY_PLAN.md).
> **Evidence level: A** · No plant data is held in this repository.

**Repository:** `e04-matbench-benchmark` · **Evidence: A** ·
**References:** R02, R04, R05, R06, R07, R08, D04.

**Industrial problem.** Every trial heat costs time and material. A plant needs to
rank candidate compositions by predicted property **before** melting, and needs
to know how much to trust that ranking.

**Why it happens.** Small, heterogeneous materials datasets make it easy to
overfit with a random split; without an official benchmark, scores are not
comparable.

**Data (open, no plant data).** MatBench v0.1 (R08, 13 tasks, official folds) and
Materials Project (R02, CC BY 4.0, academic use only). No proprietary alloy
database.

**Tool chain.** `pymatgen` / `matminer` featurization → RF and XGBoost baselines →
Automatminer reference (R08) → official 5-fold CV → MLflow → SHAP → model card.

**What each reference validates.**
- R08 — official splits, Automatminer comparator, leaderboard framing.
- R02 — Materials Project data provenance and mandatory citation.
- R04, R05 — descriptor and ML-pipeline methodology.
- R06, R07 — `pymatgen` and `matminer` libraries.
- D04 — MatBench download and version pinning.

**Deliverables.** Benchmark harness; score table vs leaderboard; featurization
report; model card; a ranked shortlist of candidate compositions with intervals.

**Validation.** Official folds only; seed recorded; error bars reported; explicit
domain-shift warning (DFT/derived targets ≠ plant heats).

**Acceptance.** At least 3 MatBench tasks reproduce the published baseline within
the stated tolerance; discrepancies documented, not hidden.

## Claim boundary

See [`evidence.md`](evidence.md) for the evidence level and the exact wording
that must be used when quoting literature numbers. All datasets and references
are listed in [`sources.md`](sources.md); the four-week execution plan is in
[`week_plan.md`](week_plan.md).
