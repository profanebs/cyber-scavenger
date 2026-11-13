# cyber-scavenger

**Scavenge before you build.** A skill that forces the agent to search local and existing resources before creating anything new.

Most agents jump straight to writing code. This skill puts a gate in front of that: the local library first, then external ready-made parts, then adaptation, and only then a self-built version — with an explicit reason and user approval.

## What it does

- Runs a three-question decision gate before any search: does an installed skill already cover it, is the generic capability good enough, does the user actually need a reusable capability?
- Searches in this order: local skills and scripts, then GitHub / npm / PyPI / awesome lists / HuggingFace, then official docs and mature implementations.
- Compares the top two or three candidates on fit, maintenance, license, dependency weight, and adaptation cost.
- Picks one path: reuse, adapt, combine, or build. Building requires a written reason.
- Routes external code through a security scan before execution.

## When to use

- Before creating a tool, script, skill, plugin, service, integration, automation, asset, template, or workflow.
- When the user says "build me X", "add a feature", "make a script".
- Not for pure content creation (writing, fiction, copywriting).

## Install

Copy the `cyber-scavenger/` directory into your agent's skills directory:

```powershell
# Windows
Copy-Item -Recurse cyber-scavenger "$env:USERPROFILE\.config\opencode\skills\"

# macOS / Linux
cp -r cyber-scavenger ~/.config/opencode/skills/
```

The skill is a single `SKILL.md`.

## The decision gate

Before searching, answer three questions. Any "no" means skip the search and do the work directly:

1. Does an installed skill really not cover this?
2. Is the generic capability really that far off?
3. Does the user really need a reusable, dedicated capability?

## Design notes

- Search is a fallback, not a ritual first step. The gate prevents "search theater" on one-line tasks.
- The output is a decision record, not a research essay: what was searched, what was found, why it was rejected, and what path was chosen.
- "Not found" must state the search scope. "I think there is nothing" does not count.
- External code goes through a security scan before it runs.

## Credits

Adapted from [dont-reinvent-the-wheel-skill](https://github.com/ShanedevPro/dont-reinvent-the-wheel-skill) by ShanedevPro (MIT). This version is localized to Chinese and extended to cover all resource types (software, plugins, skills, assets, and workflows). See `NOTICE.md`.

## License

MIT. See `LICENSE`.
