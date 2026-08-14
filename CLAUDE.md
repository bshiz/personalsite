# CLAUDE.md

Context for Claude Code when working in this repo.

## Project

Brandon Houlihan's personal portfolio site, live at brandonhoulihan.com. Deployed via GitHub Pages (repo: `personalsite`) with a custom domain configured through GoDaddy DNS — DNS routing is handled by the `CNAME` file at the repo root, not by any app code.

## Repo structure

Flat, no build step, no framework:

- `index.html` — the entire live site: markup, CSS (in a single `<style>` block), all in one file
- `favicon.png`, `headshot.jpeg`, `headshot_grey.png` — image assets at repo root, referenced by relative path
- `CNAME` — GitHub Pages custom domain config, do not touch unless DNS is the explicit topic
- `.gitignore`

New pages (e.g. case studies) follow the same pattern: a self-contained HTML file at the repo root (e.g. `case-study-tempo.html`), not a subfolder, unless Brandon says otherwise.

## Design system (current, as of index.html)

- **Fonts:** Cormorant Garamond (serif, body/headings) + DM Mono (labels, eyebrows, mono accents), both via Google Fonts
- **Palette (CSS custom properties):**
  - `--navy: #0b1828`, `--navy-mid: #0f2035`, `--navy-light: #162840`
  - `--slate: #7a9ab5`, `--slate-light: #a8c4d8`
  - `--cream: #e8e0d0`, `--white: #f0ece4`
  - `--gold: #c9a96e`, `--gold-dim: #8a6c3e`
- **Layout conventions:** fluid type via `clamp()`, generous section padding (`4rem`–`8rem`), a `.section-label` pattern (mono, uppercase, letter-spaced, with a hairline rule) used to open each section, sticky sidebar on the About section
- **Interaction:** subtle hover states (color shift, slight padding-left nudge on links), no heavy animation

Before starting any new visual direction, confirm with Brandon which file is the current live version — this site has gone through several full redesigns, and old directions sometimes persist as separate files.

## Working style — read before writing any code

- **Content before code.** Don't touch HTML/CSS for a new section or page until Brandon has approved the copy in conversation. Draft and iterate on text first, as plain text or in chat.
- **Structural CSS before visual polish.** When adding a section or page, establish shared variables and layout classes first; don't layer visual tweaks on ad hoc markup.
- **Incremental changes, frequent previews.** Prefer small diffs Brandon can react to over large rewrites. Don't restructure things he didn't ask you to touch.
- **Confirm scope before major structural changes.** Discuss the plan conversationally first.

## Copy voice

- No em dashes, ever.
- Plain, grounded, personal, empathetic. Not corporate, not abstract.
- Avoid generic leadership language — words like "ambiguity," "passion," and similar clichés are unwelcome.
- If UFO/UAP topics come up, treat the subject seriously and respectfully, not as a punchline.

## Git workflow

Standard flow, already authenticated via `gh auth login`:

```
git add .
git commit -m "..."
git push
```

No CI/build step — pushing to `main` is what ships to GitHub Pages.
