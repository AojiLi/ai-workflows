<a id="english"></a>

# AI Workflows

Language: English | [中文](#user-content-zh-cn)

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

<a id="zh-cn"></a>

# AI 使用技巧与工作方法

语言版本：[English](#user-content-english) | 中文

一个可安装到实际项目中使用的 AI skill，用于推进模型训练与评估。

## Skills

| Skill | 用途 |
| --- | --- |
| [model-training](./skills/model-training/SKILL.md) | 参考成熟做法，实际推进模型或 RL 训练与评估，并合理判断何时继续或停止。 |

## 安装

在需要使用此 skill 的项目目录中运行。

此 `model-training` 分支仅保留 `model-training` 技能。以下命令安装该分支。

安装此 skill：

```bash
npx skills@latest add 'AojiLi/ai-workflows#model-training'
```

为 Codex 安装：

```bash
npx skills@latest add 'AojiLi/ai-workflows#model-training' --skill model-training --agent codex --yes
```

## 使用

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
    `-- model-training/
```
