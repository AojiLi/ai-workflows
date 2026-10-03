# AI 使用技巧与工作方法

语言版本：[English](./README.md) | 中文

一个精简的 AI skills 库，用于梳理计划、调研一手资料和推进模型训练，可安装到实际项目中使用。

## Skills

| Skill | 用途 |
| --- | --- |
| [grill-me](./skills/grill-me/SKILL.md) | 一次问一个问题，梳理计划中的假设和决策；能从代码中找到答案的，先检查代码。 |
| [research](./skills/research/SKILL.md) | 让后台 agent 调研一手资料，在项目中保存带来源引用的 Markdown 报告。 |
| [model-training](./skills/model-training/SKILL.md) | 参考成熟做法，实际推进模型或 RL 训练与评估，并合理判断何时继续或停止。 |

## 安装

在需要使用 skills 的项目目录中运行。

精简后的技能库和 `model-training` 目前位于 `model-training` 分支。以下命令安装该分支；合并到 `main` 后可省略 `#model-training`。

安装全部 skills：

```bash
npx skills@latest add 'AojiLi/ai-workflows#model-training'
```

为 Codex 安装单个 skill：

```bash
npx skills@latest add 'AojiLi/ai-workflows#model-training' --skill grill-me --agent codex --yes
npx skills@latest add 'AojiLi/ai-workflows#model-training' --skill research --agent codex --yes
npx skills@latest add 'AojiLi/ai-workflows#model-training' --skill model-training --agent codex --yes
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
