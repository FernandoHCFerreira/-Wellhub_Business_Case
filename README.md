# Wellhub Business Case — refined deck (v2)

`Wellhub_Business_Case_v2.html` — drop-in replacement for your single-file deck.
Self-contained, no build step. Push it to GitHub Pages as-is.

## What changed vs your original

**Code quality**
- Removed the silent bug: inline JS inside the Tailwind `<script src>` tag was being dropped by the browser.
- Deduplicated CSS rules (`.slide.active`, `.exiting-forward` were defined twice).
- Consolidated two `<style>` blocks into one organised block with section comments.
- All UI strings now in English (was mixed PT/EN).

**Visual polish & typography**
- Replaced every emoji icon with inline SVGs that inherit `currentColor` (more senior, sharper at any size, prints well).
- Added `font-feature-settings` for Instrument Serif stylistic alternates.
- Every gradient-clip headline now has a solid fallback color (won't disappear in older browsers).
- Persistent top-left brandmark (`Wellhub · Business Case`).
- Top progress bar that fills as you advance.

**Animations & transitions**
- Added a backward exit transition (was forward-only).
- Smoother Apple-style easing curve, ~600ms (snappier in Q&A).
- Reveal stagger and floating blobs respect `prefers-reduced-motion`.

**Accessibility & responsiveness**
- Dots are real `<button role="tab">` with aria-labels per slide title.
- Slide counter uses `aria-live="polite"` (screen readers announce changes).
- Skip link, focus-visible rings, `role="region"` + `aria-roledescription="slide"`.
- New keyboard shortcuts: `Home` `End` `PageUp` `PageDown` `?` (help overlay).
- `@media print` — `Ctrl+P` produces a clean one-slide-per-page PDF backup.
- OG / Twitter meta so the GitHub Pages link previews well on Slack / LinkedIn.

## Keyboard shortcuts

| Action | Keys |
|---|---|
| Next slide | `→` `Space` `PageDown` |
| Previous slide | `←` `PageUp` |
| First / last | `Home` `End` |
| Toggle large text | `F` |
| Help | `?` |
| Print / PDF | `Ctrl+P` |

## Phase 2

A React port inside the Lovable project (TanStack Start, design tokens in
`oklch`, framer-motion transitions, separate `/print` route) is queued.
Just say the word and I'll build it next.
