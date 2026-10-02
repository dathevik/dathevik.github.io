# CLAUDE.md

Personal academic website of Tatevik Mkrtchyan, astrophysicist (PhD student at Instituto de
Estudios Astrofísicos, Universidad Diego Portales, Santiago, Chile).

- Static site: **Jekyll 4.4** + **Hydejack 9.2.1** theme gem (free version).
- Repo: `github.com/dathevik/dathevik.github.io`, branch `main`.
- Live at **https://www.dathevik.com** (custom domain set in GitHub Pages settings, there is no
  `CNAME` file in the repo).
- Note the working directory: the git repo is `dathevik.github.io/`, nested one level inside
  `~/Desktop/website/`. Run all commands from the repo root (where `_config.yml` lives).

## Commands

The system Ruby is 2.6 and **will fail**. The project uses chruby with Ruby 3.4.1, and gems are
vendored in `vendor/bundle` (`.bundle/config` sets `BUNDLE_PATH`). Put the right Ruby on PATH first:

```bash
export PATH="$HOME/.rubies/ruby-3.4.1/bin:$PATH"

bundle install                                  # only after Gemfile changes
bundle exec jekyll serve                        # dev server at http://localhost:4000
bundle exec jekyll build                        # one-off build into _site (gitignored)
JEKYLL_ENV=production bundle exec jekyll build  # enables built-in search + HTML compression
```

Build takes about 1 second. The Sass `@import` deprecation warnings come from the theme gem and are
expected noise, not a problem to fix.

Search is disabled in development to save build time, so test it only with `JEKYLL_ENV=production`.

## Deployment

`.github/workflows/jekyll.yml` builds and deploys to GitHub Pages on every push to `main` (also
runnable via workflow_dispatch). CI uses **Ruby 3.3** with `bundler-cache: true`, so
`Gemfile.lock` is committed on purpose to pin gem versions. It fetches full git history because
`jekyll-last-modified-at` needs it.

Do not commit or push unless asked.

## Structure

```
_config.yml               site config, sidebar menu tree, Hydejack options, collections
index.md                  "About me", served at / (permalink: /)
404.md
_featured_categories/     the four top-level section landing pages (Research, Teaching, Personal, CV)
research/_posts/          Research subpages
research/projects/_posts/ individual research project pages
teaching/_posts/          Teaching subpages
personal/_posts/          News page
cv/                       Tatevik_Mkrtchyan_CV.pdf (embedded in an iframe on /cv/)
assets/img/docs/          conference posters (PDF)
_data/authors.yml         bio + social links shown in sidebar and page footers
_data/strings.yml         all theme UI strings ("Barev!" is the customized home label)
_data/variables.yml       typography and breakpoint values
_sass/my-style.scss       extra CSS (compiled into the main stylesheet)
_sass/my-inline.scss      CSS inlined into <head>, holds the sidebar nav tree styles
_includes/body/nav.html   LOCAL OVERRIDE of a theme include, renders the sidebar nav tree
_includes/my-head.html    extra <head> content
_includes/my-body.html    extra end-of-body scripts, incl. the nav tree behavior
docs/                     leftover Hydejack theme documentation, see Gotchas
```

Images live next to the content that uses them (`research/`, `teaching/`, `personal/`), not in
`assets/`.

Any file in `_includes/` shadows the same path inside the theme gem, which is how
`_includes/body/nav.html` replaces the theme's flat sidebar menu. When touching those, read the
gem's original first:
`vendor/bundle/ruby/3.4.0/gems/jekyll-theme-hydejack-9.2.1/_includes/`.

## URL map

