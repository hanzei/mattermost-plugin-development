# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Claude Code plugin** (not a traditional application) that provides skills for developing Mattermost plugins. The plugin is distributed via the Claude Code plugin marketplace under `hanzei/mattermost-plugin-development`.

## Repository Structure

- `plugin/.claude-plugin/plugin.json` — Plugin manifest
- `plugin/skills/update-from-starter-template/SKILL.md` — Skill definition (the core logic)
- `.claude-plugin/marketplace.json` — Marketplace registry metadata (version, keywords, etc.)

## How It Works

Skills are defined as Markdown files with YAML frontmatter. The frontmatter declares the skill name, description, whether it's user-invocable, and which tools it's allowed to use. The Markdown body contains instructions that Claude follows when the skill is invoked.

The main skill (`update-from-starter-template`) syncs Mattermost plugin repos with the official [mattermost-plugin-starter-template](https://github.com/mattermost/mattermost-plugin-starter-template) and fixes linter issues. It uses `mcp__github-server__get_file_contents` to fetch files from the template repo.

## Development Workflow

When modifying skills, edit the SKILL.md file directly. Changes take effect immediately when the plugin is loaded.

When releasing a new version, update the `version` field in both:
- `.claude-plugin/marketplace.json` (in the `metadata` and `plugins[0]` sections)
