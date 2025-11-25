# Gen Alpha Output Style Plugin

No cap, this plugin transforms Claude's responses to use Gen Alpha/brainrot internet slang. It's giving main character energy fr fr.

## Features

- **Configurable intensity**: Choose from light, moderate, or full brainrot
- **Technical accuracy preserved**: Code blocks and technical content stay clean
- **Comprehensive glossary**: 50+ terms with proper usage
- **Automatic activation**: Style applies to all responses via SessionStart hook

## Installation

1. Copy this plugin to your Claude Code plugins directory
2. Enable the plugin in Claude Code settings
3. Start a new session - the style activates automatically

## Configuration

Create `.claude/gen-alpha-output-style.local.md` in your project to customize:

```markdown
---
enabled: true
intensity: full
---
```

### Settings

| Setting | Values | Default | Description |
|---------|--------|---------|-------------|
| `enabled` | `true`, `false` | `true` | Enable/disable the style |
| `intensity` | `light`, `moderate`, `full` | `full` | How much slang to use |

### Intensity Levels

**Light** - Subtle seasoning

- 1-2 slang terms per response
- Mostly standard language
- Professional-ish tone

**Moderate** - Balanced mix

- 2-4 slang terms per paragraph
- Mix of slang and standard language
- Noticeable but readable

**Full** (default) - Maximum brainrot

- Heavy slang throughout
- Dramatic reactions
- Full Gen Alpha energy

### Changing Settings

After editing `.claude/gen-alpha-output-style.local.md`:

1. Save the file
2. Exit Claude Code
3. Restart Claude Code
4. New settings take effect

**Note:** Add `.claude/*.local.md` to your `.gitignore`.

## What Gets Transformed

- Explanations and conversational text
- Comments and descriptions
- Error messages and suggestions

## What Stays Clean

- Code blocks and syntax
- File paths and technical references
- Command examples

## Example

**Before**: "I'll help you fix this bug. The issue is in line 42 where the variable is undefined."

**After (full intensity)**: "Yo I got you fam, let me cook real quick. The issue is lowkey in line 42 where the variable said 'aight imma head out' and went undefined. No cap this is an easy fix fr fr."

**After (light intensity)**: "I'll help you fix this bug. The issue is in line 42 where the variable is undefined, lowkey an easy fix."

## Glossary Highlights

| Term | Meaning |
|------|---------|
| no cap | For real, not lying |
| fr fr | For real for real (emphasis) |
| bussin | Really good |
| hits different | Exceptionally good |
| lowkey | Subtly, kind of |
| highkey | Obviously, very much |
| sigma | Independent, self-reliant |
| rizz | Charisma |
| skibidi | Chaotic energy |
| gyatt | Exclamation of surprise |

See the full glossary in `skills/gen-alpha-style/references/glossary.md`

## License

[MIT](LICENSE.txt)
