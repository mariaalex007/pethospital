# Vetri Pet Clinic — Website

WordPress website for **Vetri Pet Clinic**: 13–15 pages, premium theme with a custom child theme, WhatsApp appointment flow, UPI payments, Google Business Profile integration and local SEO.

- Project scope and quotation: [`docs/project-brief.md`](docs/project-brief.md)
- Instructions for Claude (and for humans): [`CLAUDE.md`](CLAUDE.md)

## Quick start (local)

Requires Docker and Node.js 18+.

```bash
npx @wordpress/env start     # WordPress at http://localhost:8888 (admin / password)
npx @wordpress/env stop
```

## Claude setup in this repo

| Path | Purpose |
|---|---|
| `CLAUDE.md` | Project context loaded at the start of every Claude session |
| `.claude/rules/` | Focused rules: design system, WordPress code, integrations, SEO, content |
| `.claude/skills/` | Reusable workflows: `/new-service-page`, `/appointment-flow`, `/seo-check`, `/launch-checklist` |
| `.claude/agents/` | Specialist subagents: developer, designer, content writer, SEO, QA |
| `.claude/settings.json` | Shared permissions for Claude Code |
