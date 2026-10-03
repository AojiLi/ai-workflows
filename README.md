<a id="english"></a>

# AI Workflows

Language: English | [中文](#user-content-zh-cn)

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

<a id="zh-cn"></a>

# AI 使用技巧与工作方法

语言版本：[English](#user-content-english) | 中文

一个精简的 AI skills 库，用于梳理计划和调研一手资料，可安装到实际项目中使用。

## Skills

| Skill | 用途 |
| --- | --- |
| [grill-me](./skills/grill-me/SKILL.md) | 一次问一个问题，梳理计划中的假设和决策；能从代码中找到答案的，先检查代码。 |
| [research](./skills/research/SKILL.md) | 让后台 agent 调研一手资料，在项目中保存带来源引用的 Markdown 报告。 |

## 安装

在需要使用 skills 的项目目录中运行。

安装全部 skills：

```bash
npx skills@latest add AojiLi/ai-workflows
```

为 Codex 安装单个 skill：

```bash
npx skills@latest add AojiLi/ai-workflows --skill grill-me --agent codex --yes
npx skills@latest add AojiLi/ai-workflows --skill research --agent codex --yes
```

## 使用

```text
使用 $grill-me 帮我梳理这个实验计划：[描述计划]。
```

```text
使用 $research 调研官方 PPO 训练建议和实现，在这个项目中保存带引用的报告。
```

## 目录结构

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
