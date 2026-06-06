# GitHub AI Handoff

日期：2026-06-05

## 背景

组织希望尽量把可自动化的开源运营、代码审查、依赖更新、问题整理和
流水线检查交给 GitHub 原生能力承接，降低个人维护者成本。

## 已落地

- 在组织 `.github` 仓库新增 `.github/copilot-instructions.md`，让 GitHub
  Copilot Code Review、Copilot Chat 和 Copilot coding agent 在处理组织治理
  文件时优先遵守开源、低成本、低噪音和手动发布边界。
- 在组织 `.github` 仓库新增 Dependabot、CodeQL 和 OpenSSF Scorecard 自检，
  让 reusable workflows、issue templates 和组织社区健康文件也进入 GitHub
  原生安全/供应链检查。

## 约束

- 前端 Cloudflare alpha/beta/prod 发布必须保持人工触发。
- Copilot、CodeQL、Dependabot、Scorecard、PR Guard、Docs Drift 和周报类
  自动化只提供建议与检查，最终合并、发布和安全判断仍由维护者确认。
- 任何涉及外部账号、付费计划、组织权限和安全策略的配置先记录，等待维护者
  在 GitHub 后台启用。
