# Installing Research Companion for Codex

This document is written so a Codex agent can read it and perform the installation steps directly.

## How Codex Discovers Skills

Codex discovers personal skills from `~/.agents/skills/` at startup. To install this skill, create `~/.agents/skills/research-companion` as either:

- a copied directory
- a symlink to this repository's `skills/research-companion/` directory

These instructions assume the current working directory is the root of this repository.

## Safety Rules

Before running any installation command:

1. Check whether `~/.agents/skills/research-companion` already exists.
2. If it already exists, stop and ask the user whether to replace it or keep the existing installation.
3. If the user has not chosen an installation mode yet, ask them to choose `Option A` or `Option B`.

## Option A: Global Copy

Choose this if the user wants a standalone personal installation that does not depend on this repository after setup.

```bash
mkdir -p ~/.agents/skills
cp -R skills/research-companion ~/.agents/skills/
```

This creates:

```text
~/.agents/skills/research-companion/
```

## Option B: Project-Backed Symlink

Choose this if the user wants this repository to remain the source of truth, so future edits in the repository are picked up automatically.

```bash
mkdir -p ~/.agents/skills
ln -s "$(pwd)/skills/research-companion" ~/.agents/skills/research-companion
```

This creates:

```text
~/.agents/skills/research-companion -> <repo>/skills/research-companion
```

## Verify the Installation

For a copied install:

```bash
ls -la ~/.agents/skills/research-companion
```

For a symlink install:

```bash
ls -la ~/.agents/skills/research-companion
readlink ~/.agents/skills/research-companion
```

Expected result:

- `~/.agents/skills/research-companion` exists
- `SKILL.md` and `memory-templates.md` are available through that path

## Finish

1. Restart Codex so it rescans `~/.agents/skills/`.
2. Start a new Codex session.
3. Activate the skill by saying `research companion`, `科研伙伴`, or `研究搭档`.

On first use, the skill can later register the companion's custom name in `AGENTS.md`, so no manual `AGENTS.md` edit is required during installation.
