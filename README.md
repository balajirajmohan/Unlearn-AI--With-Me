# Unlearn AI — With Me

An open educational site for learning AI engineering by building, breaking, and explaining real systems.

The public site follows one path:

> Unlearn → Understand → Build → Break → Operate

It covers the full stack from AI foundations and Python application development through RAG, agents, MCP, model adaptation, GPU inference, LLMOps, cloud deployment, and AI platforms.

## What lives here

- `docs/` — public lessons, labs, diagrams, and learning routes
- `roadmap.yml` — the 48-week source roadmap distilled from the private learning workbook
- `.github/workflows/publish-site.yml` — GitHub Pages publishing workflow
- `AI_Engineering_Learning_Tracker (2).xlsx` — private planning reference; it is not part of the public teaching experience

The site does not pretend that course completion equals mastery. Each major topic should leave behind an explanation, a working build, a failure mode, and an operating note.

## Run locally

Install the site dependencies and serve the docs:

```bash
python -m pip install mkdocs-material
mkdocs serve
```

Then open the local URL printed by MkDocs.

## Publish

Enable GitHub Pages with **GitHub Actions** as the source. Pushing to `main` runs the workflow, builds the Material site, and deploys the generated `site/` artifact.

## Privacy boundary

Keep customer data, cloud identifiers, API keys, `.env` files, private costs, and personal notes out of this repository. Use synthetic examples in lessons and labs.
