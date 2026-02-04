# CLAUDE.md

This file provides guidance for Claude Code when working with this project.

## Overview

Claude Code Plugin Marketplace containing the `enhance-claude-md` plugin. This plugin provides tools to analyze, generate, and enhance CLAUDE.md files for any project type.

## Project Structure

```
enhance-claude-md/
├── .claude-plugin/
│   └── marketplace.json          # Marketplace config (2 version locations!)
├── plugins/
│   └── enhance-claude-md/
│       ├── .claude-plugin/
│       │   └── plugin.json       # Plugin config (1 version location!)
│       ├── commands/
│       │   └── enhance-claude-md.md
│       └── skills/
│           └── claude-md-enhancer/
│               ├── SKILL.md      # Main skill definition
│               ├── analyzer.py   # Analysis logic
│               ├── generator.py  # Content generation
│               ├── template_selector.py
│               ├── workflow.py
│               ├── validator.py
│               └── examples/     # Reference CLAUDE.md examples
├── README.md
└── CLAUDE.md                     # This file
```

## File Structure

- **.claude-plugin/** - Marketplace configuration
  - **marketplace.json** - Defines marketplace metadata and plugin registry
- **plugins/** - Contains all plugins in this marketplace
  - **enhance-claude-md/** - The main plugin
    - **commands/** - Slash commands (/enhance-claude-md)
    - **skills/** - Skill definitions with Python modules

---

## MANDATORY: Version Bumping Before Commits

**YOU MUST BUMP VERSIONS BEFORE EVERY COMMIT THAT CHANGES FUNCTIONALITY.**

### Version Locations (ALL 3 MUST BE UPDATED)

| File | JSON Path | Current |
|------|-----------|---------|
| `.claude-plugin/marketplace.json` | `metadata.version` | Check file |
| `.claude-plugin/marketplace.json` | `plugins[0].version` | Check file |
| `plugins/enhance-claude-md/.claude-plugin/plugin.json` | `version` | Check file |

### Semantic Versioning Rules (MAJOR.MINOR.PATCH)

Based on [SemVer 2.0.0](https://semver.org/):

#### PATCH (x.y.Z) - Bug Fixes
Increment when you make **backward-compatible bug fixes**.

**Bump PATCH for:**
- Fixing typos in documentation or code
- Bug fixes that don't change behavior
- Internal refactoring with no API changes
- Performance improvements with no interface changes
- Fixing broken examples

**Example:** `1.0.0` → `1.0.1`

#### MINOR (x.Y.z) - New Features
Increment when you add **backward-compatible functionality**.

**Bump MINOR for:**
- Adding new features that don't break existing ones
- Adding new commands or skills
- Adding new template types or examples
- Deprecating existing functionality (but not removing it)
- Adding new optional parameters

**Example:** `1.0.1` → `1.1.0` (resets PATCH to 0)

#### MAJOR (X.y.z) - Breaking Changes
Increment when you make **incompatible API changes**.

**Bump MAJOR for:**
- Removing features, commands, or skills
- Changing command syntax or behavior
- Renaming or restructuring plugin files
- Changing required parameters
- Any change that breaks existing usage

**Example:** `1.1.0` → `2.0.0` (resets MINOR and PATCH to 0)

### Quick Decision Tree

```
Is this a breaking change?
├── YES → Bump MAJOR (reset minor.patch to 0)
└── NO → Does it add new features?
    ├── YES → Bump MINOR (reset patch to 0)
    └── NO → Bump PATCH
```

### Version Bump Checklist

Before committing, verify:

- [ ] All 3 version locations are updated
- [ ] Version numbers match across all files
- [ ] Correct version component was bumped (major/minor/patch)
- [ ] Lower version components reset appropriately

### Example Workflow

```bash
# 1. Check current versions
grep -r '"version"' .claude-plugin/ plugins/*/.claude-plugin/

# 2. Make your changes...

# 3. Bump all 3 locations (e.g., 1.0.1 → 1.0.2 for a bug fix)
# Edit: .claude-plugin/marketplace.json (2 places)
# Edit: plugins/enhance-claude-md/.claude-plugin/plugin.json (1 place)

# 4. Verify versions match
grep -r '"version"' .claude-plugin/ plugins/*/.claude-plugin/

# 5. Commit with version in message
git add -A && git commit -m "fix: Description here (v1.0.2)"
```

---

## Development Guidelines

### Adding New Features

1. Update skill files in `plugins/enhance-claude-md/skills/claude-md-enhancer/`
2. Update examples if behavior changes
3. Bump MINOR version in all 3 locations
4. Test with `/enhance-claude-md` command

### Fixing Bugs

1. Make the fix
2. Bump PATCH version in all 3 locations
3. Document fix in commit message

### Making Breaking Changes

1. Document the breaking change clearly
2. Bump MAJOR version in all 3 locations
3. Update README.md with migration guide

## Common Commands

```bash
# Check all version numbers
grep -r '"version"' .claude-plugin/ plugins/*/.claude-plugin/

# Test the plugin locally
/enhance-claude-md analyze
/enhance-claude-md create
/enhance-claude-md enhance

# View marketplace config
cat .claude-plugin/marketplace.json

# View plugin config
cat plugins/enhance-claude-md/.claude-plugin/plugin.json
```

## References

- [Semantic Versioning 2.0.0](https://semver.org/) - Official SemVer specification
- [SemVer Guide](https://www.baeldung.com/cs/semantic-versioning) - Comprehensive explanation
