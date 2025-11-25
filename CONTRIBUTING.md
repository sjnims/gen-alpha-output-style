# Contributing

Thanks for your interest in contributing to the Gen Alpha Output Style plugin!

## Getting Started

1. Fork the repository
2. Clone your fork locally
3. Create a branch for your changes

## Development Setup

```bash
# Install markdownlint for linting
npm install -g markdownlint-cli

# Test the plugin locally
claude --plugin-dir ./plugins/gen-alpha-output-style

# Run linting
markdownlint "**/*.md"
```

## Making Changes

### Plugin Structure

- `plugins/gen-alpha-output-style/hooks/` - Hook scripts and configuration
- `plugins/gen-alpha-output-style/skills/` - Skills with transformation rules
- `plugins/gen-alpha-output-style/skills/gen-alpha-style/references/` - Glossary and examples

### Adding New Slang Terms

1. Add terms to `plugins/gen-alpha-output-style/skills/gen-alpha-style/references/glossary.md`
2. Add usage examples to `plugins/gen-alpha-output-style/skills/gen-alpha-style/references/examples.md`
3. Update `SKILL.md` if adding new transformation patterns

### Modifying Hook Behavior

The `hooks/load-style.sh` script controls how the plugin loads. Changes here affect all intensity levels.

## Pull Request Process

1. Ensure markdown linting passes: `markdownlint "**/*.md"`
2. Test your changes locally with `claude --plugin-dir ./plugins/gen-alpha-output-style`
3. Write a clear PR description explaining your changes
4. Link any related issues

## Code Style

- Follow existing markdown formatting conventions
- Use descriptive commit messages
- Keep hook scripts POSIX-compatible where possible

## Reporting Issues

- Check existing issues before creating a new one
- Include steps to reproduce for bugs
- For new slang suggestions, explain the term's meaning and usage

## Questions?

Open an issue for any questions about contributing.
