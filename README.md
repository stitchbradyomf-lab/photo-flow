# Photo Flow

Human-AI interface for photo curation and enrichment.

## Purpose

Bridge between Ansel's automated detection and human judgment. Review, classify, describe, and connect photos to trips and events.

## Workflow

1. **Ansel scans** bradyvisuals.com (Fridays 7pm ET)
2. **Ansel updates** `data/queue.json` with new items
3. **Git commit** → auto-deploy to Netlify
4. **You visit** photo-flow.netlify.app
5. **You edit** JSON files to remediate missing data
6. **Git commit** → updates propagate

## Data Files

| File | Purpose |
|------|---------|
| `data/queue.json` | Your TODO items — albums needing classification |
| `data/albums.json` | All albums with enrichment status |
| `data/recent.json` | Recently detected additions |
| `data/projects.json` | Active and completed book projects |

## Status Values

- `auto-classified` — Ansel guessed attributes
- `needs-review` — Missing critical fields
- `enriched` — Human verified and added context
- `book-queued` — Marked for photo book
- `completed` — Book created or archived

## Editing

Currently: Edit JSON files directly
Future: In-browser editing UI

## Deployment

```bash
git add .
git commit -m "Update photo classifications"
git push origin main
```

Netlify auto-deploys from GitHub.

---

*Scaffolded: July 2, 2026*
