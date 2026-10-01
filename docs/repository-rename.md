# 仓库改名为 ai-workflows

选定的 GitHub 仓库名是 `AojiLi/ai-workflows`，中文展示标题是“AI 使用技巧与工作方法”。它仍是可安装的技能库，也包含项目规则和使用说明。

## 当前状态

- GitHub 已改名为 `AojiLi/ai-workflows`，新 Git 地址和已有分支已通过实际访问检查。
- 文档已更新新标题、目录示例和安装地址，本地 `origin` 已指向新地址。
- 具身智能研究技能及改名准备在 `codex/embodied-research` 分支；尚未合并到 `main`。
- 云环境的安装和启动配置兼容 `/workspace/ai-workflows` 与 `/workspace/codex-skills`，工具和依赖目录保持原位。

## 本地 checkout 与远端地址

其他已有 checkout 可更新本地 Git remote，并检查新地址：

```bash
git remote set-url origin https://github.com/AojiLi/ai-workflows.git
git ls-remote origin HEAD
```

当前云环境的 checkout 目录不会因为修改远端名称自动改名；现有 `/workspace/codex-skills` 可以继续使用。将来新环境可能使用新目录名，保存的启动配置已兼容两者。

## 合并和安装

审阅并合并 `codex/embodied-research` 分支，让默认分支包含新技能及这些文档。仓库改名已经完成，分支合并是另一个步骤。

在实际项目目录中安装：

```bash
npx skills@latest add AojiLi/ai-workflows --skill embodied-research --agent codex --yes
```

如果分支还没合并，可指定来源分支：

```bash
npx skills@latest add 'AojiLi/ai-workflows#codex/embodied-research' --skill embodied-research --agent codex --yes
```

已安装项目应检查自己的技能来源/锁定记录，必要时从新地址重新安装；先保留并检查本地修改。

## 状态维护

分支合并后，更新这份说明中的分支状态。已安装的技能不会因为仓库改名自动更新；按项目约定刷新来源和版本记录。
