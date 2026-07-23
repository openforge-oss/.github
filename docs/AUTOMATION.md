# Automation & security stack

OpenForge repositories use a layered set of automated agents for code review,
dependency/version management, and supply-chain security. This document is the
source of truth for what runs, what's config-as-code, and what an org owner must
enable once by hand.

## At a glance

| Agent | Purpose | How it's enabled | Owner action needed? |
|-------|---------|------------------|----------------------|
| **CodeRabbit** | AI pull-request review & summaries | `.coderabbit.yaml` per repo + GitHub App | ✅ install the App (once, org-wide) |
| **Dependabot — version updates** | Weekly PRs bumping outdated deps | `.github/dependabot.yml` per repo | No |
| **Dependabot — security updates & alerts** | Auto-PRs / alerts for vulnerable deps | GitHub setting | ✅ enable org-wide (once) |
| **Dependency Review** | Blocks PRs adding vulnerable/malicious deps | `dependency-review.yml` workflow | No (needs dependency graph, on by default for public repos) |
| **Dependency Audit** | Weekly outdated-package report | `dependency-audit.yml` workflow | No |
| **CodeQL** | SAST for supported languages | Org workflow template | Adopt per repo (not Dart) |
| **Secret scanning + push protection** | Blocks committed secrets | GitHub setting | ✅ enable org-wide (once) |
| **Socket** *(optional)* | Behavioral malware detection in deps | GitHub App | ✅ install if desired |

## Config-as-code (already in the repos)

- **`.coderabbit.yaml`** — CodeRabbit behavior (auto-review on `main`/`develop`,
  path-specific instructions). Present in each code repo.
- **`.github/dependabot.yml`** — weekly version-update PRs for every ecosystem in
  the repo (e.g. `pub` for Dart, `github-actions`).
- **`.github/workflows/dependency-review.yml`** — on every PR, fails if it
  introduces a dependency with a known vulnerability or a malicious-package
  advisory (GitHub Advisory Database), or a disallowed license.
- **`.github/workflows/dependency-audit.yml`** — weekly report of outdated
  packages (informational; Dependabot files the actual bump PRs).

New repos: copy these four files, or add the **org workflow templates** (Actions
→ New workflow → "By OpenForge") for CodeQL and Dependency Review.

## One-time org-owner setup (needs `admin:org` / web UI)

These can't be scripted with a standard token — do them once in the browser:

1. **Install CodeRabbit** — <https://github.com/apps/coderabbitai> → Install →
   choose the OpenForge org → All repositories. Free for open source. The
   per-repo `.coderabbit.yaml` then drives its behavior.
2. **Enable org-wide security defaults** — Org → Settings → **Code security**:
   - Dependabot **alerts** + **security updates**: enable, and "Enable for new
     repositories".
   - **Secret scanning** + **Push protection**: enable + "for new repositories".
   - (Optional) Create a **Code security configuration** and apply it to all
     repos so the above are enforced automatically on every future repo.
3. **(Optional) Deeper malware detection** — install **Socket**
   (<https://github.com/apps/socket-security>) for behavioral/supply-chain
   malware analysis beyond the GitHub Advisory Database.
4. **(Optional) Require checks org-wide** — Org → Settings → **Rules → Rulesets**
   to require the review/security checks on every repo's default branch. (Needs
   the `admin:org` scope if done via API.)

## Notes on Dart / Flutter

- **CodeQL does not support Dart.** Dart repos (like `leak_sentinel`) rely on
  `dart analyze`, `custom_lint`, and the test suite in CI instead.
- Dependabot **does** support the `pub` ecosystem, so version updates and
  security alerts work for Dart dependencies.
- The GitHub dependency graph understands `pubspec.yaml`, so Dependency Review
  covers Dart PRs too.
