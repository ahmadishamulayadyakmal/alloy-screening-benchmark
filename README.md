# Composition screening before lab trials (C04)

> Workspace folder: `e04-matbench-benchmark` · Suggested GitHub repository: `alloy-screening-benchmark`
> Epic: E04 · Weeks: W14–W17 · Evidence level: **A**
> Master specification: [`CASES.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/CASES.md) §4 · Download the papers: [`JOURNALS.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/JOURNALS.md)

## Industrial problem

Every trial heat costs time and material. A plant needs to rank candidate compositions by predicted property before melting, and to know how much to trust the ranking.

**Why it happens.** Small heterogeneous materials datasets make it easy to overfit with a random split; without an official benchmark, scores are not comparable.

## Data (no plant data)

Open data only: MatBench v0.1 (R08/D04, 13 tasks, official folds) and Materials Project (R02/D08, CC BY 4.0, academic use only). No proprietary alloy database. Evidence level A.

> The author cannot supply factory data. This project uses **only open datasets and
> credible peer-reviewed journals**. If this is a B-level case, the case report
> must contain the exact disclaimer from `CASES.md` §1 and must **never** claim
> plant validation.

## Tool chain

`pymatgen`, `matminer`, scikit-learn, XGBoost, Automatminer reference, official 5-fold CV, MLflow, SHAP, model card.

## Journal references

- **R08** — official splits, Automatminer comparator, leaderboard framing.
- **R02** — Materials Project data provenance and mandatory citation.
- **R04** — descriptor and UQ methodology.
- **R05** — ML pipeline: data -> representation -> model.
- **R06** — `pymatgen` library.
- **R07** — `matminer` featurization.
- **D04** — MatBench download and version pinning.
- **D08** — Materials Project licence and citation.

Each reference above is listed with its DOI or stable URL, access status and
manual download route in [`JOURNALS.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/JOURNALS.md) §4, and in the shared
BibTeX library `papers/references.bib`. Do not cite a paper you have not been
able to obtain; if it is inaccessible, record that in `JOURNALS.md` §8.

## Deliverables

Benchmark harness; score table vs leaderboard; featurization report; model card; ranked shortlist of candidate compositions with intervals.

## Validation & claims

Official folds only; seed recorded; error bars reported; at least 3 tasks reproduce the published baseline within tolerance; discrepancies documented, not hidden.

## Limitations

DFT/derived targets are not plant heats. Domain shift to real alloys is flagged explicitly; no trial-heat claim.

## Definition of Done

1 merged PR · green tests · 1 new artefact · 1 README paragraph · 1 sprint note
`docs/sprints/wNN.md` · tag `wNN`. Before the case tag `c04` is created,
this README must contain all six sections: Industrial problem, Data (no plant
data), Tool chain, Journal references, Validation & claims, Limitations.

## Repository skeleton

Shared files: `CONTRIBUTING.md` (sprint contract), `.github/` (issue, PR and
CI templates), `docs/sprints/wNN.md`, `docs/vv_template.md` and
`docs/model_card.md`. `CASES.md`, `JOURNALS.md` and `REPOSITORIES.md` are in a
separate planning repository; their links above remain valid after this folder
is pushed as its own repository.

The real industrial case dossier is in `case/`: `README.md` (full case card),
`evidence.md`, `sources.md` and `week_plan.md`.

## Repository status and GitHub Desktop

This folder is already a Git repository on `main`, pushed to GitHub as
`alloy-screening-benchmark` with an SSH `origin`. In GitHub Desktop, choose **Add local
repository** and select this folder; do not clone into the same path.

```bash
git status --short --branch
git pull --rebase origin main
git push origin main
```

Weekly work follows `CONTRIBUTING.md`: one PR, green tests, one artefact, one
README paragraph, `docs/sprints/wNN.md`, tag `wNN`. Tag `c04` only after
all six README sections are complete.


## Language

All artefacts in this repository are written in **English**.
