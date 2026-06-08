# Weekly Digest ENOBUFS 修复记录

## 背景

- 记录时间：2026-06-09
- 影响仓库：`mss-boot`、`mss-boot-admin-antd`
- 失败工作流：`Weekly Digest`
- 失败步骤：`Create weekly digest issue`

## 现象

GitHub Actions 日志显示 reusable workflow 在读取 Actions runs 时失败：

```text
Error: spawnSync gh ENOBUFS
repos/<repo>/actions/runs?created=>=2026-05-31&per_page=100
```

原因是 GitHub Actions runs API 返回体包含大量 runner、repository、commit 等嵌套信息，Node `execFileSync` 默认 buffer 被打满。

## 修复

- 将 reusable `weekly-digest.yml` 的 `gh()` helper 增加 `maxBuffer: 20 * 1024 * 1024`。
- 对 workflow runs 查询使用 `gh api --jq` 投影，只保留 digest 需要的字段。
- 将 `per_page` 从 100 降到 50，避免定时 digest 被历史 run 噪声拖垮。

## 后续验证

- 推送 `.github` 后，重新运行失败的 `Weekly Digest`。
- 如果仍失败，再检查 issue create/edit 权限和 label 创建逻辑。
- 外部仓库只需要继续引用 `mss-boot-io/.github/.github/workflows/weekly-digest.yml@main`。

