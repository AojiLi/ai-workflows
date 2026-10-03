# AI Workflows

Language: English | [中文](./README.zh-CN.md)

A small library of reusable AI skills for clarifying plans, researching primary sources, and carrying out model training.

## Skills

| Skill | Purpose |
| --- | --- |
| [grill-me](./skills/grill-me/SKILL.md) | Examine a plan's assumptions and decisions, one question at a time. Inspect the codebase for answers available there. |
| [research](./skills/research/SKILL.md) | Delegate primary-source research to a background agent and save a cited Markdown report in the project. |
| [model-training](./skills/model-training/SKILL.md) | Follow established practices, carry out model or RL training and evaluation, and decide reasonably whether to continue. |

## Install

Run from the project where you want to use the skills.

The simplified library and `model-training` are currently on `codex/simplify-skills`. The commands below install that branch; omit `#codex/simplify-skills` after it is merged into `main`.

Install all skills:

```bash
npx skills@latest add 'AojiLi/ai-workflows#codex/simplify-skills'
```

Install one skill for Codex:

```bash
npx skills@latest add 'AojiLi/ai-workflows#codex/simplify-skills' --skill grill-me --agent codex --yes
npx skills@latest add 'AojiLi/ai-workflows#codex/simplify-skills' --skill research --agent codex --yes
npx skills@latest add 'AojiLi/ai-workflows#codex/simplify-skills' --skill model-training --agent codex --yes
```

## Use

```text
Use $grill-me to examine this experiment plan: [describe the plan].
```

```text
Use $research to investigate the official PPO training recommendations and implementations, and save a cited report in this project.
```

```text
Use $model-training to train and evaluate this policy. Consult established practices, proceed beyond necessary checks within the agreed budget, and report remaining gaps honestly.
```

## Structure

```text
ai-workflows/
|-- README.md
|-- README.en.md
|-- README.zh-CN.md
`-- skills/
    |-- README.md
    |-- grill-me/
    |-- model-training/
    `-- research/
```
