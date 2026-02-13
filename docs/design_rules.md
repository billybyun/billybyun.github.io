# Design Rules (UI Consistency)

## Visual Hierarchy
- Demos = cards (strongest visual weight)
- Concepts = lighter cards or simple blocks
- Lit Reviews = list style (lightest weight)

## Layout
- Keep two-column layout (sidebar + content) on desktop.
- Sidebar should remain sticky (no heavy borders/glows).
- Avoid nested scrollboxes unless necessary.

## Typography
- Body text: 0.9–0.95rem
- Section headings: ~1.05rem
- Keep contrast readable (avoid too-muted text)

## Components to Reuse
- `.section` for content blocks
- `.project-card` for demos
- `.concept-card` for concepts
- `.bullets` for lists
- `.tag` for labels

## Interaction
- Hover effects subtle (accent-soft background ok)
- Links: accent color, underline on hover

## Accessibility
- Ensure text contrast is readable on dark background.
- Provide alt text for images.
