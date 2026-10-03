<a id="english"></a>

# AI Workflows

Language: English | [中文](#user-content-zh-cn)

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
    |-- grill-me/
    |-- model-training/
    `-- research/
```

<a id="zh-cn"></a>

# AI 使用技巧与工作方法

语言版本：[English](#user-content-english) | 中文

一个精简的 AI skills 库，用于梳理计划、调研一手资料和推进模型训练，可安装到实际项目中使用。

## Skills

| Skill | 用途 |
| --- | --- |
| [grill-me](./skills/grill-me/SKILL.md) | 一次问一个问题，梳理计划中的假设和决策；能从代码中找到答案的，先检查代码。 |
| [research](./skills/research/SKILL.md) | 让后台 agent 调研一手资料，在项目中保存带来源引用的 Markdown 报告。 |
| [model-training](./skills/model-training/SKILL.md) | 参考成熟做法，实际推进模型或 RL 训练与评估，并合理判断何时继续或停止。 |

## 安装

在需要使用 skills 的项目目录中运行。

精简后的技能库和 `model-training` 目前位于 `codex/simplify-skills` 分支。以下命令安装该分支；合并到 `main` 后可省略 `#codex/simplify-skills`。

安装全部 skills：

```bash
npx skills@latest add 'AojiLi/ai-workflows#codex/simplify-skills'
```

为 Codex 安装单个 skill：

```bash
npx skills@latest add 'AojiLi/ai-workflows#codex/simplify-skills' --skill grill-me --agent codex --yes
npx skills@latest add 'AojiLi/ai-workflows#codex/simplify-skills' --skill research --agent codex --yes
npx skills@latest add 'AojiLi/ai-workflows#codex/simplify-skills' --skill model-training --agent codex --yes
```

## 使用

```text
使用 $grill-me 帮我梳理这个实验计划：[描述计划]。
```

```text
使用 $research 调研官方 PPO 训练建议和实现，在这个项目中保存带引用的报告。
```

```text
使用 $model-training 训练并评估这个策略。先参考成熟做法，必要检查通过后按约定预算进入正式训练，如实报告剩余差距。
```

## 训练项目的 AGENTS.md

希望训练任务默认使用 `model-training` 时，将 [AGENTS.md 模板](./skills/model-training/assets/AGENTS.md.template) 合并到实际项目根目录的 `AGENTS.md`，保留已有规则。英文模板只负责路由，具体训练流程由 skill 维护。

安装 skill 后，模板位于 `.agents/skills/model-training/assets/AGENTS.md.template`。安装不会自动创建或修改项目的 `AGENTS.md`。

## 目录结构

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
