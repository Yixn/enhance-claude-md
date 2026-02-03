---
name: enhance-claude-md
description: Analyze, generate, or enhance CLAUDE.md files for any project
argument-hint: [analyze|create|enhance]
---

# Enhance CLAUDE.md

Invoke the `linkster-general:claude-md-enhancer` skill to analyze, generate, or enhance CLAUDE.md files.

## What This Command Does

1. **Loads the claude-md-enhancer skill** with full context
2. **Executes the requested operation** based on arguments or interactive prompts
3. **Returns customized CLAUDE.md content** tailored to your project

## Usage

```bash
# Interactive mode - skill guides you through the process
/enhance-claude-md

# Analyze existing CLAUDE.md
/enhance-claude-md analyze

# Create new CLAUDE.md for current project
/enhance-claude-md create

# Enhance existing CLAUDE.md with missing sections
/enhance-claude-md enhance
```

## Implementation Steps

When this command is invoked:

### 1. Load the Skill

Use the Skill tool to invoke `linkster-general:claude-md-enhancer`:

```
Skill(linkster-general:claude-md-enhancer)
```

### 2. Determine Operation Mode

Parse the argument (if provided):

- `analyze` - Analyze existing CLAUDE.md and report issues
- `create` - Create new CLAUDE.md for the project
- `enhance` - Improve existing CLAUDE.md with missing sections
- No argument - Enter interactive mode, let skill guide the user

### 3. Execute the Skill

Follow the skill's instructions to:

- Explore the repository structure
- Detect project type and tech stack
- Generate or enhance CLAUDE.md content
- Validate output against best practices

## Important Notes

- **This is a wrapper command** - All logic lives in the skill
- **Interactive workflow** - The skill will ask for confirmation before making changes
- **Supports modular architecture** - Can create context-specific files (backend/CLAUDE.md, frontend/CLAUDE.md)

## Error Handling

If the skill fails to load:
- Report the error to the user
- Suggest running `/plugin update linkster-general@linkster-local`
