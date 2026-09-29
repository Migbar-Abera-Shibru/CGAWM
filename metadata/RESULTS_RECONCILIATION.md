# CGAWM results reconciliation — revision package

This note records what is currently supported by the preserved thesis, manuscript, notebooks, and W&B export.

## 1. Ablation experiment

The five-condition ablation experiment is a real experiment performed by the authors. The original report/output file could not be located during the current data recovery effort.

The historical values reported in Thesis Table 4.5 are preserved in `data/ablation_historical_reported_results.csv`:

- Model-Free Baseline: -5.508
- Curriculum-Only: -5.007
- Model-Based Only: +2.500
- Full Hybrid CGAWM: +1.499
- Uncertainty Ablation: +2.500

The notebooks also contain other executions with different numerical outcomes. Those executions are retained separately in the notebook-recorded CSV files and must not be silently substituted for the historical manuscript/thesis values.

## 2. Main multi-seed experiment

`new_seed_experiment.ipynb` contains the 5,000-episode experiment with seeds 42, 123, and 999 for Model-Free, Curriculum, Model-Based, and Full Hybrid CGAWM. The notebook explicitly saves per-seed logs as `.pt` files during execution, but those generated `.pt` files are not currently available in this package.

Therefore the package preserves the notebook as the provenance for this experiment, but does not claim to contain the underlying trajectory-level logs.

## 3. SOTA comparison

`new_test_for_sota.ipynb` contains 5,000-episode training runs and also contains the exact values used in the manuscript's Figure 7 bar chart:

- MAPPO: 85.012894
- DreamerV3: 92.288086
- MAMBRL: 109.394470
- Full CGAWM Hybrid: 137.048340

These values are preserved in `data/sota_figure_7_reported_values.csv` as **figure-source/report values**. They should not be described as recovered raw trajectory data because the plotting cell stores the values directly rather than loading a retained trajectory dataset.

The same notebook also contains a section explicitly described in its source as using “Simulation logic using target reward curves from actual SOTA papers.” Those simulated curves must not be represented as independent empirical reproductions of the original SOTA papers.

`comparison_on_SOTA.ipynb` contains a separate 3-seed numerical execution with MAPPO, ALP-GMM, DreamerV3, MAMBA, and Full CGAWM. Its results are preserved separately because they do not numerically match the manuscript Figure 7 values.

## 4. Hyperparameters and convergence

The thesis records the final selected configuration and reports that values were selected through validation/coarse grid search. It records seeds 42, 123, and 999 for the long-run experiment and reports convergence for all three seeds.

The manuscript currently contains both “100% convergence” and “90% convergence” wording. The thesis evidence supports reporting the observed result more precisely as convergence in all three evaluated seeds, provided the manuscript's convergence criterion is defined consistently.

## 5. 136% improvement claim

The thesis/manuscript document a 136% improvement claim, but the exact original operands used for that headline calculation are not explicitly preserved in the recovered materials. One retained historical notebook execution has PPO/Model-Free = -5.508 and Full Hybrid = 1.9995, which yields approximately 136.3% under the manuscript's stated formula. This is a plausible provenance clue, not proof of the original calculation.

Do not present that calculation as definitively reconstructed unless the original report/output is recovered.

## 6. W&B export

`data/wandb_experiment_export.csv` is an export of 20 W&B runs. It contains run metadata, hyperparameters, status, and selected training/evaluation metrics. It is not a trajectory-level dataset, replay-buffer dump, checkpoint archive, or complete per-step history.

## 7. Publication rule

This package should be described as a collection of preserved computational artifacts, recorded/processed results, configuration information, and provenance documentation. It should **not** be described as a complete raw-data archive unless the missing trajectory/log/checkpoint artifacts are recovered.
