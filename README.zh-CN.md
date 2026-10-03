# AI 使用技巧与工作方法

语言版本：[English](./README.md) | 中文

一个精简的 AI skills 库，用于调研一手资料和推进模型训练，可安装到实际项目中使用。

## Skills

| Skill | 用途 |
| --- | --- |
| [research](./skills/research/SKILL.md) | 让后台 agent 调研一手资料，在项目中保存带来源引用的 Markdown 报告。 |
| [model-training](./skills/model-training/SKILL.md) | 参考成熟做法，实际推进模型或 RL 训练与评估，并合理判断何时继续或停止。 |

## 安装

在需要使用 skills 的项目目录中运行。

所有 skills 在 `main` 分支中按目录维护，使用 `--skill` 即可只安装需要的技能。

安装全部 skills：

```bash
npx skills@latest add AojiLi/ai-workflows
```

为 Codex 安装单个 skill：

```bash
npx skills@latest add AojiLi/ai-workflows --skill research --agent codex --yes
npx skills@latest add AojiLi/ai-workflows --skill model-training --agent codex --yes
```

## 使用

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
    |-- model-training/
    `-- research/
```
