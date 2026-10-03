# AI Workflows

Language: English | [中文](./README.zh-CN.md)

A small library of reusable AI skills for researching primary sources and carrying out model training.

## Skills

| Skill | Purpose |
| --- | --- |
| [research](./skills/research/SKILL.md) | Delegate primary-source research to a background agent and save a cited Markdown report in the project. |
| [model-training](./skills/model-training/SKILL.md) | Follow established practices, carry out model or RL training and evaluation, and decide reasonably whether to continue. |

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
npx skills@latest add AojiLi/ai-workflows --skill model-training --agent codex --yes
```

## Use

```text
Use $research to investigate the official PPO training recommendations and implementations, and save a cited report in this project.
```

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
    |-- model-training/
    `-- research/
```
