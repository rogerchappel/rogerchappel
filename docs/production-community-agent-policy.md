# Production And Community Agent Policy
Version: 2026-04-28

Use this policy for production SaaS, company/client, and community OSS repositories.

## Core Rule

Work must be reviewable, reversible, verifiable, and safe. Production and maintainer trust beat raw speed.

## Required Workflow

Before editing, state:

1. objective
2. expected blast radius
3. files likely to change
4. commit plan
5. verification plan
6. risk level: low, medium, or high

Then:

1. create or confirm a branch from latest `main`
2. make the smallest coherent change
3. review `git status`
4. review `git diff`
5. stage only related files
6. run the smallest relevant verification
7. commit atomically
8. rebase on `main` before PR
9. open or prepare a PR
10. return a review pack

## Branch And Merge Policy

- Work on a branch.
- Use atomic commits.
- Open or prepare a PR.
- Do not merge without explicit human approval.
- Do not rewrite shared history unless explicitly instructed.

## Commit Policy

Use Conventional Commits.

One commit equals one reviewable intent.

Allowed types: `feat:`, `fix:`, `test:`, `docs:`, `refactor:`, `ci:`, `chore:`, `perf:`, `types:`.

Do not mix unrelated behaviour, tests, docs, formatting, dependencies, generated files, CI, or config changes.

## Stop Before Touching

Ask before changing:

- auth
- security
- payments, billing, or Stripe
- production data
- migrations
- secrets or environment variables
- public API compatibility
- licensing
- telemetry/privacy behaviour
- destructive commands
- production configuration
- major dependency upgrades

## Production Data

Never delete, overwrite, or mutate production data unless explicitly instructed.

For data sync work:

- dry-run mode is required
- idempotent upsert is preferred
- validation before write is required
- manual run command is required
- failure report is required
- no deletes unless explicitly approved

## Verification

Every task must include verification. Use the smallest relevant check first: targeted unit test, integration test, typecheck, lint, build, smoke command, or manual QA checklist.

If verification cannot be run, say why and provide the exact command that should be run.

## Review Pack

Every completed task must return:

```md
## Review Pack
Repo:
Branch:
PR:
Task:
Status: done / blocked / needs review
Summary:
Commits:
Files changed:
Verification:
Risk level:
Rollback plan:
Human decision needed:
Next recommended task:
```

## Blocker

If blocked, return:

```md
## Blocker
What blocked:
Why it matters:
Options:
Recommended option:
Human decision needed:
```
