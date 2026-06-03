# happybday

URL-param driven birthday card generator — nerdy, minimal, printable.
Pure HTML/JS, no build step. Hosted on GitHub Pages.

## Identity

This repo follows the Claude push convention. Commits authored as
`Claude (happybday) <claude@local>`, pushed to Forgejo via HTTPS-with-token.
See `~/ops/runbooks/identity-setup.md`.

## Conventions

- Cross-repo notes, runbooks, audits: `~/ops/`
- Per-repo intent (current focus, blockers, next): `~/ops/projects/happybday.md`

## Pages

| Page | Role |
|------|------|
| `start.html` | Entry: token input or redirect to builder |
| `builder.html` | Visual editor — live preview, generates token + share link |
| `index.html` | The card itself — all content from URL params |
| `plain.html` | Plain-text / print version |

## Local Dev

```bash
python3 -m http.server 8080
# → http://localhost:8080/builder.html
```

No build step, no npm. Edit HTML/JS/CSS directly.

## Key files

| File | Role |
|------|------|
| `config.js` | Card configuration (themes, fields) |
| `messages.json` | Configurable messages/texts |
| `devices/` | Device-specific rendering adjustments |

## Hosting

GitHub Pages from `main` branch root.
Versioning via `release-please-config.json` (conventional commits → automated release).

## Do not

- Add a backend or server-side component — everything is intentionally client-side
- Add npm or a build pipeline
