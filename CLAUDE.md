# Maintainer Instructions

Governs authoring conventions for this repo only. Doesn't load into projects
that install the `hemingway-style` plugin — Claude Code loads a plugin's
skills/agents/hooks/commands into consuming projects, not its CLAUDE.md.
Applies only when this repo itself is the working directory.

## Compression

`skills/hemingway-style/SKILL.md` is Claude-auto-loaded into every project
that installs this plugin, so its token cost is worth cutting. After any
edit, run `/caveman-compress skills/hemingway-style/SKILL.md`.

That command comes from a separate plugin, not Claude Code core:
[JuliusBrussee/caveman](https://github.com/JuliusBrussee/caveman). Install it
with `/plugin marketplace add JuliusBrussee/caveman` then
`/plugin install caveman@caveman` before running the command above.

Exception: `README.md`. Human-only read, never auto-loaded — full sentences,
not caveman fragments.

This file (`CLAUDE.md`) is exempt from the compression rule — it only loads
when this small repo itself is the working directory, so the token cost is
already low. Not worth requiring the caveman plugin just for that.

## Dogfooding

`README.md`, and any other prose file meant for a human reader, runs
through `hemingway-style` itself before commit — both passes, in order.
