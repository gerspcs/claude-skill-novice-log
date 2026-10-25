---
name: novice-log
description: Update ~/.claude/novice-<topic>.md with session learnings — CLI commands, gotchas, fixes, ports. Written for novice developers.
---

Review the current conversation and update (or create) the right
`~/.claude/novice-<topic>.md` topic file — **not** `~/.claude/NOVICE.md`
itself, which is only an index (see below). Split from one file into topic
files on 2026-08-17 because a single 2,719-line file was impractical to
grep-and-find in, even with a read-first trigger.

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

**Step 1 — pick the topic file.** Current topic files, all in
`/home/ger/.claude/`:

| File | Covers |
|---|---|
| `novice-kubernetes.md` | Kubernetes / kind / Gatekeeper / Tekton / ArgoCD / Trivy / Linkerd / Velero |
| `novice-docker.md` | Docker outside a Kubernetes context — Compose, contexts, snap Docker, container networking |
| `novice-lightrag-rag.md` | LightRAG / RAG pipeline |
| `novice-editorial-writing.md` | Editorial & document workflow — book-drive, 2ndbook-drive, Beeches, PDF/docx conversion |
| `novice-git-gitea.md` | Git / Gitea — self-hosted git.local, push setup, repo publishing |
| `novice-agentic-cicd.md` | Agentic CI/CD — gated pipelines, signed approvals, audit chains, MCP gateways, mutation-checking tests |

If the session's content genuinely spans two topics, put the whole session
in whichever topic dominates the narrative (don't split one session's story
across files) — this matches how the existing mixed-topic sessions were
handled at split time (see `NOVICE.md`'s "Mixed-topic sessions" section for
examples).

If nothing fits, ask the user before creating a new `novice-<topic>.md` —
don't create one unilaterally, and don't fall back to writing into
`NOVICE.md` itself.

**Step 2 — write the entry.** Never write to the project root. Create the
topic file if absent:
```
# NOVICE.md — <Topic Title>

Topic file split out of `~/.claude/NOVICE.md` on 2026-08-17. Same rules
apply: written for a developer new to the project/terminal, real commands +
gotchas, never rewritten — only appended.

---

## Session CLI Log

### Session: YYYY-MM-DD (project-name)

[entries here]
```

If the topic file exists:
- Add `## Session CLI Log` section at the bottom if missing
- Add `### Session: YYYY-MM-DD (project-name)` using today's date and current project name
- Never duplicate entries from prior sessions
- Never modify content above the Session CLI Log section

**Step 3 — update the index.** Add one row to the **Session index** table
in `~/.claude/NOVICE.md` (date, topic file, one-line session title) so the
index stays a complete map without anyone needing to open every topic file.

## Skip

- Commands with no learning value
- Implementation details (belongs in CLAUDE.md/AGENTS.md)
- Sensitive values — describe the pattern, not the value

## After updating

Report what was added and how many new entries were written.
