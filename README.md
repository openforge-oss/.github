# .github

This is OpenForge's **community health** repository. It has two jobs:

1. **`profile/README.md`** renders as the organization's public landing page at
   <https://github.com/FlutterForge-V1>.
2. The files at the root of this repo (`CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`,
   `SECURITY.md`, `GOVERNANCE.md`) and the templates in `.github/` act as
   **org-wide defaults**: any OpenForge repository that doesn't ship its own
   copy inherits these automatically.

Individual repositories may override any of these with their own versions when
they need project-specific detail (for example,
[`leak_sentinel`](https://github.com/FlutterForge-V1/leak_sentinel) ships its
own `CONTRIBUTING.md` with build steps).

## Layout

```
profile/README.md              → org landing page
CODE_OF_CONDUCT.md             → default for all repos
CONTRIBUTING.md                → default for all repos
GOVERNANCE.md                  → how the org is run
SECURITY.md                    → default vulnerability policy
docs/AUTOMATION.md             → automated review & security stack (CodeRabbit, Dependabot, CodeQL, …)
.github/PULL_REQUEST_TEMPLATE.md
.github/ISSUE_TEMPLATE/config.yml
.github/dependabot.yml
.github/workflow-templates/    → CodeQL & Dependency Review starter workflows for org repos
```

See [`docs/AUTOMATION.md`](docs/AUTOMATION.md) for the full automated review and
supply-chain security setup, and the one-time org-owner steps.
