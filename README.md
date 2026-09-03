# immoschott.github.io

The personal academic website of **Immo Schott** — Principal Economist, Division of
International Finance, Board of Governors of the Federal Reserve System.

Live site: **https://immoschott.github.io**

This is a plain static website (HTML + CSS, no build step and no frameworks). It is
hosted for free by **GitHub Pages**: whenever a change is pushed to this repository,
GitHub automatically publishes it to the address above.

---

## What's in this repository

```
index.html        The entire website — all text, sections, and links live here.
style.css         The look of the site (colors, fonts, spacing, dark mode).
Immo.jpg          The portrait photo shown in the header.
cv_immo.pdf       The public CV linked from the header and Contact section.
cv_immo.tex       LaTeX source for the CV — kept here so it can be edited on any computer.
.nojekyll         Tells GitHub Pages to serve the files exactly as-is.
README.md         This file.

Tax_Heterogeneity.pdf, TPS_PAPER.pdf, DebtMaturity_Immo.pdf,
DebtMaturity_BusinessCycles.pdf   Working-paper / accepted-manuscript PDFs.

Publications/                              Published-paper PDFs, appendices, replication files.
Firm Heterogeneity and Macroeconomics workshop/   Past workshop programs (PDF).
Non-academic publications/                 Policy / other writing PDFs.
```

Every file in this repository is public. That is normal and expected for an academic
site — the HTML source and all linked PDFs are meant to be readable by anyone.

---

## How to edit the site

The whole site is one file, `index.html`. You do not need to know how to code to make
routine edits.

**Option A — edit directly on GitHub (easiest):**

1. Open `index.html` in this repository on github.com.
2. Click the pencil (✏️) icon in the top-right of the file view.
3. Change the words **between** the angle-bracket tags — for example, in
   `<div class="title">Paper Title</div>`, edit only `Paper Title`. Leave the tags
   (`<div ...>` and `</div>`) alone.
4. Scroll down, click **Commit changes**. The live site updates within about a minute.

**Option B — edit on your computer, then upload:**

1. Edit `index.html` locally (Notepad++, VS Code, or any text editor).
2. Preview by double-clicking `index.html` to open it in your browser.
3. Push the change to GitHub (see "Publishing updates" below).

### Common edits

| To change…            | Search `index.html` for…          | Then edit…                          |
|-----------------------|-----------------------------------|-------------------------------------|
| A paper title         | the current title text            | text in `<div class="title">…</div>`|
| Co-authors            | the current names                 | text in `<div class="authors">…</div>` |
| Journal / status line | e.g. `Review of Economic Studies` | text in `<div class="venue">…</div>`|
| A news item           | `class="news-item"`               | the text in that line               |
| A link's destination  | the current URL                   | the text inside `href="..."`        |

### Adding a new paper

Copy an existing paper's full block (from one `<div class="pub...">` down to its matching
closing `</div>`) and paste it, then edit the copy. Adding a PDF means dropping the file
into this repo (top level or a subfolder) and pointing the link's `href` at it.

> **Filenames are case-sensitive on GitHub** (unlike Windows). If the site links to
> `Immo.jpg`, the file must be named exactly `Immo.jpg` — not `immo.jpg`. A mismatch
> makes the image or PDF fail to load. Match capitalization and spaces exactly.

---

## Publishing updates (local → GitHub)

If you edit files on your computer, publish them by pushing to GitHub:

```bash
cd path/to/immoschott.github.io   # the local folder containing these files
git add -A
git commit -m "Update site"
git push
```

GitHub Pages rebuilds automatically; the live site reflects the change within ~1 minute.
(If you edit directly on github.com via Option A, this step is done for you.)

---

## How this was set up (GitHub Pages)

For reference, the one-time steps that made this site live:

1. **Created a GitHub account** with username `immoschott`.
2. **Created a repository named `immoschott.github.io`.** The name matters: a repo named
   `<username>.github.io` is served at the clean root URL `https://<username>.github.io`.
   (Any other repo name would instead serve at `https://<username>.github.io/<repo>/`.)
3. **Set the repository to Public** — required for free GitHub Pages hosting.
4. **Added the website files** (this repository's contents), with `index.html` at the top
   level so it is served as the home page.
5. **Enabled GitHub Pages:** repository **Settings → Pages → Build and deployment →
   Source: "Deploy from a branch" → Branch: `main` / folder: `/ (root)` → Save.**
6. After about a minute, the site went live at **https://immoschott.github.io**.

### Optional: a custom domain

To serve the site from a custom address (e.g. `immoschott.com`):

1. Buy the domain (e.g. from Cloudflare or Namecheap).
2. Add a file named `CNAME` to this repository containing just the domain, e.g.
   `immoschott.com`.
3. In the domain registrar's DNS settings, point the domain at GitHub Pages
   (an `A`/`ALIAS` record to GitHub's IPs, or a `CNAME` record to `immoschott.github.io`).
4. In **Settings → Pages → Custom domain**, enter the domain and enable **Enforce HTTPS**.

---

## Keeping the site current (regular audits)

Plan to review the site periodically. Each audit should cover:

1. **News section** — remove items that have gone stale, and add anything new
   (acceptances, new working papers, upcoming talks/workshops). Keep it short and recent.
2. **Old files** — check the repo for outdated PDFs. The rule is:
   - **Published papers:** keep only the *published* PDF (plus its online appendix /
     replication files where relevant). Delete superseded working-paper drafts.
   - **Working papers:** keep only the *current* draft. When a newer version replaces it,
     delete the old one.
   - Never leave `*_old.*` or dated duplicate drafts lying around.
3. **Links** — spot-check that CV, PDF, DOI, and external links still resolve.

---

## Notes

- The site uses two web fonts (Inter and Newsreader) loaded from Google Fonts, and
  automatically supports light and dark mode based on the visitor's system preference.
- The BibTeX buttons and citation pop-up are handled by a small script at the bottom of
  `index.html` — no external libraries are used.
- The footer disclaimer ("Views expressed here are my own…") is intentional and should be
  kept.
