# Data status and provenance

## Confirmed real experiments

The CGAWM experiments in the supplied notebooks and thesis were actually performed by the authors. The absence of a currently recoverable output file does not mean that an experiment was simulated or fabricated.

## What is included

- Original Jupyter notebooks currently available to the authors.
- The main 5,000-episode, three-seed notebook (`new_seed_experiment.ipynb`).
- The SOTA notebook (`new_test_for_sota.ipynb`) containing both training runs and the explicit Figure 7 source values.
- Notebook-recorded numerical result tables.
- Historical ablation values reported in the thesis.
- W&B export containing run metadata and selected metrics.
- Experiment configuration excerpts and reconciliation documentation.

## What is not currently recovered

- Original ablation report/output file.
- Per-episode raw logs for every reported experiment.
- Replay-buffer dumps.
- Model checkpoints.

## How to interpret the result files

`ablation_historical_reported_results.csv` is a historical record of the real ablation experiment as reported in Thesis Table 4.5. It is not a reconstructed raw dataset.

`ablation_run_*_recorded.csv` contains other numerical executions preserved from notebooks. These must not be silently substituted for the historical manuscript result.

`sota_figure_7_reported_values.csv` contains the exact values stored in the Figure 7 plotting cell. These are figure-source/report values, not recovered trajectory-level data.

`sota_three_seed_recorded.csv` contains a separate 3-seed notebook execution whose numerical values do not match the manuscript Figure 7 values. It is retained for provenance and transparency.

`wandb_experiment_export.csv` is an experiment-tracking export, not raw trajectory data.
