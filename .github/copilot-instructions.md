<!-- Copilot / AI agent guidance for hillarykhuu.github.io -->
# Copilot Instructions — hillarykhuu.github.io

Purpose: Short, actionable guidance to make AI coding assistance immediately productive working on this repo.

1) Big picture
- This is a static GitHub Pages portfolio site served from the repository root (repo name indicates Pages from root). There is no build step: pages are plain HTML/CSS with images and assets in `projects/`.
- Major pieces: root pages (`index.html`, `about.html`), shared styles (`css/style.css`), and per-project folders under `projects/` (each contains `index.html` + asset subfolders).

2) How content is organized (useful patterns)
- Project listing: `index.html` uses `.project-grid` and `.project-card` elements. To add a new project, add a new `.project-card` anchored to `projects/projectX/index.html`.
- Galleries: use the `image-gallery` and `gallery-container` / `gallery-card` patterns already present in `projects/project1/index.html` for consistent layouts.
- Styles: global variables and theme live in `css/style.css` (CSS variables for colors, utility classes for grids and image responsiveness). Many project pages include inline `<style>` blocks — prefer migrating shared styles into `css/style.css` for consistency.
- Images: assets live in project-specific folders (e.g., `projects/project1/aligned_ncc_0912_basic/`). Keep large original `.tif`/raw images out of production pages or add compressed web-versions for fast page loads.

3) Developer workflow / quick commands
- Preview locally: run a simple static server at repository root (recommended):

  python -m http.server 8000

  then open http://localhost:8000
- No build/test commands are present. Editing is: modify files, commit, push to GitHub (Pages should publish from the repo root). Confirm Pages branch in repository settings if unsure.

4) Project-specific conventions & gotchas
- Relative navigation: project pages are nested; internal links use `../../index.html` and similar. Keep relative paths correct when moving files.
- Accessibility: images generally include `alt` attributes — continue this pattern.
- Consistency: Some project pages duplicate header/nav and use custom colors; when changing site-wide behavior, update `css/style.css` and then adjust per-project overrides only if necessary.

5) When to propose changes
- Consolidate styles into `css/style.css` when multiple project pages duplicate the same CSS rules.
- Replace oversized `.tif` images used for previews with optimized `.jpg`/`.webp` copies and keep originals in an `archive/` folder if needed for reproduction.

6) Examples (copy-ready snippets)
- Add a project card in `index.html`:

    <div class="project-card">
        <a href="projects/project6/index.html">
            <h3>Project 6</h3>
            <p>Short description</p>
        </a>
    </div>

- Use an in-page gallery pattern (see `projects/project1/index.html`):

    <div class="image-gallery">
      <img src="images/1.jpg" alt="caption">
      <img src="images/2.jpg" alt="caption">
    </div>

7) Files to inspect when making changes
- Root pages: [index.html](index.html), [about.html](about.html)
- Shared styles: [css/style.css](css/style.css)
- Example project with gallery & inline styles: [projects/project1/index.html](projects/project1/index.html)

If any of these assumptions are incorrect or you'd like different conventions (build pipeline, image optimization rules, linting), tell me what to add or change and I'll update this file.

---
Requested next step: review and tell me any missing workflows, custom deploy steps, or preferred style conventions to include.