| URL | Source file |
| --- | --- |
| `/` | `index.md` |
| `/research/` | `_featured_categories/research.md` |
| `/research/high-redshift-quasars/` | `research/_posts/2025-02-05-high-z-quasars.md` |
| `/research/high-redshift-quasars/sed-selection/` | `research/projects/_posts/2025-02-01-1.md` |
| `/research/high-redshift-quasars/radio-loud/` | `research/projects/_posts/2026-07-02-4.md` |
| `/research/high-redshift-quasars/lsst/` | `research/projects/_posts/2025-02-03-3.md` |
| `/research/circumgalactic-medium/` | `research/_posts/2025-02-06-cgm.md` |
| `/research/circumgalactic-medium/lya-halos/` | `research/projects/_posts/2025-02-02-2.md` |
| `/research/publications/` | `research/_posts/2024-02-01-publicatons.md` |
| `/research/talks/` | `research/_posts/2025-06-01-talks.md` |
| `/research/collaborations/` | `research/_posts/2023-01-23-collaborations.md` |
| `/research/outreach/` | `research/_posts/2025-02-03-outreach.md` |
| `/teaching/` | `_featured_categories/teaching.md` |
| `/teaching/students/` | `teaching/_posts/2025-02-03-Teaching.md` |
| `/teaching/mentorship/` | `teaching/_posts/2024-01-23-Mentorship and interviews.md` |
| `/personal/` | `_featured_categories/personal.md` |
| `/personal/news/` | `personal/_posts/2024-02-07-news.md` |
| `/cv/` | `_featured_categories/cv.md` |

The sections were renamed in Oct 2026 (Science to Research, Education to Teaching) because
"Education" read as her own schooling rather than her work in the field. In the same pass
`high-z-quasars` and `cgm` were spelled out, so that the URL, the sidebar label, the title on the
banner photo and the page's own title all read the same way. Every old URL is preserved by a
`redirect_from:` entry in the page's front matter, served by `jekyll-redirect-from`, and pages
renamed twice carry both generations. **Keep those entries.** Add a new one whenever a page's
`permalink` changes, since her CV, posters and published outreach pieces link to these URLs.

**One name per thing.** For any subpage, the sidebar label, the title laid over its banner photo,
its page title and its URL slug should all say the same thing. She asks for this specifically, and
mismatches between them are the thing she notices first.

Filenames carry no meaning here. **Every page sets its own `permalink`**, so dates and numbered
names like `2025-02-01-1.md` are leftovers from how the file was created. A file in a `_posts`
directory still needs a valid `YYYY-MM-DD-` prefix for Jekyll to accept it, but changing the date
does not change the URL. When adding a page, set the `permalink` explicitly and do not rely on the
filename.

## Sidebar navigation tree

Sidebar navigation comes from the `menu:` list in `_config.yml`, not from the file tree, so a new
page is only reachable from the sidebar once it is added there. Each entry may carry a `submenu:`
list, which renders as a collapsible tree: the section label stays a link to its landing page, and
a caret button next to it expands the subpages. A `submenu:` nested inside a submenu entry gives a
third, indented level with no caret of its own, shown whenever the section is open. Menu labels are
independent of page titles, so keep them short enough for the 22rem sidebar.

Three files work together:

- `_includes/body/nav.html` builds the markup, overriding the theme's flat version.
- `_sass/my-inline.scss` styles it. In production the theme inlines that file into a `<style>` block
  in `<head>`, so the sidebar does not flash unstyled; in development it arrives via the external
  stylesheet instead, which is why a dev page has no nav CSS in its `<head>`. `.nav-sub` collapses
  via `max-height`, currently capped at `32rem`, which needs raising if a section ever grows past
  roughly 12 items.
- `_includes/my-body.html` holds the behavior: the caret toggle, plus marking the current page and
  auto-expanding the section it belongs to.

**Why the current-page state is set in JavaScript rather than Liquid.** The sidebar is rendered
outside `#_main`, and Hydejack's push-state navigation only replaces `#_main`. The sidebar is never
re-rendered, so anything Liquid writes into it would go stale the moment a visitor clicks a link.
On top of that, the theme pulls the sidebar in with `include_cached`, so `page.url` inside the nav
include would be baked in from whichever page happened to build first. The script therefore
re-syncs on each `hy-push-state-after` event. Do not try to move this into Liquid.

A `<noscript>` block in `nav.html` leaves every section expanded when JavaScript is off.

Layout notes, since the rest of the sidebar is centered and the tree is not:

- The nav block is left aligned, so every label shares a left edge instead of each being centered
  on its own length. The photo, title and tagline above it stay centered.
- The block is indented so the section labels begin exactly where the centered tagline's text
  begins. That edge cannot be hardcoded: the tagline is centered, so its left edge depends on how
  wide the text renders in the visitor's system font. `alignNav()` in `_includes/my-body.html`
  therefore measures the tagline text with a `Range`, compares it against where the first section
  label actually sits, and shifts `--nav-pad` by the difference, re-running on resize and after
  `document.fonts.ready`. The value in `my-inline.scss` is only the pre-measurement fallback.
  Deriving the indent arithmetically from the caret width instead would break as soon as the caret
  or gap is resized, which is why it measures.
