# Evaris agent skills

Agent Skills ([agentskills.io](https://agentskills.io) open standard) that
teach coding agents to work with Evaris: setting up
[Inspect AI](https://inspect.aisi.org.uk) evals, wiring them into CI, and
publishing/querying results.

| Skill | Purpose |
| --- | --- |
| `evaris-evals` | Scaffold inspect-ai evals in any repo, run them, wire CI, publish to Evaris, query results with least-privilege tokens. |

## Install (one command, any agent)

```bash
npx skills add evarisai/skills
```

The `skills` CLI ([skills.sh](https://skills.sh)) auto-detects installed agents
and installs into the right place for each — `.claude/skills/` (Claude Code),
`.agents/skills/` (Codex), `.cursor/skills/` (Cursor), and many others. Use
`npx skills add https://github.com/evarisai/skills/tree/main/skills/evaris-evals`
to install just this skill, or `--copy` instead of symlinked installs.

To test changes before merging to `main`, point the tree URL at the branch:

```bash
npx skills add https://github.com/evarisai/skills/tree/<branch>/skills/evaris-evals
```

## Editing rules

Keep `SKILL.md` under 500 lines with detail in `references/`; the frontmatter
`name` must match the directory name; bump `metadata.version` when user-visible
behavior changes. Validate after edits:
`npx skills-ref validate skills/evaris-evals` (or
`npx skills add . --copy` locally to smoke-test).
