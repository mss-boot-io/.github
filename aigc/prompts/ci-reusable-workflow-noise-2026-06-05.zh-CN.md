# 2026-06-05 组织级 CI 噪声修复记忆

## 背景

组织级 reusable workflow 引入后，多个仓库的 Dependabot PR 被 PR Guard 和 Docs Drift 拦截，Gitee mirror 也因为浅克隆推送失败，导致开源项目首页 Actions 大面积红。

## 决策

- Dependabot 的依赖升级 PR 仍保留标题和敏感路径检查，但缺少人工 PR 正文说明时降级为 warning。
- Dependabot 只改 GitHub Actions 版本且没有文档更新时，Docs Drift 降级为 warning。
- Gitee mirror 只在 `main` push 时触发，并使用 full-depth checkout，避免 shallow update 和 delete 事件误删远端分支。

## 后续

- 人工 PR 仍必须写清测试、文档、安全、发布/回滚影响。
- workflow、部署、配置类变更仍必须同步 docs、README、CHANGELOG 或 `aigc` 记忆。
