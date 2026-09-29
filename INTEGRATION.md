# Using this stack outside Claude Code

The four skills are plain SKILL.md files - any agent that reads skills works.

## OpenClaw
Symlink each skill into the workspace skills dir:
for s in audit diagnose fix visibility; do ln -sfn ~/projects/seo-geo-stack/skills/$s ~/clawd/skills/seo-$s; done
Then ask for a site audit / AI visibility score. The weekly watchdog maps to an OpenClaw cron automation that re-runs visibility + audit and delivers the trend report to your chat.

## zcode
for s in audit diagnose fix visibility; do ln -sfn ~/projects/seo-geo-stack/skills/$s ~/.zcode/skills/seo-$s; done

## Claude Code (plugin mode)
This repo ships .claude-plugin/plugin.json, so it installs as a plugin: clone and add it to your plugin config, or copy skills/* into .claude/skills/.
