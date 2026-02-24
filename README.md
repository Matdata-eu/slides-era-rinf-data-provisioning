# ERA RINF Data Provisioning Workshop

Slidev presentation for the ERA hands-on workshop on RINF data provisioning, aimed at Infrastructure Managers and National Registration Entities.

**Date:** 25 February 2026 · European Union Agency for Railways

## Getting Started

```bash
npm install
npm run dev
```

Open [http://localhost:3030](http://localhost:3030) to view the slides.

## Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start the dev server with live reload |
| `npm run build` | Build the slides as a static site |
| `npm run export` | Export slides to PDF |

## Artifacts

### GitHub Pages
The slides are automatically built and published to GitHub Pages on every push to `main`. The live presentation is available at:
`https://<org>.github.io/slides-era-rinf-data-provisioning/`

### PDF Release
Pushing a `v*` tag triggers the **Create PDF Release** workflow, which exports the slides to PDF and attaches it to the GitHub release as `dim-accessing-data-<version>.pdf`. Running the workflow manually (via `workflow_dispatch`) will upload the PDF as a workflow artifact instead.

## Project Structure

- `slides.md` — Main presentation content
- `assets/` — Images and other static assets
- `getting-started-rinf-data-provisioning.md` — Participant getting-started guide
