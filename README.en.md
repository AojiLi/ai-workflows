# AI Workflows

Language: English | [中文](./README.zh-CN.md)

![Anime-style Codex skills engineering workspace](./assets/codex-skills-hero-engineering.png)

Reusable AI working methods and installable skills for robotics and embodied-AI research, stress-testing engineering plans, investigating primary sources, reviewing repository-backed technical decisions, and establishing durable project settings. Start with Codex; the project setup guide also describes skill installation for Claude Code.

This repository focuses on engineering and robotics research workflows. General idea-validation, decision, writing, frontend-design, and algorithmic-art skills live in [AojiLi/codex-general-skills](https://github.com/AojiLi/codex-general-skills).

## Operating Model

- Clarify the engineering question before implementation.
- Inspect relevant repository evidence before giving technical advice.
- For research changes, inspect papers and author implementations, reuse applicable components, and define a discriminating experiment before adding complexity.
- Use subagents when repository size or context pressure makes independent coverage useful.
- Keep recommendations small, reversible, testable, and explicit about unknowns.
- Keep durable project facts in authoritative docs and load optional context only when needed.

## Skills

### Planning And Stress Testing

#### [grill-me](./skills/grill-me/SKILL.md)

Use it when you already have an engineering plan or design and want its hidden decisions challenged. It walks the decision tree one question at a time, gives a recommended answer with each question, and explores the repository itself when the answer is discoverable from code.

```text
Use $grill-me to stress-test this API migration plan: [describe the plan].
```

### Research And Engineering Review

#### [embodied-research](./skills/embodied-research/SKILL.md)

Use it for robotics algorithms, robot learning, model training, baseline reproduction, and embodied-AI simulation ideas. It investigates original papers and actual implementations, identifies reusable components, and proposes the smallest experiment that can test the hypothesis. It distinguishes reported claims, inspected code, observed results, and assumptions; training runs stay within the authorized scope and budget.

```text
Use $embodied-research to investigate whether longer observation history helps this policy recover from occlusion. Inspect the existing baseline and author implementations, then propose a reuse plan and controlled experiment. Do not start training yet.
```

#### [research](./skills/research/SKILL.md)

Use it when an engineering question depends on current documentation, APIs, specifications, source code, or other primary evidence. It delegates the reading to a background agent, traces important claims to first-party sources, and writes one cited Markdown report into the repository's existing research location.

```text
Use $research to investigate the current WebAuthn passkey APIs and save the findings in this repo.
```

#### [engineering-decision-review](./skills/engineering-decision-review/SKILL.md)

Use it for architecture, refactoring, module design, migrations, technical tradeoffs, risk review, or implementation strategy that depends on an existing repository. It maps the relevant repository surface, reports coverage and blind spots, uses targeted subagent lanes when useful, builds a current-system model, compares realistic options, recommends one path, and divides it into reversible slices with checks and stop conditions.

```text
Use $engineering-decision-review to decide whether this repository should split the billing module into a separate service.
```

### Project Setup

#### [codex-project-settings](./skills/codex-project-settings/SKILL.md)

Use it when starting long-term Codex work in a repository or repairing an existing setup. It inspects and classifies the repository, summarizes the evidence and blind spots, asks you to confirm its project understanding, then creates or safely merges the smallest useful setup: native `AGENTS.md` guidance, optional on-demand `CONTEXT.md`, and repo-local skills the project actually needs. When present, `CONTEXT.md` uses explicit routing and soft and hard size budgets.

```text
Use $codex-project-settings to initialize this repository for long-term Codex work.
```

## Install

Install all skills:

```bash
npx skills@latest add AojiLi/ai-workflows
```

Install one skill:

```bash
npx skills@latest add AojiLi/ai-workflows --skill grill-me
npx skills@latest add AojiLi/ai-workflows --skill research
npx skills@latest add AojiLi/ai-workflows --skill engineering-decision-review
npx skills@latest add AojiLi/ai-workflows --skill codex-project-settings
npx skills@latest add AojiLi/ai-workflows --skill embodied-research
```

## Use In A Robotics Project

Run this from the actual research project's directory to install only the research workflow for Codex:

```bash
npx skills@latest add AojiLi/ai-workflows --skill embodied-research --agent codex --yes
```

Installing a skill does not create project instructions or install training/simulation dependencies. See the [robotics project setup guide (中文)](./docs/robotics-project-setup.md) and [AGENTS.md template (中文)](./docs/templates/robotics-AGENTS.md) for project-level routing, research records, usage checks, and updates. Merge the template with existing project rules rather than overwriting them.

## Codex Project Settings Framework

The reusable project baseline is documented in [codex_agent_framework.md](./codex_agent_framework.md). Its selective context model is:

- `AGENTS.md`: natively discovered repository commands, rules, verification, and routing.
- `CONTEXT.md`: optional on-demand durable project facts and invariants.
- `.agents/skills/`: optional project-specific workflows.

## Structure

```text
ai-workflows/
|-- README.md
|-- README.en.md
|-- README.zh-CN.md
|-- codex_agent_framework.md
|-- docs/
|   |-- repository-rename.md
|   |-- robotics-project-setup.md
|   `-- templates/robotics-AGENTS.md
`-- skills/
    |-- grill-me/
    |-- research/
    |-- embodied-research/
    |-- engineering-decision-review/
    `-- codex-project-settings/
```

## Validation

Validate a skill with the bundled Codex validator:

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py skills/<skill-name>
```
