# Research Companion

A persistent research thinking partner for academic/scientific projects, available as a Claude Code plugin and a Codex skill.

## Features

- Named companion with custom personality
- Layered memory system (L1 core / L2 sessions / L3 archive)
- Cross-session continuity
- Context window monitoring hook
- Bilingual (Chinese/English)

## Installation

### Claude Code (via Plugin Marketplace)

**Step 1:** Add the marketplace:

```bash
/plugin marketplace add rainshed/research-companion
```

**Step 2:** Install the plugin:

```bash
/plugin install research-companion@rainshed-research-companion
```

### Codex

Codex uses native skill discovery from `$CODEX_HOME/skills/` (default: `~/.codex/skills/`).

Ask Codex:

```text
Install the `research-companion` skill from https://github.com/rainshed/research-companion/tree/main/codex-skills/research-companion using the built-in GitHub skill installer, then remind me to restart Codex.
```

Manual instructions: [`.codex/INSTALL.md`](.codex/INSTALL.md) or install directly from [`codex-skills/research-companion`](https://github.com/rainshed/research-companion/tree/main/codex-skills/research-companion)

### Optional: Context Monitor

The context window monitor hook uses [cozempic](https://github.com/eastlondoner/cozempic) to track context usage and warn you before running out of space. Install it with:

```bash
npm install -g cozempic
```

The plugin works without cozempic — the context monitor will simply be inactive.

## Usage

Say `科研伙伴`, `research companion`, or `研究搭档` in Claude Code or Codex to activate.

On first use, the companion will ask you to give it a name. After that, you can also activate it by saying that name.

## Repository Structure

```
research-companion/
├── .codex/
│   └── INSTALL.md           # Codex installation runbook
├── .claude-plugin/
│   ├── plugin.json          # Plugin manifest
│   └── marketplace.json     # Marketplace catalog
├── skills/
│   └── research-companion/
│       ├── SKILL.md          # Claude Code skill (writes CLAUDE.md)
│       └── memory-templates.md
├── codex-skills/
│   └── research-companion/
│       ├── SKILL.md          # Codex skill (writes AGENTS.md)
│       └── memory-templates.md
├── hooks/
│   └── hooks.json           # Context monitor hook config
├── scripts/
│   └── context-monitor.sh   # Context window usage monitor
└── README.md
```

## License

MIT
