---
name: mcamner-fork-boundary
description: Use when working in the MCamner/excalidraw fork to ensure all patches, experiments, automation, and PR decisions stay scoped to the user's fork unless upstream contribution is explicitly requested.
---

# MCamner Excalidraw Fork Boundary

## Purpose

This repository is the user's personal fork:

```text
MCamner/excalidraw
```

It is forked from upstream:

```text
excalidraw/excalidraw
```

The default operating rule is:

```text
Work against MCamner/excalidraw only.
Do not open pull requests upstream unless the user explicitly asks for an upstream contribution.
```

## Rules

- Treat `MCamner/excalidraw` as the active working repository.
- Keep local patches, experiments, MQ integrations, docs, skills, and automation in the user's fork.
- Do not create pull requests to `excalidraw/excalidraw` by default.
- Do not push directly to, target, or otherwise modify upstream.
- Only propose upstream contribution when the change is clearly general-purpose and the user explicitly asks for it.
- If creating branches, create them in `MCamner/excalidraw`.
- If opening pull requests, target `MCamner/excalidraw` unless the user explicitly says to target upstream.
- Preserve upstream compatibility where practical so the fork can still be synced.

## Safe defaults

Use these remotes locally:

```bash
origin   https://github.com/MCamner/excalidraw.git
upstream https://github.com/excalidraw/excalidraw.git
```

Use this pattern for work:

```bash
git checkout master
git pull origin master
git checkout -b mq/<short-task-name>
```

Push only to the user's fork:

```bash
git push origin mq/<short-task-name>
```

## Before any PR

Ask and confirm the target:

```text
Should this PR target MCamner/excalidraw or upstream excalidraw/excalidraw?
```

Default answer unless the user says otherwise:

```text
Target MCamner/excalidraw only.
```

## Upstream contribution exception

Only target `excalidraw/excalidraw` when all are true:

- The user explicitly asks for an upstream PR.
- The change is not MQ-specific.
- The change is not personal workflow-specific.
- The change does not contain local paths, private automation assumptions, or user-specific docs.
- The fork is synced cleanly with upstream before preparing the contribution.
