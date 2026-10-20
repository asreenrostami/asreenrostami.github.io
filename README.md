# asreenrostami.github.io

Personal academic site, built with Jekyll (the same engine GitHub Pages runs natively,
so no build step is needed on your end — just push and GitHub Pages builds it).

## Structure

- `_config.yml` — site title, your bio blurb, and the four profile links (ACM, LinkedIn,
  ORCID, Google Scholar) that appear fixed in the navbar/footer on every page. Also the `nav:`
  list that drives the top navigation.
- `_layouts/default.html` — the shared page shell: fixed top navbar (page links + the four
  profile icons) and footer. Every page uses this, so editing it once changes every page.
- `_layouts/post.html` — layout for blog posts.
- `index.md` — About / landing page, including the profile-photo hero.
- `research.md`, `publications.md`, `awards.md`, `events.md` — the other pages.
- `blog.md` — lists everything in `_posts/`.
- `_posts/` — one Markdown file per blog post, named `YYYY-MM-DD-title.md`. Copy the
  starter post there as a template for new ones.
- `assets/` — CSS, the vendored Bootstrap / Font Awesome / Academicons files (copied from
  your old site so the icons keep working without relying on any third-party CDN), and
  `assets/img/profile-ri.jpg` (your current RISE profile photo).
- `papers/` — your PDF files, unchanged from the old site.
- `legacy-single-page/` — your previous one-page site, kept here as a backup. Safe to
  delete once you're happy with the new site, but not required for the new site to work.

## Editing content

Each page is plain Markdown with a bit of HTML mixed in — open the `.md` file and edit
the text directly.

## Publishing

Commit and push this folder to your `<username>.github.io` repository's default branch;
GitHub Pages will build and deploy it automatically. In your repo's Settings → Pages,
make sure the source is set to the branch you pushed (root folder).

## Known issues to fix before publishing

- `_config.yml` has a placeholder `url:` — replace `https://asreenrostami.github.io` with
  your actual GitHub Pages URL if it differs.
- `papers/thesis.pdf` is ~243 MB. GitHub rejects any single file over 100 MB in a normal
  push, so this file will fail to upload as-is. You'll need to either use
  [Git LFS](https://git-lfs.com), compress/host the PDF elsewhere (e.g. DiVA, which the
  Publications page already links to) and swap the link, or split/shrink the file.
- Five publications link to PDFs that aren't in `papers/` (this was already the case on
  the old site, not introduced here): `Hack-CSCW22.pdf`, `KintsugiVR_IMX22.pdf`,
  `Rostami_SOUPS22.pdf`, `VRtrouble-chi22.pdf`, `dramaten-2021.pdf`. Add those files to
  `papers/` or the links will 404.
- `events.md` has placeholder text for talks and thesis/internship openings — fill in
  real entries (there are commented-out HTML templates in the file to copy).
- The About page now uses `assets/img/profile-ri.jpg` (pulled from your RISE profile
  page, resized to 900px wide). The original `profile.jpg` from the single-page site is
  still in `legacy-single-page/img/` if you'd rather use that one instead — swap the
  filename in `index.md`'s hero `<img>` tag to switch.