- The caret sits to the left of the section label, and is first in the markup too so that keyboard
  tab order matches the visual order. Items with no subpages are indented by `--nav-indent` on the
  `<li>` to line up with the section labels.
- The current page is marked with a soft shade, not an underline. Underlines are removed from all
  nav links. The shade's halo is drawn with `box-shadow` spread rather than padding so the
  highlight contributes no layout, which keeps labels on the same left edge whether or not they are
  current. Both link types are `inline-block`, which is what makes that work.

One detail to preserve: the first menu link must keep `id="_drawer--opened"`, because the mobile
hamburger in the theme's `body/menu.html` targets that id to open the drawer.

## Content conventions

These are consistent across the site. Follow them rather than theme defaults.

- **`layout: plain`** on every page. It renders the content without the post/blog chrome.
- **`sitemap: false`** on nearly every page, and `hide_last_modified: true` on most.
- **Images are declared in front matter and referenced via Liquid**, which keeps the paths and
  captions at the top of the file:
  ```yaml
  image1: /research/projects/lsst.jpeg
  image_caption1: "Me at the Vera C. Rubin Observatory in Chile"
  ```
  ```html
  <figure>
    <img src="{{ page.image1 }}" alt="...">
    <figcaption>{{ page.image_caption1 }}</figcaption>
  </figure>
  ```
- **Page-scoped `<style>` block at the bottom of the file.** Section pages are hand-built HTML with
  their own CSS rather than plain markdown. `_sass/my-style.scss` is only for genuinely site-wide
  rules.
- **Repeated CSS patterns** (duplicated per page on purpose, keep them in sync when editing):
  - `.intro` / `.lead-in` for the opening paragraph and the bold line that introduces a list.
  - `.project` + `.project-media.break-layout` + `.media-link` + `.media-frame` + `.media-title`
    for the wide banner cards on `/research/` and `/teaching/`. `break-layout` is the theme's class
    for content that spans wider than the text column; `.media-frame--contain` switches the image
    from cropped to fitted (used for the transparent Lyman alpha animation).
  - Each banner is wrapped in an `<a class="media-link">`, so the photo and the title laid over it
    are one link to that subpage. **The text on the photo is the subpage's own name**, and there is
    deliberately no `<h2>` under the banner: the name on the photo is the section's only heading.
  - `.project-grid` + `.project-card` + `.project-status` on `/research/high-redshift-quasars/` and
    `/research/circumgalactic-medium/`: projects as tiles side by side, each tile one link to its
    project page, so there is no "read more". The grid is `repeat(auto-fit, minmax(15rem, 1fr))`, so
    adding or removing a card needs no other change and it reflows to one column on a phone by
    itself. `.project-status` is the short state of play ("Published", "Observing", "In progress",
    "Paper in review") and is **maintained by hand**: check it against the project page's text when
    editing either.
  - A subpage does not repeat the photo used for it on the parent landing page. The Mentorship page
    had its banner photo removed for exactly this reason.
- **Text first, then the picture it refers to.** Every page alternates a paragraph with the photos
  belonging to it, rather than collecting all the prose and then all the images. `/personal/` was
  restructured this way; keep a new topic's `.photo-row` directly under its paragraph.
- Front-matter image keys are named for their subject (`image_hiking`, `caption_cgm`), not
  `image1..image7`, so a key cannot drift away from the paragraph it belongs to.
- **Credit other people's figures** in the caption, kept short, e.g. the Lyman alpha visualization
  on `/research/` carries "Visualization code by Dr. Emanuele Farina."
  - `.learn-more` / `.back` / `.section-links` links, styled `#36a9e1` bold underlined.
  - `.video-preview` + `.video-play` for YouTube thumbnails with a play overlay. These link out to
    YouTube using `https://img.youtube.com/vi/<ID>/maxresdefault.jpg` (or `sddefault.jpg` when
    maxres is missing) instead of embedding an iframe, which keeps the pages light.
- **External links** use `{:target="_blank"}` in markdown or `target="_blank" rel="noopener"` in HTML.
- Theme accent is `rgb(79,177,186)` with `theme_color: rgb(25,55,71)`; the translucent banner
  captions reuse `rgba(25, 55, 71, 0.6)`.
