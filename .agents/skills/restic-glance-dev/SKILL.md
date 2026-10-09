---
name: restic-glance-dev
description: Maintain restic-glance-extension fork source, repository documentation and agent guidance with local ownership, evidence and runtime boundaries.
---

# Fork source maintenance

Read [README.md](../../../README.md), `pyproject.toml` and the existing source.
`src/config.py` owns environment interpretation; `src/restic.py` owns subprocess
interaction and backup queries; `src/main.py` owns HTTP/cache lifecycle;
`src/service.py` owns display transformation and `src/widget.py` owns rendering.
Repository aliases, repository URLs, command arguments and passwords are
sensitive operational data; use synthetic fixtures and bounded diagnostics.

Use Python 3.14 as declared in pyproject.toml. For documentation, validate
routes/frontmatter and compile tracked Python without importing the app.
This baseline has no tracked test suite; syntax checks do not prove timeout,
cache recovery or widget behavior. A behavioral change needs a meaningful
synthetic subprocess/cache or HTTP contract before claiming those outcomes.
The image workflow owns image construction/publication. Source maintenance
requires no real backup access, app startup, restic maintenance, restore, prune,
credential change, image release or deployment. A snapshot listing or cache
hit cannot establish a successful backup or restore.

## Repository delivery

Inspect the actual remotes, default branch and target GitHub repository before
publication. This task updates `jlapenna/restic-glance-extension`; ownership of a fork does not
authorize an upstream merge. Use a dedicated feature worktree from the freshly
fetched configured base, preserving other branches and sessions. Read
[worktree-hygiene](https://github.com/jlapenna/repo-tools/blob/main/plugins/repo-tools/skills/worktree-hygiene/SKILL.md)
and [land-pr](https://github.com/jlapenna/repo-tools/blob/main/plugins/repo-tools/skills/land-pr/SKILL.md)
for normal checked delivery and cleanup; never bypass protection or hooks.

## Harness upkeep

Use the [shared harness-maintenance workflow](https://github.com/jlapenna/repo-tools/blob/main/plugins/repo-tools/skills/harness-maintenance/SKILL.md), adapted from
[Ryan Lopopolo's field guide](https://github.com/lopopolo/harness-engineering/tree/226c8d35fb6ea3ed55467753dba6dea2b5fd5778). Corroborate observed failures and
repair their earliest owner, keeping the root guide a route and conditional
procedures in references. Preserve current contracts separately from chronology.
A source check proves structure or consistency; comparable fresh use is required
to claim improved agent behavior. Keep fork decisions local and refer to shared
implementations rather than copying them across repositories.
