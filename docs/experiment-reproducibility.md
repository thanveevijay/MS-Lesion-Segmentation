# Experiment Reproducibility Protocol

## Record for every run
- Dataset version and patient-level split identifiers
- Preprocessing configuration
- Model architecture and parameter count
- Optimizer, learning rate, batch size, and epoch count
- Random seeds and software environment
- Checkpoint selection rule
- Evaluation script version and metric definitions

## Training discipline
1. Keep the test partition isolated until final evaluation.
2. Save the configuration alongside each checkpoint.
3. Record training and validation losses per epoch.
4. Document early-stopping and learning-rate scheduling criteria.
5. Preserve failed runs with a short explanation rather than silently replacing their records.

## Reproducibility checks
- Re-run a selected configuration with the same seed.
- Confirm that the same data split and preprocessing are loaded.
- Compare metric differences using a stated tolerance.
- Investigate discrepancies caused by nondeterministic operations or environment changes.

## Reporting
Include enough configuration and data-version information for another contributor to reproduce the experiment without relying on undocumented local settings.
