# mattermost-plugin-development

A Claude Code plugin for developing Mattermost plugins.

## Installation

Add the marketplace and install the plugin:

```
/plugin marketplace add hanzei/mattermost-plugin-development
/plugin install mattermost-plugin-development@hanzei-mattermost-plugin-development
```

Or use the interactive plugin manager:

```
/plugin
```

## Skills

### update-from-starter-template

Syncs a Mattermost plugin repository with common files from [mattermost-plugin-starter-template](https://github.com/mattermost/mattermost-plugin-starter-template) and fixes all linter issues.

**Usage:**

```
/mattermost-plugin-development:update-from-starter-template
```

This skill will:

1. Prepare the repository by creating a new branch
2. Update common build and config files from the starter template while preserving plugin-specific customizations
3. Fix linter issues using `gofumpt` and manual fixes
4. Verify tests pass and create a commit with PR