- Math is available through kramdown with the KaTeX engine (compiled at build time by
  `kramdown-math-katex` + `duktape`), so it does not work on the legacy GitHub Pages pipeline.

## Science figures

Research figures come from her analysis repo at `~/PhDProjects/loud-quiet-quasars` (the paper draft
is in `paper/draft.tex`, final figures in `paper/plots/`). Two rules she has asked for:

- **Transparent backgrounds.** A plot with a white rectangle behind it looks pasted on; a
  transparent one sits on the page.
- **No literature citations** in the body text of project pages. They belong in the paper.

To regenerate a figure for the site, do **not** run her plot scripts directly: they overwrite the
paper's own figures, which need their white backgrounds. Run the script through a wrapper that
redirects the output and forces transparency, so her repo is left untouched:

```python
import runpy, matplotlib
matplotlib.use("Agg")
from matplotlib.figure import Figure

SCRIPT = "<path in ~/PhDProjects/loud-quiet-quasars/.../some_plot.py>"
TARGET = "<path in this repo>/research/<name>.png"

_orig = Figure.savefig
def savefig(self, fname, *a, **kw):
    if str(fname).endswith(".png"):           # redirect the PNG, drop the PDF
        kw["transparent"] = True; kw["dpi"] = 200
        return _orig(self, TARGET, *a, **kw)
Figure.savefig = savefig
runpy.run_path(SCRIPT, run_name="__main__")   # run_name/`__file__` keep its relative data paths working
```

Verify afterwards that the source script's own output file still has its original timestamp.

Numbers on the project pages (redshift ranges, detection rates, luminosities) are taken from the
paper draft and drift as it changes. Re-check them against `paper/draft.tex` when editing.

## Writing voice

The prose is first person, warm, direct and a bit playful ("Welcome to my room!", "joined our dark
forces"). Science pages explain the physics in plain language before any jargon. When editing or
drafting text:

- **No em-dashes.** Use commas, periods or parentheses instead. This is a standing preference.
- Keep her phrasing. Do not smooth the personality out of it.
- Research claims, dates, paper references and student names are factual. Do not invent or
  extrapolate them.

## Gotchas

- **`jekyll-titles-from-headings` is disabled on purpose, in `_config.yml`. Do not re-enable it.**
  Its `title?` check calls `inferred_title?`, which returns true for *every* `Jekyll::Document`, so
  it treats every file under a `_posts/` directory as having no real title no matter what the front
  matter says. For any post whose body starts with an h1/h2/h3, it overwrote `title:` with that
  heading and deleted the heading from the body. It had silently renamed `/research/talks/` to
  "Conferences" and eaten its "Conferences" subheading on the live site. Every page here sets its
  own title, so the plugin only ever did harm. Consequence to remember: a post's body should not
  start with a heading repeating its title, because the title is already rendered as the `<h1>`.
- `docs/` is the untouched Hydejack starter-kit documentation and still builds to `/docs/`. Likewise
  `README.md`, `CHANGELOG.md`, `_includes/features.md` and `_includes/table.md` are theme boilerplate
  about Hydejack, not about this site. Do not treat them as project documentation.
- `collections:` in `_config.yml` declares `projects` and `science` collections, but there are no
  `_projects/` or `_science/` directories. Those entries are vestigial; the real content is posts
  under `research/`, `teaching/` and `personal/`. The `defaults:` block for `hyde/` is also dead.
- `dark_mode` is configured in `_config.yml` but only works in Hydejack PRO. This repo uses the free
  gem, so those settings have no effect.
- `research/Movie_PSO352m15_alpha.mov` is a 350+ MB master video, gitignored and in `exclude:`. The
  web version actually used on the site is `research/pso352_lya_halo.webp`.
- `_site/` is gitignored but present locally, and `.jekyll-cache/` and `vendor/` too. Never edit
  anything under `_site/`, it is regenerated on every build.
- macOS keeps creating `.DS_Store` files throughout the tree. They are gitignored, ignore them in
  `git status`.
- `_data/authors.yml` still has placeholder angle brackets in `name:` and a typo in the email
  (`...udp.cld`), plus a leftover `author2` dummy author. `_config.yml` has the same bracketed
  `author.name`. Harmless for rendering but worth fixing if touching those files.
