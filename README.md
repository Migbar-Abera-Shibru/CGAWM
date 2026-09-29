# CGAWM — Reproducibility and Supporting Data

**Manuscript:** CGAWM: A Curriculum-Guided Adversarial World Model for Sample-Efficiency Multi-Agent Reinforcement Learning

This package contains the computational artifacts and preserved result records currently available for the CGAWM study. It is a **provenance and supporting-data package**, not a complete archive of every raw training trajectory.

## What changed in this revision package

This version incorporates the thesis and the subsequently identified `new_test_for_sota.ipynb` provenance. In particular:

- the real five-condition ablation experiment is identified as historical experimental data even though its original report/raw output was not recovered;
- the 5,000-episode, three-seed main experiment notebook is included;
- the SOTA notebook containing the exact Figure 7 source values is included;
- the W&B CSV export is included;
- manuscript/thesis-reported values are kept separate from notebook-recorded numerical executions;
- simulated/target-generated SOTA curves are explicitly identified and are not presented as raw empirical data.

## Contents

```text
CGAWM_Scientific_Reports_Data_Package/
├── README.md
├── DATA_AVAILABILITY_STATEMENT.md
├── metadata/
│   ├── DATA_STATUS.md
│   ├── RESULTS_RECONCILIATION.md
│   ├── SOURCE_DOCUMENTS.md
│   ├── EXPERIMENT_MANIFEST.csv
│   ├── ADVISOR_CHECKLIST.md
│   └── experiment_config_excerpts.json
├── data/
│   ├── ablation_historical_reported_results.csv
│   ├── ablation_run_1_recorded.csv
│   ├── ablation_run_2_recorded.csv
│   ├── ablation_run_3_recorded.csv
│   ├── sota_figure_7_reported_values.csv
│   ├── sota_5000_training_runs_status.csv
│   ├── sota_single_run_1_recorded.csv
│   ├── sota_single_run_2_recorded.csv
│   ├── sota_three_seed_recorded.csv
│   └── wandb_experiment_export.csv
└── notebooks/
    ├── Improve_the_CGAWM.ipynb
    ├── comparison_on_SOTA.ipynb
    ├── new_seed_experiment.ipynb
    ├── new_test_for_sota.ipynb
    └── Untitled23.ipynb
```

## Provenance categories

### Historical reported results
These are values documented in the thesis/manuscript. The ablation experiment was actually performed by the authors, but the original report/raw output could not be recovered.

### Notebook-recorded results
These are numerical summaries retained in notebook execution outputs. The notebooks may contain multiple executions with different outcomes, so each run is preserved rather than silently selected as the manuscript result.

### Figure-source values
`data/sota_figure_7_reported_values.csv` contains the exact values explicitly stored in the Figure 7 plotting cell of `new_test_for_sota.ipynb`.

### W&B export
`data/wandb_experiment_export.csv` contains W&B run metadata, configurations, and selected metrics for 20 runs.

## Important raw-data limitation

The currently recovered package does **not** contain the underlying trajectory-level transition data, complete per-episode logs for every manuscript figure, replay-buffer dumps, or model checkpoints. `new_seed_experiment.ipynb` shows that `.pt` seed-log files were generated during the 5,000-episode experiment, but those generated files are not currently recovered.

Therefore, do not describe this package as containing the complete raw dataset. No missing trajectory values have been invented or regenerated merely to fill gaps.

## SOTA caution

`new_test_for_sota.ipynb` contains both actual training runs and a separate section explicitly described in the notebook as “Simulation logic using target reward curves from actual SOTA papers.” The simulated section must not be represented as an independent reproduction of the original SOTA algorithms.

## Recommended publication wording

Use the accompanying `DATA_AVAILABILITY_STATEMENT.md` as the starting point. Replace the repository placeholder with the final public repository URL/DOI only after the repository is created.
