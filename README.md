# Research Companion

A Claude Code plugin that acts as a persistent research thinking partner for academic/scientific projects.

## Features

- Named companion with custom personality
- Layered memory system (L1 core / L2 sessions / L3 archive)
- Cross-session continuity
- Context window monitoring hook
- Bilingual (Chinese/English)

## Installation

**Step 1:** Add the marketplace:

```bash
/plugin marketplace add rainshed/research-companion
```

**Step 2:** Install the plugin:

```bash
/plugin install research-companion@rainshed-research-companion
```

### Optional: Context Monitor

The context window monitor hook uses [cozempic](https://github.com/eastlondoner/cozempic) to track context usage and warn you before running out of space. Install it with:

```bash
npm install -g cozempic
```

The plugin works without cozempic — the context monitor will simply be inactive.

## Usage

Say `科研伙伴`, `research companion`, or `研究搭档` in Claude Code to activate.

On first use, the companion will ask you to give it a name. After that, you can also activate it by saying that name.

## Plugin Structure

```
research-companion/
├── .claude-plugin/
│   ├── plugin.json          # Plugin manifest
│   └── marketplace.json     # Marketplace catalog
├── skills/
│   └── research-companion/
│       ├── SKILL.md          # Main skill definition
│       └── memory-templates.md  # Memory file format templates
├── hooks/
│   └── hooks.json           # Context monitor hook config
├── scripts/
│   └── context-monitor.sh   # Context window usage monitor
└── README.md
```

## License

MIT
