---
name: Website Architecture Refactor
overview: "Phase 1 implements the ML domain structure: create ml/index.html with Demos/Concepts/Lit Reviews sections, create ml/concepts/vlm.html as the first concept page, and update main navigation to link to ml/ instead of #ml."
todos:
  - id: step1
    content: Create ML domain page (ml/index.html)
    status: completed
  - id: step2
    content: Create VLM concept page (ml/concepts/vlm.html)
  - id: step3
    content: Update main nav in index.html (ML link to ml/)
isProject: false
---

# Website Architecture Refactor – Phase 1 Plan

## Current State

- **[index.html](index.html)** – Main portfolio (sidebar, top-nav, sections for Robotics, BCI, ML, Tutorials, Work, About)
- ML content lives in the `#ml` section: two project cards (Drug Discovery, Science Automation) plus Tutorials/Notes

## Phase 1 Scope

Create the ML domain structure and first concept page. Build step by step.

---

## Step 1: Create ML Domain Page

**File:** `ml/index.html`

**Structure:**
- Reuse layout/styling from [index.html](index.html) (sidebar, top-nav, section cards)
- **Top nav:** Same banner as main page (Robotics, BCI, ML, Tutorials, Work, About). ML highlighted with `.primary` to show current context. Other links point to `../#section-id`.
- **No** domain-specific nav (Demos, Concepts, Lit Reviews) – those are in-page sections reached by scrolling.
- **Demos section:** Placeholder text if empty, or migrate the two ML project cards from index (Drug Discovery, Science Automation)
- **Concepts section:** Link to `concepts/vlm.html` (Vision-Language Models)
- **Lit Reviews section:** Placeholder list (e.g., "Coming soon" or empty list)

**URL:** `/ml/`

**Relative paths:** Use `../` for assets (e.g., `../assets/img/profile_billy.jpeg`), `../` for back-to-home.

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

**File:** [index.html](index.html)

**Change:** In the top-nav, update the ML link from `#ml` to `ml/`:

```html
<a href="ml/">ML</a>
```

**Back link:** Sidebar on ml/index.html links to `../` for "Back to overview."

---

## Folder Structure After Phase 1

```
billybyun.github.io/
├── index.html              # Main portfolio
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

| Decision | Recommendation |
|----------|----------------|
| **Styling** | Inline the same CSS from index.html into ml/index.html and vlm.html for Phase 1. |
| **Demos content** | Start with placeholder ("No demos yet") unless migrating the two ML project cards. |
| **Back navigation** | Sidebar on ml/index.html links to `../` for home. |
| **ML page nav** | Same top banner as main page (Robotics, BCI, ML, Tutorials, Work, About). ML highlighted. No Demos/Concepts/Lit Reviews nav – those are in-page sections. |

---

## Out of Scope (Phase 1)

- Robotics and BCI domain pages
- Main page redesign
- Tagging system, blog engine

---

## Future: Work Artifacts (LinkedIn-style)

**Goal:** Add artifact cards under each role in the Work section, like LinkedIn – thumbnail image, title, and link to external article/paper/video.

**Examples from your LinkedIn:**
- Precision Neuroscience: "Exclusive | Inside the Operating Room: Doctors Test a Revolutionary Brain-Computer Implant" (article/video)
- Nature Biomedical Engineering paper (publication)

**Implementation sketch:**
- Restructure Work section: each role becomes a block with description + optional `artifact` list
- Each artifact: `<a href="...">` wrapping a card with thumbnail (`<img>` or `background-image`), title, and external-link icon
- Store thumbnails in `assets/img/` or use Open Graph images from URLs if feasible
- Reuse `.project-card`-style layout or create `.artifact-card` (compact horizontal or square thumbnail + text)

**Placement:** Work section in [index.html](index.html), under each role entry.
