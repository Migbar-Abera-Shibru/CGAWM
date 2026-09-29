# Final checklist before sending to the advisor / Springer revision

1. Review `metadata/RESULTS_RECONCILIATION.md`.
2. Confirm that the historical ablation values in `data/ablation_historical_reported_results.csv` are the values intended for the revised manuscript.
3. Confirm the Figure 7 values in `data/sota_figure_7_reported_values.csv` are the intended manuscript values.
4. Confirm whether any original `.pt`, per-episode logs, checkpoints, or the missing ablation report can still be recovered.
5. Keep `new_seed_experiment.ipynb` and `new_test_for_sota.ipynb` in the public archive because they are important provenance for the final experiments.
6. Do not publish the simulated/target-generated SOTA curves as if they were independent empirical reproductions.
7. Record the final software versions/environment used for the manuscript revision if available.
8. Create the public GitHub repository and add this package/code as appropriate.
9. Create a Zenodo release and obtain a DOI.
10. Replace the placeholders in `DATA_AVAILABILITY_STATEMENT.md` with the final repository name and DOI/URL.
11. Put exactly the same Data Availability statement in the manuscript and Springer Nature submission system.
12. Keep a versioned release corresponding to the submitted revision.
