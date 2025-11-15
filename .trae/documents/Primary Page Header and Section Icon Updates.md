## Goals
- Move “For Primary School Students (Grades 1–6)” to the top as the main page header, replacing the current “NJAIO — Primary”.
- Remove the yellow numbered circles from the benefits list.
- Add a distinct icon to each of the five sections to improve kid-friendly clarity.

## Implementation
- Header/hero
  - Replace the brand text in the header with “For Primary School Students (Grades 1–6)”.
  - Update the hero title to the same wording and remove the duplicate section heading inside the card.
- List styling
  - Replace the `.features` counter-based styling by removing `counter-reset`, `counter-increment`, and the `::before` circle.
  - Keep rounded list items and soft shadows for a playful look.
- Section icons
  - Update each top-level `<li>` title to include an emoji icon:
    - Awareness & Recognition: 🔎
    - Critical Thinking Foundations: 🧠
    - Creativity & Imagination: 🎨
    - Responsible Use: 🛡️
    - Future Orientation: 🚀
  - Style icons with a slightly larger size and consistent spacing.
- Accessibility
  - Wrap icons in `<span aria-hidden="true">…</span>` and keep clear text labels.
  - Preserve color contrast and font sizes for readability.

## Verification
- Refresh the local preview to confirm:
  - Top header shows “For Primary School Students (Grades 1–6)”.
  - No numbered circles appear in the list.
  - Each of the five sections displays its icon consistently.
