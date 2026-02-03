# Enhance CLAUDE.md Marketplace

A Claude Code marketplace containing tools to analyze, generate, and enhance CLAUDE.md files for any project.

## Installation

Add this marketplace to Claude Code:

```
Yixn/enhance-claude-md
```

Or use the full URL:

```
https://github.com/Yixn/enhance-claude-md
```

## Included Plugins

### enhance-claude-md

Tools for working with CLAUDE.md project documentation files.

**Command:** `/enhance-claude-md`

**Skill:** `claude-md-enhancer`

#### Features

- **Analyze** existing CLAUDE.md files for improvements
- **Generate** new CLAUDE.md files based on project analysis
- **Enhance** existing documentation with best practices
- **Validate** CLAUDE.md structure and content

#### Usage

```
/enhance-claude-md analyze    # Analyze current project's CLAUDE.md
/enhance-claude-md generate   # Generate a new CLAUDE.md
/enhance-claude-md enhance    # Improve existing CLAUDE.md
```

## Project Structure

```
.
├── .claude-plugin/
│   └── marketplace.json        # Marketplace registry
└── plugins/
    └── enhance-claude-md/
        ├── .claude-plugin/
        │   └── plugin.json     # Plugin configuration
        ├── commands/
        │   └── enhance-claude-md.md
        └── skills/
            └── claude-md-enhancer/
                ├── SKILL.md
                ├── analyzer.py
                ├── generator.py
                ├── validator.py
                ├── workflow.py
                ├── template_selector.py
                └── examples/
                    └── (6 template examples)
```

## Example Templates

The skill includes example CLAUDE.md templates for different project types:

| Template | Use Case |
|----------|----------|
| `minimal-solo` | Solo developer, simple projects |
| `core-small-team` | Small teams, shared conventions |
| `modular-root` | Monorepo root configuration |
| `modular-backend` | Backend/API services |
| `modular-frontend` | Frontend applications |
| `python-api` | Python API projects |

## License

MIT
