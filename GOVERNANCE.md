# FlutterForge Governance

This document describes how FlutterForge is run. It is intentionally lightweight
— we optimize for shipping useful tools and for a welcoming community, not for
process.

## Roles

- **Contributors** — anyone who opens an issue, a discussion, or a pull request.
  No commitment required; you're a contributor the moment you help.
- **Maintainers** — trusted contributors with merge rights on one or more
  repositories. They review PRs, triage issues, and cut releases.
- **Organization owners** — a small group responsible for the org itself:
  membership, security, and creating/archiving repositories.

## Becoming a maintainer

There's no application form. Maintainers are invited after a track record of:

- consistent, high-quality contributions to a repo;
- helpful, respectful participation in reviews and discussions;
- good judgment about scope ("small and sharp").

If that's you, an existing maintainer will reach out — or you can nominate
yourself in a discussion.

## Decision-making

- **Everyday changes** (bug fixes, docs, new lint rules) merge on **one
  maintainer approval** with green CI.
- **Significant changes** (new project, breaking change, changing a tool's
  scope) are proposed in a discussion and need **agreement from two
  maintainers**, with time left for objections.
- **Disagreements** are resolved by discussion first. If consensus can't be
  reached, organization owners make the final call, explained in writing.

## Project lifecycle

1. **Proposed** — an idea in a discussion. Anyone can propose.
2. **Incubating** — a repo exists; API and scope are still moving.
3. **Active** — released, documented, and maintained (e.g. `leak_sentinel`).
4. **Archived** — no longer maintained; kept read-only for history. We say so
   clearly in the README rather than letting a tool rot silently.

## Branch & release conventions (all repos)

- `main` — released, protected. No direct pushes; changes arrive via PR.
- `develop` — integration branch; PRs target this.
- Feature branches — `feat/`, `fix/`, `docs/`, `chore/`.
- [Semantic Versioning](https://semver.org) and a `CHANGELOG.md` per repo.

## Code of Conduct

All participation is governed by our [Code of Conduct](CODE_OF_CONDUCT.md).
Enforcement is handled by organization owners.
