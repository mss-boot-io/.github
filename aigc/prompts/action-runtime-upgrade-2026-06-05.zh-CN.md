# Actions runtime 升级记忆

- 日期：2026-06-05
- 背景：主干 CI 已全绿后，GitHub Actions 提示 `actions/checkout@v4` 仍运行在 Node.js 20 runtime；GitHub 将在 2026-06-16 默认切到 Node 24，并在 2026-09-16 移除 Node 20。
- 处理：组织 `.github` 仓库的本地 workflow 将 `actions/checkout` 升级到 `v6`，降低后续组织级模板出现黄色弃用提示或未来失败的概率。
- 验证：通过 GitHub API 确认 `actions/checkout` 存在 `refs/tags/v6`，提交后由 PR CI / guard 验收。

