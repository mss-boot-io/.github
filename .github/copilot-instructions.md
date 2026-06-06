# mss-boot-io GitHub Operations Instructions

This repository hosts organization-wide community health files, reusable
workflow guidance, and governance notes for `mss-boot-io`.

When working here:

- Keep changes small, reviewable, and suitable for public open source
  collaboration.
- Prefer GitHub-native automation before adding external bots or services.
- Do not store secrets, account credentials, private endpoints, or personal
  data in repository files, issue templates, workflows, or examples.
- Treat Copilot code review, issue drafting, Dependabot, CodeQL, Scorecard,
  PR Guard, Docs Drift, and weekly digest workflows as advisory automation.
  Maintainers still decide scope, security risk, release timing, and merges.
- Frontend Cloudflare alpha, beta, and prod deployments must stay manual.
  Do not convert Cloudflare workflows into automatic PR or push deploys.
- Durable organization memory belongs in `mss-boot-docs/aigc` or the local
  repository `aigc/prompts/` directory. Use lowercase kebab-case filenames.
- Use neutral, verifiable language and include reproducible validation steps
  when changing governance, workflow, or release process files.
