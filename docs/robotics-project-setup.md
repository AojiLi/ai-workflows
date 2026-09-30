# 在实际机器人项目里使用这些 Skills

这个仓库维护跨项目的研究流程。实际项目保存自己的代码、数据接口、训练命令和实验结果。云环境用于维护这个技能库；实际实验也可以在你的本地工作站、GPU 服务器或项目云环境中进行。

第一版的研究入口是 `embodied-research`：理解假设 → 查论文和作者实现 → 判断可复用部分 → 设计最小实验 → 在授权范围内实现和验证。它涵盖机器人算法、模型训练与具身智能仿真；不会因为安装就自动下载模型、安装 ROS/仿真器或启动训练。

## 1. 在实际项目里安装

进入你要做研究的项目目录，而不是这个技能库目录：

```bash
cd /path/to/your-robotics-project
npx skills@latest add AojiLi/codex-skills --skill embodied-research --agent codex --yes
```

`/path/to/your-robotics-project` 要换成真实路径。这个命令按项目安装指定技能；不加 `--global`，不必把整个技能库装进去。需要交互选择时可以去掉 `--yes`。

Codex 的项目级技能入口是 `.agents/skills/embodied-research/SKILL.md`。安装工具还可能生成技能锁定记录或链接；检查 `git status`，按团队约定决定是否共享这些安装文件。不要只复制一个 `SKILL.md` 而遗漏其 `references/`。

检查安装结果：

```bash
npx skills@latest list --agent codex
```

安装后，在项目中开始新的 Codex 会话并确认技能可见。然后可以调用：

```text
使用 $embodied-research 调查这个 idea：[研究问题]。
先核查现有基线和相关论文的作者实现，给出复用方案与最小区分实验。
这次先做调查和实验设计，不启动训练。
```

也可以说明已授权的实现范围与训练预算，让它在范围内完成实验，而不是每一步重新询问。

## 2. 用 AGENTS.md 建立项目默认规则

安装 skill 不会自动生成或修改项目的 `AGENTS.md`。如果希望遇到研究任务时默认采用这个流程，参考 [机器人项目 AGENTS.md 模板](templates/robotics-AGENTS.md)，把适用规则合并到实际项目根目录的 `AGENTS.md`。

模板可以从本仓库查看；实际项目不必永久保留整个技能库的 checkout。没有 `AGENTS.md` 时可根据模板创建；已有文件时先读再合并，不整体覆盖。补充真实可用的命令和路径，不把示例占位符当成事实。

Codex 会发现项目指导文件；技能则按任务加载。`AGENTS.md` 提供默认规则和路由，`SKILL.md` 提供完整流程。根目录有 `AGENTS.override.md` 时，它会替代同目录的 `AGENTS.md`；不要假定两者叠加。

共享的项目规则应进入 Git，才能随项目到其他机器。这个技能库自身忽略 `AGENTS.md` 和 `CONTEXT.md`，实际项目可能也有类似规则；检查自己的 `.gitignore`，明确选择共享还是只在本机使用。不要写入密钥或敏感数据。

现有的 `codex-project-settings` skill 可以协助检查和合并项目指导。如果只需要研究入口与上述规则，不必额外安装它，也不必创建完整的参考管理目录。

## 3. 按需保存研究上下文

优先使用项目已有的文档、论文记录和实验跟踪系统。缺少对应记录时，可以逐步采用：

```text
your-robotics-project/
├── AGENTS.md
├── .agents/skills/embodied-research/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/
└── research/
    ├── context.md       # 任务、接口、基线、资源约束
    ├── literature.md    # 核查过的论文与实现、可复用部分和限制
    └── experiments.md   # 假设、对照、配置、状态、实际结果
```

这三份研究记录是可选普通文档，需要规则或当前任务明确要求读取；安装技能和发布环境都不会自动继承聊天记忆。已有权威资料足够时不要重复创建。技能内的 `references/evidence-records.md` 提供轻量记录字段，未确认事实应标为未知。

## 4. 做一次真实的使用验收

挑一篇你熟悉的论文和现有基线，要求代理：

1. 找到原始论文和作者仓库，指出一个关键机制的论文位置、代码文件和实际配置。
2. 说明哪些部分可直接复用，与你的观测/动作接口有什么差异。
3. 提出能区分两种解释的最小实验，并明确未核查、未运行的事项。

检查它是否真正读过材料。网页搜索、论文正文读取和 Git 仓库访问是不同能力；仅安装技能不会提供这些工具或权限。访问受限时它应继续本地分析并说明证据缺口。

这次仓库的元数据与安装验证只证明技能能被发现和安装，不证明它已复现某篇论文，也不证明机器人训练/仿真环境已经就绪。

## 5. 维护与更新

在 `codex-skills` 修改通用工作流，验证后提交 GitHub 更新；实际项目再更新已安装的技能：

```bash
cd /path/to/your-robotics-project
npx skills@latest update embodied-research --project --yes
```

更新前检查本地改动，把项目专属规则留在项目 `AGENTS.md` 或独立的项目技能中，避免修改已安装的通用技能后被更新覆盖。安装工具版本和来源记录影响可重复性；要求严格固定版本的项目，应记录并使用经审核的仓库版本及安装方式。

Claude Code 用户可以选择 `--agent claude-code` 安装；它使用 `.claude/skills/` 入口，可能链接到安装工具维护的共享目录。项目指导文件加载方式与 Codex 不同，应按所用 Claude Code 版本配置 `CLAUDE.md`，不要假定同一套入口规则自动生效。
