# Claude Interaction Log — UNOARC Slides

---

## 2026-03-12

### Build MARP presentation from Google Doc
- **User:** Requested a MARP presentation based on a Google Docs link.
- **Claude:** Attempted to fetch the doc; initial requests returned 401. On retry, used export URL which redirected successfully and retrieved document content about UNO Amateur Radio Club.
- **Output:** Created `presentation.md` with 9 slides covering club overview, membership, goals, fundraising request, and project wish list.

### Serve presentation on port 8080
- **User:** Asked to run the marp command to serve on port 8080.
- **Claude:** `marp` not found in PATH. Used `npx @marp-team/marp-cli` instead. First attempt failed (file path given instead of directory). Fixed by passing the directory path.
- **Output:** Server running at http://localhost:8080/ via `npx @marp-team/marp-cli --server --port 8080 /home/mpayne/UNOARC-slides`

### GitHub Actions auto-build
- **User:** Requested automatic rebuild of `index.html` and `slides.pdf` on push to GitHub when any `.md` file changes.
- **Claude:** Created `.github/workflows/build.yml` using `marp-team/marp-action@v2`. On push to `main` affecting any `.md` file, it builds `index.html` and `presentation.pdf`, then commits and pushes them back to the repo.

### Interaction logging
- **User:** Asked to track all Claude interactions in a markdown file.
- **Claude:** Created this file (`interaction-log.md`) and updated `MEMORY.md` to persist the preference across sessions.
