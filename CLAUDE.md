# mikehmusic — Project Context

## File Location
Working directory: `/Users/michaelhamilton/sites/gtnb_website_build_2026/`

All edits happen here directly. Do not look for files on the Desktop — the project was moved from `~/Desktop/GTNB_Website_Build_2026/` to this location.

## GitHub Repo
- **URL:** `github.com/espyou/mikehmusic`
- **Remote:** `git@github.com:espyou/mikehmusic.git`
- **Push method: SSH only** — do not use HTTPS or tokens. The SSH key is at `~/.ssh/id_ed25519` and is already configured. Always push via `git push` from the working directory above.

## Live Site
`https://espyou.github.io/mikehmusic`

Served by GitHub Pages from the `main` branch. Goes live ~1-2 minutes after a push.

## Preview Server
- **URL:** `http://localhost:3456`
- **Server script:** `~/mikehmusic_server.py`
- **Start via:** `preview_start` tool using the `mikehmusic` config in `~/.claude/launch.json`
- Serves from `/Users/michaelhamilton/sites/gtnb_website_build_2026/`
- **If the preview panel breaks or shows a weird viewport**, use Chrome directly at `http://localhost:3456` — it's more reliable
- **Kit email form and any other external CDN scripts will NOT render properly in the Claude preview panel** — always test those in a real browser (Chrome via the Chrome MCP tools)

## Workflow
1. Mike describes a change
2. Claude edits files in the working directory above
3. Mike reviews in the preview panel at `localhost:3456` (or Chrome for CDN-dependent features)
4. Mike says "push" — Claude commits and pushes via SSH to `main`
5. Live site updates automatically — no manual copying needed

## Key Rules
- **Never push via HTTPS or embedded tokens**
- **Always use SSH (`git@github.com:...`)**
- Mike does not need to copy files anywhere — the working directory, preview, and repo are all connected
- Do not commit `.DS_Store`, `.claude/`, or other system files
- The `images/` subfolder holds all image assets — keep it that way
- **When adding new images, always stage the image files explicitly alongside the HTML** — `git add index.html` alone will miss new image files, causing broken references on the live site
