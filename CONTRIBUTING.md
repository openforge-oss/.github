# Contributing to FlutterForge

Welcome! FlutterForge exists to turn the pain points Flutter engineers hit into
open-source tools — and that only works with your input. This is the org-wide
guide; individual repositories may add a `CONTRIBUTING.md` with project-specific
build and test steps, which takes precedence for that repo.

## Ways to contribute

- **Report a pain point.** The most valuable thing you can give us is a real
  problem. Open an issue on the relevant repo, or a
  [discussion](https://github.com/orgs/FlutterForge-V1/discussions) if it has no
  home yet.
- **File a bug.** Use the repo's issue templates. A minimal reproduction is gold.
- **Improve docs.** Typos, unclear steps, missing examples — all welcome.
- **Send a pull request.** Fix a bug, add a feature, or add a rule.
- **Propose a new tool.** Describe the pain and the tool you wish existed.

## Pull request flow

1. **Fork** the repo (or branch, if you're a member) and cut a branch from
   `develop`: `feat/...`, `fix/...`, `docs/...`.
2. Make your change. Keep PRs focused — one logical change each.
3. Ensure the repo's checks pass locally (formatting, analysis, tests). Each
   repo documents its exact commands.
4. Open the PR **against `develop`**. `main` is the released, protected branch.
5. Fill in the PR template and link any issue (`Closes #123`).
6. A maintainer reviews. Green CI + one approval merges.

## Expectations

- Be respectful and constructive — see the [Code of Conduct](CODE_OF_CONDUCT.md).
- Write clear commit messages.
- Add or update tests and docs alongside code.
- Update the repo's `CHANGELOG.md` when there is one.

## Recognition

Contributions of every size are credited. Sustained, high-quality contribution
is how people become maintainers — see [GOVERNANCE.md](GOVERNANCE.md).

Thank you for helping make Flutter better for everyone. 💛
