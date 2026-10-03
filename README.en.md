# AI Workflows

Language: English | [中文](./README.zh-CN.md)

A small library of reusable AI skills for clarifying plans and researching primary sources.

## Skills

| Skill | Purpose |
| --- | --- |
| [grill-me](./skills/grill-me/SKILL.md) | Examine a plan's assumptions and decisions, one question at a time. Inspect the codebase for answers available there. |
| [research](./skills/research/SKILL.md) | Delegate primary-source research to a background agent and save a cited Markdown report in the project. |

## Install

Run from the project where you want to use the skills.

Install all skills:

```bash
npx skills@latest add AojiLi/ai-workflows
```

Install one skill for Codex:

```bash
npx skills@latest add AojiLi/ai-workflows --skill grill-me --agent codex --yes
npx skills@latest add AojiLi/ai-workflows --skill research --agent codex --yes
```

## Use

```text
Use $grill-me to examine this experiment plan: [describe the plan].
```

```text
Use $research to investigate the official PPO training recommendations and implementations, and save a cited report in this project.
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
    `-- research/
```
