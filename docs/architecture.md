# Site Architecture (Source of Truth)

## Goal
A scalable research portfolio organized by: **Demos → Concepts → Literature Reviews** across domains.

## Information Architecture
Each domain page uses the same 3-layer structure:
1) **Demos** (systems + results + links to code)
2) **Concepts** (synthesis / mental models)
3) **Lit Reviews** (paper-by-paper notes)

Main landing page is curated highlights across all domains.

## URLs + Folder Mapping
- `/` → `index.html` (curated hub)
- `/ml/` → `ml/index.html`
- `/ml/concepts/vlm.html` → VLM concept page
- `/robotics/` → `robotics/index.html` (Phase 2)
- `/bci/` → `bci/index.html` (Phase 2)

## Navigation Rules
- Top nav links go to domain pages (not long-scroll anchors) once a domain page exists.
- Each domain page must contain: Demos, Concepts, Lit Reviews (omit empty sections if needed).

## Phases
- Phase 1: ML page + first concept page (VLM)
- Phase 2: Robotics page + VLA concept + link from robotics demos to concepts
- Phase 3: BCI page + decoding/LM concept + lit review expansion
