# Repository Agent Guide
Version: 2026-04-28

## Purpose

This repository publishes Roger Chappel's public profile and central agent workflow policy notes.

## Repository Type

Current type: personal OSS / public profile.

## Default Mode

Work on a branch unless explicitly told otherwise. Use atomic commits, keep PRs reviewable, verify before completion, and return a review pack.

## Repo Layout

- `README.md` - public GitHub profile content
- `docs/` - reusable agent workflow and repository policy notes

## Commands

Install: none

Test: none

Lint: none

Typecheck: none

Build: none

Smoke test: `git diff --check`

## Work Policy

Before editing, report:

1. objective
2. expected blast radius
3. files likely to change
4. commit plan
5. verification plan
6. risk level

## Commit Policy

Use Conventional Commits. One commit equals one reviewable intent.

Do not mix implementation, docs, dependency bumps, generated files, CI changes, config changes, or formatting-only changes unless they are part of the same reviewable intent.

## Risk Escalation

Ask before changing auth, security, payments, production data, migrations, secrets, public API compatibility, config formats, telemetry/privacy behaviour, destructive commands, or production configuration.

## PR Policy

For production, company, client, and community repositories, open or prepare a PR and do not merge without explicit human approval.

## Review Pack Required

At the end of every task, return:

```md
## Review Pack
Repo:
Branch:
PR:
Task:
Status:
Summary:
Commits:
Files changed:
Verification:
Risk level:
Rollback plan:
Human decision needed:
Next recommended task:
```
