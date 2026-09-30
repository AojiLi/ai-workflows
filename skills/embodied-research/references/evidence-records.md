# Lightweight Evidence Records

Adapt these sections to the project's existing records. Use one canonical location for each fact and link to it. Empty templates are not evidence; omit irrelevant fields and label missing information as unknown.

## Project Context

Only create `research/context.md` if existing docs do not already give a concise research orientation. Record durable facts and replace obsolete ones in place:

- research objective and current task family
- robot/task, observations/actions, frames/units, control rate, and deploy-time information
- baseline code/config/checkpoint and authoritative document paths
- dataset provenance and split policy, evaluator, and failure cases
- simulator/runtime requirements, compute and experiment constraints
- confirmed assumptions versus unresolved questions

Keep exact operational commands in the project's chosen command source, such as `AGENTS.md` or a runbook; link instead of maintaining multiple copies.

## Literature And Implementation Record

Use an existing reference location or a relevant section of `research/literature.md` or `research/<topic>.md`:

```markdown
### Candidate: <method>
- Question addressed:
- Search terms/sources and date checked:
- Paper URL/version and relevant section/equation/table:
- Claim and evidence category: paper-reported / code-inspected / locally-observed / hypothesis
- Repo URL/commit and file/function/config locations:
- Available checkpoint and evaluation implementation:
- Reusable components and required adaptations:
- Conditions and differences from this project:
- License/dependency constraints:
- Paper/code discrepancies and unanswered questions:
- Decision: investigate / reuse / adapt / reject, with reason:
```

Record access failures and sources actually inspected. A paper-reported result can be well supported without being locally reproduced; the evidence category describes what was checked, not a claim that all categories are equivalent.

## Experiment Plan And Result

Use the existing tracker or a section of `research/experiments.md` or `research/<topic>.md`. Keep the initial plan and add the actual execution record, including any changes:

```markdown
### Experiment: <id>
- Question/hypothesis and falsifying outcome:
- Baseline, treatment, simpler alternative, and controlled variables:
- Metrics, evaluation distribution, holdout, and checkpoint selection:
- Independent units, training/evaluation seeds, and planned repetitions:
- Budget basis, runtime/resource bound, run sequence, and stop condition:
- Known command and resolved configuration; missing prerequisites:
- State: planned / running / completed / failed / unrun

#### Actual execution (only for work performed)
- Code commit and local diff identity:
- Dataset/version/split and initial checkpoint identity:
- Resolved config and command:
- Software/simulator/device versions and determinism settings:
- Training seeds, evaluation seeds, runs/episodes completed:
- Exit status and completion evidence:
- Logs/checkpoints/metrics artifacts:
- Results and uncertainty method; failures and negative results:
- Changes from plan and comparison limitations:
- Supported conclusion, alternatives not excluded, and next step:
```

Never insert synthetic numbers into actual-result fields. An unexecuted plan remains unrun; an installed dependency or successful smoke test is not a reproduced paper result.
