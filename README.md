# novice-log — Claude Code skill

Update `~/.claude/NOVICE.md` with session learnings — CLI commands, gotchas, fixes, and ports — written for novice developers.

## What it does

- Scans the current session for CLI commands, errors, and discoveries
- Writes each finding in plain English with context ("why you'd run this")
- Appends a dated `### Session: YYYY-MM-DD (project)` block to a single shared log
- Never duplicates entries; never touches content from earlier sessions

## Install

```bash
mkdir -p ~/.claude/skills/novice-log
cp SKILL.md ~/.claude/skills/novice-log/
```

## Usage

```
/novice-log
```

Run at the end of any session to capture learnings before closing.

## Files

| File | Purpose |
|---|---|
| `SKILL.md` | Skill instructions loaded by Claude Code |
