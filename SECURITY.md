# Security Policy

This is the org-wide default policy for FlutterForge projects. A repository may
publish its own `SECURITY.md` with project-specific detail, which takes
precedence for that repo.

## Reporting a vulnerability

Please **do not** open a public issue for a suspected vulnerability.

Use GitHub's **private vulnerability reporting** on the affected repository:
`https://github.com/FlutterForge-V1/<repo>/security/advisories/new`

Include:

- the affected repository and version,
- a minimal reproduction,
- the impact as you understand it.

You can expect an acknowledgement within **5 business days**, and we'll keep you
updated as we investigate and ship a fix. Coordinated disclosure is appreciated.

## Scope note

Most FlutterForge tools are **development-time** utilities (lints, codegen, CLIs)
with no production runtime or network surface. For those, the highest-impact
"security" issues are usually **incorrect auto-fixes** or **false negatives** —
please report those the same way.
