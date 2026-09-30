<a id="english"></a>

# Codex Engineering And Research Skills

Language: English | [中文](#user-content-zh-cn)

![Anime-style Codex skills engineering workspace](./assets/codex-skills-hero-engineering.png)

Reusable Codex skills for robotics and embodied-AI research, stress-testing engineering plans, investigating primary sources, reviewing repository-backed technical decisions, and establishing durable project settings.

This repository focuses on engineering and robotics research workflows. General idea-validation, decision, writing, frontend-design, and algorithmic-art skills live in [AojiLi/codex-general-skills](https://github.com/AojiLi/codex-general-skills).

## Operating Model

- Clarify the engineering question before implementation.
- Inspect relevant repository evidence before giving technical advice.
- For research changes, inspect papers and author implementations, reuse applicable components, and define a discriminating experiment before adding complexity.
- Use subagents when repository size or context pressure makes independent coverage useful.
- Keep recommendations small, reversible, testable, and explicit about unknowns.
- Keep durable project facts in authoritative docs and load optional context only when needed.

## Skills

### Planning And Stress Testing

#### [grill-me](./skills/grill-me/SKILL.md)

Use it when you already have an engineering plan or design and want its hidden decisions challenged. It walks the decision tree one question at a time, gives a recommended answer with each question, and explores the repository itself when the answer is discoverable from code.

```text
Use $grill-me to stress-test this API migration plan: [describe the plan].
```

### Research And Engineering Review

#### [embodied-research](./skills/embodied-research/SKILL.md)

Use it for robotics algorithms, robot learning, model training, baseline reproduction, and embodied-AI simulation ideas. It investigates original papers and actual implementations, identifies reusable components, and proposes the smallest experiment that can test the hypothesis. It distinguishes reported claims, inspected code, observed results, and assumptions; training runs stay within the authorized scope and budget.

```text
Use $embodied-research to investigate whether longer observation history helps this policy recover from occlusion. Inspect the existing baseline and author implementations, then propose a reuse plan and controlled experiment. Do not start training yet.
```

#### [research](./skills/research/SKILL.md)

Use it when an engineering question depends on current documentation, APIs, specifications, source code, or other primary evidence. It delegates the reading to a background agent, traces important claims to first-party sources, and writes one cited Markdown report into the repository's existing research location.

```text
Use $research to investigate the current WebAuthn passkey APIs and save the findings in this repo.
```

#### [engineering-decision-review](./skills/engineering-decision-review/SKILL.md)

Use it for architecture, refactoring, module design, migrations, technical tradeoffs, risk review, or implementation strategy that depends on an existing repository. It maps the relevant repository surface, reports coverage and blind spots, uses targeted subagent lanes when useful, builds a current-system model, compares realistic options, recommends one path, and divides it into reversible slices with checks and stop conditions.

```text
Use $engineering-decision-review to decide whether this repository should split the billing module into a separate service.
```

### Project Setup

#### [codex-project-settings](./skills/codex-project-settings/SKILL.md)

Use it when starting long-term Codex work in a repository or repairing an existing setup. It inspects and classifies the repository, summarizes the evidence and blind spots, asks you to confirm its project understanding, then creates or safely merges the smallest useful setup: native `AGENTS.md` guidance, optional on-demand `CONTEXT.md`, and repo-local skills the project actually needs. When present, `CONTEXT.md` uses explicit routing and soft and hard size budgets.

```text
Use $codex-project-settings to initialize this repository for long-term Codex work.
```

## Install

Install all skills:

```bash
npx skills@latest add AojiLi/codex-skills
```

Install one skill:

```bash
npx skills@latest add AojiLi/codex-skills --skill grill-me
npx skills@latest add AojiLi/codex-skills --skill research
npx skills@latest add AojiLi/codex-skills --skill engineering-decision-review
npx skills@latest add AojiLi/codex-skills --skill codex-project-settings
npx skills@latest add AojiLi/codex-skills --skill embodied-research
```

## Use In A Robotics Project

Run this from the actual research project's directory to install only the research workflow for Codex:

```bash
npx skills@latest add AojiLi/codex-skills --skill embodied-research --agent codex --yes
```

Installing a skill does not create project instructions or install training/simulation dependencies. See the [robotics project setup guide (中文)](./docs/robotics-project-setup.md) and [AGENTS.md template (中文)](./docs/templates/robotics-AGENTS.md) for project-level routing, research records, usage checks, and updates. Merge the template with existing project rules rather than overwriting them.

## Codex Project Settings Framework

The reusable project baseline is documented in [codex_agent_framework.md](./codex_agent_framework.md). Its selective context model is:

- `AGENTS.md`: natively discovered repository commands, rules, verification, and routing.
- `CONTEXT.md`: optional on-demand durable project facts and invariants.
- `.agents/skills/`: optional project-specific workflows.

## Structure

```text
codex-skills/
|-- README.md
|-- README.en.md
|-- README.zh-CN.md
|-- codex_agent_framework.md
|-- docs/
|   |-- robotics-project-setup.md
|   `-- templates/robotics-AGENTS.md
`-- skills/
    |-- grill-me/
    |-- research/
    |-- embodied-research/
    |-- engineering-decision-review/
    `-- codex-project-settings/
```

## Validation

Validate a skill with the bundled Codex validator:

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py skills/<skill-name>
```

<a id="zh-cn"></a>

# Codex Engineering And Research Skills

语言版本：[English](#user-content-english) | 中文

![二次元风格 Codex skills 工程化工作台](./assets/codex-skills-hero-engineering.png)

这是一组工程与研究专用的 Codex skills，用于机器人算法与具身智能研究、压力测试工程计划、调研一手资料、基于仓库证据审核技术决策，以及建立长期可维护的项目设置。

这个仓库关注工程和机器人研究工作流。通用 idea 验证、决策、文字编辑、前端设计和算法艺术 skills 已移动到 [AojiLi/codex-general-skills](https://github.com/AojiLi/codex-general-skills)。

## 工作模型

- 在实现前先澄清工程问题。
- 在给出技术建议前检查相关仓库证据。
- 对研究改动，先查论文和作者实现、复用适用组件，再设计能区分解释的实验，最后增加必要的新部分。
- 当仓库较大或主上下文压力较高时，使用 subagents 做独立覆盖。
- 推荐路径保持小、可逆、可测试，并明确披露未知部分。
- 把稳定项目事实放在权威文档中，只在需要时读取可选上下文。

## Skills

### 规划与压力测试

#### [grill-me](./skills/grill-me/SKILL.md)

适合已经有工程计划或设计，但希望把隐藏决策和假设问清楚的场景。它会沿着决策树一次问一个问题，每个问题都会附带推荐回答；如果答案可以从代码得到，它会先检查仓库而不是反问用户。

```text
使用 $grill-me 压力测试这个 API 迁移计划：[描述计划]。
```

### 调研与工程审核

#### [embodied-research](./skills/embodied-research/SKILL.md)

适合机器人算法、机器人学习、模型训练、基线复现和具身智能仿真 idea。它先调查原始论文和实际实现，判断可复用部分，再提出能验证假设的最小实验；区分论文报告、源码确认、本地观察与推测，并在已授权的范围和预算内开展训练。

```text
使用 $embodied-research 调查：延长观测历史能否改善策略在遮挡后的恢复？先检查当前基线和作者实现，给出复用方案与对照实验。这次不启动训练。
```

#### [research](./skills/research/SKILL.md)

适合需要核对当前文档、API、规范、源码或其他一手证据的工程问题。它会把阅读工作交给后台 agent，把重要结论追溯到官方文档、源码、spec 或 first-party API，并在仓库原有的调研位置保存一份带引用的 Markdown 报告。

```text
使用 $research 调研当前 WebAuthn passkey API，并把结果保存到这个仓库。
```

#### [engineering-decision-review](./skills/engineering-decision-review/SKILL.md)

适合依赖现有仓库的架构、重构、模块设计、迁移、技术取舍、风险审核或实现策略问题。它会检查相关仓库范围，披露已读内容和 blind spots，在有必要时使用定向 subagent lanes，建立当前系统模型，比较真实可行的选项，推荐一条路径，并把它拆成带验证和停止条件的可逆步骤。

```text
使用 $engineering-decision-review 判断这个仓库是否应该把 billing 模块拆成独立服务。
```

### 项目设置

#### [codex-project-settings](./skills/codex-project-settings/SKILL.md)

适合开始长期 Codex 项目工作，或者修复已有项目设置。它会检查并分类仓库，说明证据和 blind spots，让你确认它对项目的理解，然后建立最小够用的设置：Codex 原生发现的 `AGENTS.md`、确有需要时才创建的 `CONTEXT.md`，以及项目专用 skills。`CONTEXT.md` 存在时采用明确的读取路由、目标值和硬上限。

```text
使用 $codex-project-settings 为这个仓库建立长期 Codex 项目设置。
```

## 安装

安装全部 skills：

```bash
npx skills@latest add AojiLi/codex-skills
```

安装单个 skill：

```bash
npx skills@latest add AojiLi/codex-skills --skill grill-me
npx skills@latest add AojiLi/codex-skills --skill research
npx skills@latest add AojiLi/codex-skills --skill engineering-decision-review
npx skills@latest add AojiLi/codex-skills --skill codex-project-settings
npx skills@latest add AojiLi/codex-skills --skill embodied-research
```

## 在实际机器人项目里使用

进入实际研究项目目录，按项目安装指定的 Codex skill：

```bash
npx skills@latest add AojiLi/codex-skills --skill embodied-research --agent codex --yes
```

安装 skill 不会自动创建项目规则或安装训练/仿真依赖。参见 [项目接入说明](./docs/robotics-project-setup.md) 和 [AGENTS.md 模板](./docs/templates/robotics-AGENTS.md)，了解默认路由、研究记录、使用验收和更新方法。已有项目规则应先读再合并，不整体覆盖。

## Codex Project Settings Framework

可复用项目基线位于 [codex_agent_framework.md](./codex_agent_framework.md)。它采用选择式上下文模型：

- `AGENTS.md`：Codex 原生发现的仓库命令、规则、验证要求和路由。
- `CONTEXT.md`：可选、按需读取的稳定项目事实和约束。
- `.agents/skills/`：可选的项目专用工作流。

## 目录结构

```text
codex-skills/
|-- README.md
|-- README.en.md
|-- README.zh-CN.md
|-- codex_agent_framework.md
|-- docs/
|   |-- robotics-project-setup.md
|   `-- templates/robotics-AGENTS.md
`-- skills/
    |-- grill-me/
    |-- research/
    |-- embodied-research/
    |-- engineering-decision-review/
    `-- codex-project-settings/
```

## 验证

使用 Codex 自带 validator 检查 skill：

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py skills/<skill-name>
```
