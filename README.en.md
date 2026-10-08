# AI Workflows

Language: English | [中文](./README.zh-CN.md)

A small library of reusable AI skills for researching primary sources, carrying out model training, and clarifying explanations.

## Skills

| Skill | Purpose |
| --- | --- |
| [research](./skills/research/SKILL.md) | Delegate primary-source research to a background agent and save a cited Markdown report in the project. |
| [paper-reading](./skills/paper-reading/SKILL.md) | Read a paper through author background, its original abstract and explanation, a method flowchart, and actual results. |
| [model-training](./skills/model-training/SKILL.md) | Follow established practices, carry out model or RL training and evaluation, and decide reasonably whether to continue. |
| [wait-what](./skills/wait-what/SKILL.md) | Ask the agent to explain again with missing context and simpler language. Imported from Matt Pocock; invoked manually. |
| [diagnosing-bugs](./skills/diagnosing-bugs/SKILL.md) | Diagnose hard bugs and performance regressions through reproduction, ranked hypotheses, targeted probes, and regression checks. Imported from Matt Pocock. |
| [grilling](./skills/grilling/SKILL.md) | Stress-test plans, decisions, and ideas through dependency-aware rounds of questions and recommended answers. Imported from Matt Pocock. |

## Install

Run from the project where you want to use the skills.

Skills are maintained in separate directories on `main`. Use `--skill` to install only the skill you need.

Install all skills:

```bash
npx skills@latest add AojiLi/ai-workflows
```

Install one skill for Codex:

```bash
npx skills@latest add AojiLi/ai-workflows --skill research --agent codex --yes
npx skills@latest add AojiLi/ai-workflows --skill paper-reading --agent codex --yes
npx skills@latest add AojiLi/ai-workflows --skill model-training --agent codex --yes
npx skills@latest add AojiLi/ai-workflows --skill wait-what --agent codex --yes
npx skills@latest add AojiLi/ai-workflows --skill diagnosing-bugs --agent codex --yes
npx skills@latest add AojiLi/ai-workflows --skill grilling --agent codex --yes
```

## Use

```text
Use $grilling to stress-test this plan: [describe the plan].
```

```text
Use $diagnosing-bugs to investigate this failure: [symptom, logs, and reproduction steps].
```

```text
Use $paper-reading to explain this paper: [attach PDF or provide a paper link].
```

```text
Use $research to investigate the official PPO training recommendations and implementations, and save a cited report in this project.
```

```text
Use $model-training to train and evaluate this policy. Consult established practices, proceed beyond necessary checks within the agreed budget, and report remaining gaps honestly.
```

```text
Use $wait-what to explain that again with the context I am missing.
```

Source and MIT license details: [wait-what](./skills/wait-what/SOURCE.md), [diagnosing-bugs](./skills/diagnosing-bugs/SOURCE.md), and [grilling](./skills/grilling/SOURCE.md).

## Project Instructions for Training

To apply `model-training` to training tasks by default, merge the [AGENTS.md template](./skills/model-training/assets/AGENTS.md.template) into your project's root `AGENTS.md`, preserving existing instructions. The English template routes training tasks to the skill, which contains the training workflow.

After installing the skill, the template is available at `.agents/skills/model-training/assets/AGENTS.md.template`. Installation does not create or update your project's `AGENTS.md` automatically.

## Structure

```text
ai-workflows/
|-- README.md
|-- README.en.md
|-- README.zh-CN.md
`-- skills/
    |-- README.md
    |-- diagnosing-bugs/
    |-- grilling/
    |-- model-training/
    |-- paper-reading/
    |-- research/
    `-- wait-what/
```
