# Repository Guidelines

## Project Structure & Module Organization
The site is a single-page app served from `index.html`, which hosts HTML markup, Tailwind utility classes loaded via CDN, and embedded Chart.js logic near the footer script block. Static documents, media, and downloadable artifacts live under `assets/`, grouped into `audio/`, `hero/`, `video/`, and root-level PDFs such as `Sun-Island-bali-report.pdf` plus the distributable `sun-island-bali.zip`. Keep new assets in the appropriate subfolder and reference them with relative paths so the page can run directly from the filesystem.

## Build, Test, and Development Commands
No build step is required; open `index.html` directly or serve the folder locally. For a quick local server, run `python -m http.server 8000` from the repository root or `npx serve .` if Node is available. Use browser devtools live reload or lightweight extensions to speed feedback when editing the inline scripts.

## Coding Style & Naming Conventions
Follow the existing four-space indentation for HTML blocks and align closing tags vertically. JavaScript inside the `<script>` block uses camelCase for functions and variables (`formatTime`, `scoreCompositionChart`); match that pattern and keep helper functions grouped by feature with section comments. Tailwind class lists should stay ordered roughly layout > spacing > color to remain readable, and custom IDs should stay kebab-case (`progress-bar-container`) to avoid collisions.

## Testing Guidelines
We rely on manual smoke tests in a Chromium-based browser and Safari. After changes, verify charts render without console warnings, the chatbot accepts input and returns canned responses, audio playback toggles correctly, and all download links under `assets/` resolve. If you introduce heavier logic, add temporary Jest or Playwright checks under a `tests/` folder and remove or document them in the pull request.

## Commit & Pull Request Guidelines
Commits in this repo are short and imperative (`Create README.md`, `AUDIO`); follow that style, limit the subject to 72 characters, and scope changes narrowly. Each pull request should include a summary, before/after screenshots or screen capture for visual tweaks, a list of manual test steps run, and references to any related issues or briefs. Note any large assets added and justify their size to keep the downloadable bundle manageable.
