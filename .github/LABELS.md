# GitHub Labels

This document describes the labels used in this repository. Labels are automatically synced from `.github/labels.json` via the [Sync Labels workflow](.github/workflows/sync-labels.yml).

## Label Categories

### Type Labels

These describe the nature of the issue or PR.

| Label | Description | When to Use |
|-------|-------------|-------------|
| `bug` | Something isn't working | Broken functionality, errors, unexpected behavior |
| `enhancement` | New feature or request | New features, improvements to existing functionality |
| `documentation` | Improvements or additions to documentation | README, CLAUDE.md, inline comments |
| `question` | Further information is requested | Asking for help or clarification |
| `refactor` | Code refactoring | Restructuring without behavior change |
| `chore` | Maintenance and housekeeping | Dependencies, CI config, tooling |

### Area Labels

These identify which part of the plugin is affected.

| Label | Description | When to Use |
|-------|-------------|-------------|
| `area: glossary` | Related to slang terms and glossary | Changes to glossary.md, new terms, corrections |
| `area: hook` | Related to hook scripts | SessionStart hook, shell scripts |
| `area: skill` | Related to skills and transformation rules | SKILL.md, intensity levels, examples |

### Priority Labels

These indicate urgency and importance.

| Label | Description | When to Use |
|-------|-------------|-------------|
| `priority: high` | High priority | Blocking, security, major functionality |
| `priority: medium` | Medium priority | Moderate impact, normal priority |
| `priority: low` | Low priority | Minor issues, nice to have |

### Status Labels

These track the current state of an issue or PR.

| Label | Description | When to Use |
|-------|-------------|-------------|
| `blocked` | Blocked by another issue or external factor | Waiting on external dependency |
| `needs-review` | Awaiting review | PR ready for review |
| `stale` | Automatically marked as stale | Auto-applied by stale bot after 60 days |

### Special Labels

These mark special characteristics.

| Label | Description | When to Use |
|-------|-------------|-------------|
| `new-slang` | Suggestion for new slang term | Issue proposing new Gen Alpha slang |
| `good first issue` | Good for newcomers | Simple, well-documented tasks |
| `help wanted` | Extra attention is needed | Could use community contribution |
| `pinned` | Pinned issue - exempt from stale bot | Important issues that shouldn't auto-close |
| `roadmap` | Part of the project roadmap | Planned features and milestones |
| `security` | Security-related issue | Vulnerabilities, security improvements |

### Resolution Labels

These indicate how an issue was resolved.

| Label | Description | When to Use |
|-------|-------------|-------------|
| `duplicate` | This issue already exists | Close with link to original |
| `invalid` | This doesn't seem right | Not a valid issue for this repo |
| `wontfix` | This will not be worked on | Out of scope or not planned |

## Adding New Labels

1. Edit `.github/labels.json` to add your new label
2. Create a PR with the change
3. Once merged, the Sync Labels workflow will automatically create the label

## Label Colors

- **Red tones** (`d73a4a`, `b60205`, `d93f0b`): Bugs, high priority, security
- **Blue tones** (`1d76db`, `0075ca`): Area labels, documentation
- **Green tones** (`0e8a16`, `006b75`, `008672`): Low priority, pinned, help wanted
- **Yellow tones** (`fbca04`, `fef2c0`, `e4e669`): Medium priority, chore, invalid
- **Purple tones** (`5319e7`, `7057ff`, `d876e3`): New slang, good first issue, question
- **Cyan/teal** (`a2eeef`, `c5def5`): Enhancement, refactor
- **Gray tones** (`cfd3d7`, `ededed`, `ffffff`): Duplicate, stale, wontfix
