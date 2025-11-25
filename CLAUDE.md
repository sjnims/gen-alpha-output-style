# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Claude Code plugin marketplace containing the `gen-alpha-output-style` plugin, which transforms Claude's responses to use Gen Alpha/brainrot internet slang while preserving technical accuracy in code blocks.

## Repository Structure

```text
.claude-plugin/marketplace.json  # Marketplace manifest (for distribution)
plugins/gen-alpha-output-style/  # The actual plugin
├── .claude-plugin/plugin.json   # Plugin manifest
├── hooks/
│   ├── hooks.json               # SessionStart hook config
│   └── load-style.sh            # Reads settings, outputs prompt
└── skills/gen-alpha-style/
    ├── SKILL.md                 # Core transformation rules
    └── references/              # Glossary and examples
```

## How the Plugin Works

1. **SessionStart hook** triggers `load-style.sh` at session start
2. **load-style.sh** reads user settings from `.claude/gen-alpha-output-style.local.md` (if exists)
3. Script outputs intensity-appropriate prompt instructions to Claude's context
4. Default intensity is "full" if no settings file exists

## Development Commands

```bash
# Lint markdown files
markdownlint "**/*.md"

# Test plugin locally
claude --plugin-dir ./plugins/gen-alpha-output-style

# Test the hook script directly
bash ./plugins/gen-alpha-output-style/hooks/load-style.sh
```

## Key Configuration

- **Markdownlint**: MD013 (line length) and MD060 (table style) are disabled in `.markdownlint.json`
- **User settings**: Read from `.claude/gen-alpha-output-style.local.md` with YAML frontmatter (`enabled`, `intensity`)
- **Intensity levels**: `light`, `moderate`, `full` (default)

## Plugin Components

- **Hooks**: Use `${CLAUDE_PLUGIN_ROOT}` for portable paths in hooks.json
- **Skills**: SKILL.md uses YAML frontmatter with `name`, `description`, `version`
- **Settings pattern**: `.local.md` files with YAML frontmatter parsed via `sed`
