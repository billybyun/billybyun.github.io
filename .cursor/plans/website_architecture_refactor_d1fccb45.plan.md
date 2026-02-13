---
name: Website Architecture Refactor
overview: "Phase 1 implements the ML domain structure: create ml/index.html with Demos/Concepts/Lit Reviews sections, create ml/concepts/vlm.html as the first concept page, and update main navigation to link to ml/ instead of #ml."
todos: []
isProject: false
---

# Website Architecture Refactor – Phase 1 Plan

## Current State

- **[horizontal-layout.html](horizontal-layout.html)** – Full portfolio with sidebar, top-nav (Robotics, BCI, ML, Tutorials, Work, About), and anchor-based sections (#ml, #robotics, #bci)
- **[index.html](index.html)** – Simple landing card (GitHub, LinkedIn, Scholar)
- ML content lives in the `#ml` section: two project cards (Drug Discovery, Science Automation) plus Tutorials/Notes

## Phase 1 Scope

Create the ML domain structure and first concept page. No changes to Robotics/BCI or main page redesign.

---

## Step 1: Create ML Domain Page

**File:** `ml/index.html`

**Structure:**

- Reuse layout/styling from [horizontal-layout.html](horizontal-layout.html) (sidebar, top-nav, section cards)
- Domain-specific nav: Demos | Concepts | Lit Reviews (in-page anchors)
- **Demos section:** Placeholder text if empty, or migrate the two ML project cards from horizontal-layout (Drug Discovery, Science Automation)
- **Concepts section:** Link to `concepts/vlm.html` (Vision-Language Models)
- **Lit Reviews section:** Placeholder list (e.g., "Coming soon" or empty list)

**URL:** `/ml/` (or `ml/index.html`)

**Relative paths:** Use `../` for assets (e.g., `../assets/img/profile_billy.jpeg`), `../horizontal-layout.html` or `../` for back-to-home.

---

## Step 2: Create VLM Concept Page

**File:** `ml/concepts/vlm.html`

**Content:**

- **Definition:** What Vision-Language Models are
- **Core architecture:** Vision encoder → Projector → LLM (brief diagram or bullet list)
- **Why it matters:** 1–2 paragraphs on relevance to robotics, BCI, or general ML
- **Upcoming literature reviews:** List of planned reviews (placeholder links or "TBD")

**Layout:** Same design system as domain page. Breadcrumb or back link: ML → Concepts → VLM.

**URL:** `/ml/concepts/vlm.html`

**Relative paths:** Use `../../` for root assets.

---

## Step 3: Update Main Navigation

**File:** [horizontal-layout.html](horizontal-layout.html)

**Change:** In the top-nav (around line 355), update the ML link:

```html
<!-- From -->
<a href="#ml">ML</a>

<!-- To -->
<a href="ml/">ML</a>
```

**Consider:** Add a back/home link on `ml/index.html` so users can return to the main portfolio. Sidebar can link to `../horizontal-layout.html` or `../` depending on whether index.html or horizontal-layout is the canonical home.

---

## Folder Structure After Phase 1

```
billybyun.github.io/
├── index.html
├── horizontal-layout.html
├── vertical-layout.html
├── style.css
├── assets/
│   └── img/
└── ml/
    ├── index.html          # ML domain page
    └── concepts/
        └── vlm.html        # VLM concept page
```

---

## Design Decisions


| Decision            | Recommendation                                                                                                                                             |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Styling**         | Inline the same CSS from horizontal-layout into ml/index.html and vlm.html for Phase 1. Extract to shared `style.css` or `layout.css` in a later refactor. |
| **Main page**       | Keep horizontal-layout.html as the primary portfolio for now. Index.html remains the simple landing. Clarify later which becomes the "curated overview."   |
| **Demos content**   | Start with placeholder ("No demos yet" or similar) unless you want to migrate the two ML project cards immediately.                                        |
| **Back navigation** | Sidebar on ml/index.html should link to `../horizontal-layout.html` (or `../` if index is home) for "Back to overview."                                    |


---

## Out of Scope (Phase 1)

- Robotics and BCI domain pages
- Main page redesign
- Tagging system
- Blog engine
- Shared CSS extraction (optional for Phase 1)

---

## Future Phases (Reference)

- **Phase 2:** Replicate structure for Robotics and BCI
- **Phase 3:** Curate main page (Selected Demos, Themes, Recent Reviews)
- **Phase 4:** Optional horizontal scroll, blog-style pagination for literature

