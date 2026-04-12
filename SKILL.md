---
name: novice-log
description: Update ~/.claude/NOVICE.md with session learnings — CLI commands, gotchas, fixes, ports. Written for novice developers.
---

Review the current conversation and update (or create) `~/.claude/NOVICE.md`.

## Capture from this session

- CLI commands run (bash, curl, docker, git, lsof, etc.)
- Gotchas — broken, surprising, or non-obvious behaviour
- Fixes — patterns a beginner wouldn't know
- Credentials, ports, service URLs
- Error messages and resolutions

## Entry format

Write for a **novice developer** new to the project and terminal.

**Commands:** code block + plain-English explanation of each part + why you'd use it.

**Gotchas:** symptom → cause → fix.

## File structure

Always write to `/home/ger/.claude/NOVICE.md`. Never write to the project root.

Create if absent:
```
# NOVICE.md — Developer Learning Log

This document captures real commands and discoveries from development sessions.

---

## Session CLI Log

### Session: YYYY-MM-DD (project-name)

[entries here]
```

If the file exists:
- Add `## Session CLI Log` section at the bottom if missing
- Add `### Session: YYYY-MM-DD (project-name)` using today's date and current project name
- Never duplicate entries from prior sessions
- Never modify content above the Session CLI Log section

## Skip

- Commands with no learning value
- Implementation details (belongs in CLAUDE.md/AGENTS.md)
- Sensitive values — describe the pattern, not the value

## After updating

Report what was added and how many new entries were written.
