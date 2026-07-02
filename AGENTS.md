# Repository Guidelines

## Project Structure & Module Organization

This repository contains a static conference website for the 5th International Conference on the Economics of Informality.

- `index.html` holds the full page content and section structure.
- `styles.css` contains all layout, typography, responsive behavior, and visual styling.
- `assets/` stores images used by the page, including speaker photos, institutional logos, the hero image, and form/header artwork.
- `assets/logos/` contains individual institutional logo files.
- `CNAME` defines the custom domain used by GitHub Pages or related hosting.

There is no JavaScript application layer, package manager, or generated source inside this repository.

## Build, Test, and Development Commands

No build step is required. The site can be previewed directly:

```powershell
Start-Process .\index.html
```

For a local HTTP preview, run:

```powershell
python -m http.server 8080
```

Then open `http://127.0.0.1:8080/`. Use this option when checking asset paths, image loading, and browser behavior.

## Coding Style & Naming Conventions

Use plain, semantic HTML and keep section IDs stable because navigation and external links may depend on them. Maintain two-space indentation in HTML and CSS. Prefer descriptive class names such as `.committee-grid`, `.speaker-card`, or `.submission-layout`.

Store images with lowercase, hyphenated filenames where possible, for example `partner-logos.png` or `conference-hero.png`. Avoid replacing existing assets unless the visual change is intentional and verified.

## Testing Guidelines

There is no automated test suite. Before committing, perform manual checks:

- Open the page locally and verify all images load.
- Check desktop and mobile widths in browser dev tools.
- Confirm links, submission form buttons, speaker photos, and logo bands.
- Search for outdated dates or names with `rg`, for example:

```powershell
rg "August 20|Andrea Otero|Banco de la" .
```

## Commit & Pull Request Guidelines

Use short, imperative commit messages consistent with the existing history, such as:

- `Update scientific committee`
- `Correct Andrea Otero name`
- `Fix Universidad de los Andes logo in partner banner`

Pull requests should describe the user-facing change, list edited files, and include screenshots for visual changes. For logo, speaker, deadline, or committee updates, mention the source of truth and confirm that the live preview was checked.

## Deployment Notes

Push changes to `main` for GitHub-backed deployment. If publishing through Cloudflare Pages manual upload, regenerate the external deployment ZIP from the workspace and verify the custom domain after deployment.
