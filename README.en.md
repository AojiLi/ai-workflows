# AI Workflows

Language: English | [中文](./README.zh-CN.md)

A reusable AI skill for carrying out model training and evaluation.

## Skills

| Skill | Purpose |
| --- | --- |
| [model-training](./skills/model-training/SKILL.md) | Follow established practices, carry out model or RL training and evaluation, and decide reasonably whether to continue. |

## Install

Run from the project where you want to use the skill.

This `model-training` branch contains only the `model-training` skill. The commands below install that branch.

Install the skill:

```bash
npx skills@latest add 'AojiLi/ai-workflows#model-training'
```

Install for Codex:

```bash
npx skills@latest add 'AojiLi/ai-workflows#model-training' --skill model-training --agent codex --yes
```

## Use

```text
Use $model-training to train and evaluate this policy. Consult established practices, proceed beyond necessary checks within the agreed budget, and report remaining gaps honestly.
```

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
    `-- model-training/
```
