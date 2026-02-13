# Website Context for Agents

## Current State
- Site is a static GitHub Pages site using plain HTML/CSS.
- Primary layout: sidebar + main content, dark glassy theme.
- `horizontal-layout.html` currently acts as the main page draft.

## Target Direction
- Refactor into domain pages with consistent structure:
  **Demos → Concepts → Literature Reviews**
- Start with ML: create `/ml/` and first concept page `/ml/concepts/vlm.html`.

## Constraints
- No frameworks (no React, no Next.js).
- Keep existing visual style (reuse current CSS).
- Prefer minimal diffs and incremental steps.
- Avoid broken relative links.

## Next Tasks (Phase 1)
1) Create `ml/index.html` (ML landing with Demos/Concepts/Lit sections).
2) Create `ml/concepts/vlm.html` (VLM concept page).
3) Update main nav to link ML to `ml/` instead of `#ml`.

## Link Conventions
- Use folder `index.html` so links can be `ml/` not `ml/index.html` where possible.
