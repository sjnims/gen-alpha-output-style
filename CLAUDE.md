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

## Architecture

**Two-tier structure:**

1. **Marketplace level** (`.claude-plugin/marketplace.json`) - Registers the repo as a marketplace that can contain multiple plugins
2. **Plugin level** (`plugins/gen-alpha-output-style/.claude-plugin/plugin.json`) - Individual plugin manifest

**Plugin mechanism:** The SessionStart hook runs `load-style.sh` which:

1. Reads user settings from `.claude/gen-alpha-output-style.local.md` (if exists)
2. Checks `enabled` flag (exits silently if `false`)
3. Outputs intensity-appropriate prompt instructions to Claude's context

## Development Commands

```bash
# Lint markdown files
markdownlint "**/*.md"

# Test plugin locally (loads from local directory)
claude --plugin-dir ./plugins/gen-alpha-output-style

# Test the hook script directly (outputs prompt text)
bash ./plugins/gen-alpha-output-style/hooks/load-style.sh

# Test with specific intensity (create temp settings first)
mkdir -p .claude && echo -e "---\nenabled: true\nintensity: light\n---" > .claude/gen-alpha-output-style.local.md
bash ./plugins/gen-alpha-output-style/hooks/load-style.sh
rm .claude/gen-alpha-output-style.local.md
```

## Key Configuration

- **Markdownlint**: MD013 (line length) and MD060 (table style) disabled in `.markdownlint.json`
- **User settings**: `.claude/gen-alpha-output-style.local.md` with YAML frontmatter (`enabled`, `intensity`)
- **Intensity levels**: `light`, `moderate`, `full` (default)
- **Hook paths**: Use `${CLAUDE_PLUGIN_ROOT}` for portable paths in hooks.json
