# Contributing

Thanks for helping improve `mss-boot-io`.

## Before opening an issue

- Search existing issues and discussions.
- For bugs, include the affected repository, version or commit, environment,
  reproduction steps, expected behavior, actual behavior, and logs.
- For feature requests, describe the user problem, proposed behavior, trade-offs,
  and whether the change affects compatibility.
- Do not report vulnerabilities in public issues. Follow `SECURITY.md`.

## Pull request expectations

- Use a Conventional Commits style title, for example `fix(admin): handle empty
  language header`.
- Keep the change scoped. Split unrelated backend, frontend, and docs work into
  separate pull requests when possible.
- Fill in the PR template, including tests, docs, security impact, and release
  impact.
- Update documentation when behavior, configuration, APIs, release environments,
  or deployment steps change.
- Add or update tests for behavior changes.

## Local quality checks

Common checks by repository:

- `mss-boot`: `go test ./...`
- `mss-boot-admin`: `make test`
- `mss-boot-admin-antd`: `pnpm install --frozen-lockfile && pnpm lint && pnpm test && pnpm build:local`
- `mss-boot-docs`: `pnpm install --frozen-lockfile && pnpm build`

## AI-assisted contributions

AI agents are welcome as assistants, but contributors remain responsible for:

- Reading the surrounding code before changing it.
- Verifying generated code and documentation.
- Avoiding fabricated APIs, dependencies, benchmarks, or compatibility claims.
- Recording durable project memory in `mss-boot-docs/aigc/` when the change
  affects organization workflow or release policy.
