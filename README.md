# Research Companion

A Claude Code skill that acts as a persistent research thinking partner for academic/scientific projects.

## Features

- Named companion with custom personality
- Layered memory system (L1 core / L2 sessions / L3 archive)
- Cross-session continuity
- Context window monitoring hook
- Bilingual (Chinese/English)

## Installation

```bash
# From your project root
git clone git@github.com:rainshed/research-companion.git /tmp/rc-install
mkdir -p .claude/skills
cp /tmp/rc-install/.claude/skills/* .claude/skills/
cp /tmp/rc-install/.claude/context-monitor.sh .claude/
cp /tmp/rc-install/.claude/settings.local.json .claude/
chmod +x .claude/context-monitor.sh
rm -rf /tmp/rc-install
```

The context monitor uses [cozempic](https://github.com/eastlondoner/cozempic). Install with `npm install -g cozempic` (optional).

## Usage

Say `科研伙伴`, `research companion`, or `研究搭档` in Claude Code to activate.

## License

MIT