---
name: model-training
description: Train, fine-tune, resume, and evaluate machine learning and reinforcement learning models, including paper reproductions. Follow established practices, carry out meaningful training, and judge when further experimentation is worthwhile.
---

# Model Training

## 1. Learn Established Practices
Consult relevant textbooks, paper training details, official documentation, and established implementations.
Understand suitable configurations, training budgets, evaluation methods, and common failure modes.
Prefer existing training pipelines. Reuse previously verified references when they remain applicable.

## 2. Understand the Task and Execute
Inspect the project's code, configuration, data or environment, previous results, and checkpoints.
Reuse the user's stated goals, authorization, and budget. Ask only for critical missing information.
When asked to train, carry out training within the authorized scope. Scripts and recommendations alone do not complete a training request.

## 3. Distinguish Debugging from Full Training
Define a limited set of necessary checks and their passing conditions.
Once they pass, proceed to full training within the authorized budget.
Do not require convergence or complete task success during a smoke test.
Avoid endlessly adding prerequisites.

## 4. Keep Experiments Comparable
Establish a baseline, fix the evaluation protocol, and give the selected configuration sufficient training.
Do not repeatedly change configurations or restart because of poor short-term results.
Record what changed, the code version, accumulated training, and actual results for each experiment.
When resuming, verify the required training state. Loading model weights alone may not constitute a full resume.

## 5. Evaluate Actual Performance
Use independent evaluation and learning curves to assess results.
Do not rely solely on loss or total reward.
For RL, distinguish training randomness from evaluation scenario randomness.
Preserve logs, checkpoints, job identifiers, and execution status, including failures and negative results.

## 6. Decide Reasonably Whether to Continue
Distinguish explicit requirements from aspirational targets. Explain the basis for thresholds you propose.
Near a target, assess the practical significance of the gap, evaluation variability, and the expected benefit of further work.
A short plateau does not automatically justify stopping; a small remaining gap does not justify unlimited retries.
Use the budget, adequately observed trends, and stopping conditions to decide the next action.
An experiment may reasonably end with an unresolved gap. Report it honestly without silently lowering requirements or claiming the target was met.

## Optional Project Instructions

An [AGENTS.md template](assets/AGENTS.md.template) is included for projects that want to route training tasks to this skill. Installing the skill does not modify project instructions; merge the template into the project's root `AGENTS.md` while preserving existing guidance.
