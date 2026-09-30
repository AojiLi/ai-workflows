# Experiment And Training Checks

Select checks that address the current question. These are investigation prompts, not a requirement to run every check or a substitute for the actual project's documentation.

## Baseline And Pipeline

- Identify the executed config after inheritance and runtime overrides, not just a sample YAML.
- Check dataset sampling, trajectory boundaries, observation/action alignment, normalization, and train/evaluation consistency.
- Check whether train/validation splits separate the appropriate trajectories, scenes, objects, robots, or subjects; a random frame split can leak correlated samples.
- Inspect action representation, coordinate frame, scale, control frequency, history length, prediction horizon, and action execution length.
- Check visual preprocessing and sensor calibration when relevant. Distinguish missing observations, history handling, and simulator-only information.
- Inspect pretrained checkpoint compatibility, loaded parameters, frozen modules, optimizer/scheduler state, and resumed training state.
- For supervised/imitation learning, inspect samples and try a simple baseline or small-data overfit check where meaningful.
- For online RL, inspect resets, termination/truncation, reward terms, action saturation, rollout accounting, and behavior of a simple policy. Do not substitute supervised overfitting for an RL pipeline check.
- Verify the evaluator and artifact paths before investing in a long run. Training loss alone does not validate task performance.

## Hypothesis And Controls

- Write the mechanism being tested and an outcome that would weaken the hypothesis.
- Compare the original baseline, the proposed change, and a simpler adaptation when it can explain the same gain.
- Separate additional information, parameter count, data augmentation, compute, and optimization changes from the mechanism under study.
- Choose the comparison budget to match the claim: environment interactions for sample efficiency, wall time/resources for speed, or a declared convergence protocol for final performance.
- Keep data, observation availability, action conventions, initialization/checkpoint, evaluation protocol, and relevant randomness comparable. Record unavoidable differences.
- For a history/occlusion idea, first check whether the baseline already uses history and whether train-time sampling matches evaluation-time buffering. A possible comparison is existing history, extended history, and new memory mechanism; this is a design example, not an established result.

## Evaluation And Uncertainty

- Fix success definitions, reset/initial-state distribution, episode horizon, observation noise, and timeout handling before interpreting improvements.
- Record training seeds separately from evaluation episode seeds. Episodes from one trained checkpoint are nested observations, not independent training replicates.
- For an initial cheap experiment, one training seed may be acceptable; label it preliminary and plan replication before claiming stability.
- Report per-task and relevant failure-mode results, as well as aggregates. State run/episode counts and the aggregation/uncertainty method.
- Match confidence intervals or resampling to the independent units and dependence structure. Do not present variation across episodes as uncertainty across training runs.
- Declare checkpoint selection and hyperparameter-selection rules. Reserve final tasks/scenes/data not used for tuning when the goal requires generalization evidence.
- Preserve failure, divergence, crashes, and partial runs; investigate their cause rather than dropping them from comparisons silently.

## Simulator, Hardware, And Transfer

- Record simulator and physics-engine versions, timestep, control decimation, device, headless/render mode, and relevant deterministic settings.
- State the limits of reproducibility across devices, software versions, and runtime physics changes; setting a seed alone does not establish equivalent conditions.
- Tie domain-randomization parameters and ranges to observed failure, documented task settings, or a clearly labeled hypothesis.
- Identify mismatches in contacts, actuation, delays, sensing, and reset distribution when proposing sim-to-real use.
- Keep simulation evidence separate from real-robot evidence. Do not initiate physical robot actions under an offline experiment request.

## Readiness Before Expensive Runs

- Required device, simulator, data, weights, dependencies, storage, and logging are usable.
- A representative pipeline check completed with expected artifacts and behavior.
- The resolved config, baseline, evaluator, run budget, and stop conditions are recorded.
- The execution fits the user's authorization and budget. Resume within that scope; ask only for a genuinely missing prerequisite.
