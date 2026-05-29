# Creative Brief — CCPA Notice

**Source URL (recreate to the letter, then clean it up):** [https://www.prizestash.com/ccpa](https://www.prizestash.com/ccpa)
**Notes from tracker:** Legal Page
**Folder:** `pages/www.prizestash.com_ccpa/`
**Output file:** `index.html` (sibling of this brief)

---

## 1. Purpose

California Consumer Privacy Act disclosure summarizing rights and how to exercise them.

This page is a **like-for-like recreation** of `https://www.prizestash.com/ccpa` — every clause, field, headline, and link from the live page must appear in the rebuild. Pull the exact body copy and structure from the live page, then re-skin it using the design system below. Do not paraphrase legal text; copy it verbatim.

## 2. Content sections (in order)

1. Hero — title 'California Consumer Privacy Act Notice', updated date
2. Plain-language summary card (purple-tint background) with the four key rights as bullets
3. 1 — Categories of information collected
4. 2 — Sources of information
5. 3 — Business purposes for use
6. 4 — Third parties information is shared with
7. 5 — Your rights (Access, Delete, Opt-Out of Sale, Non-Discrimination)
8. 6 — How to exercise your rights — links to RTA, RTD, and Do-Not-Sell forms
9. 7 — Verification process
10. 8 — Authorized agents
11. 9 — Contact

> **Sourcing note:** open `https://www.prizestash.com/ccpa` and copy the actual text into the matching section above. If a section on the live page is missing here, add it; if a section here doesn't exist on the live page, drop it. Goal is exact content parity, cleaner presentation.

## 3. Layout

720px column, two-column table for category × source mapping (collapses to stacked cards under 640px).

## 4. Calls to action

Two prominent buttons in the rights section: 'Request my data' (links to RTA) and 'Delete my data' (links to RTD). Both Push Purple primary buttons, 48px tall, full width on mobile.


## Shared Design System (apply to every page)

### Color tokens
```css
:root {
  --push-purple: #5C3DE4;   /* primary CTA, links, accents */
  --dark-purple: #312679;   /* hover, emphasis */
  --clear:       #F1F1F1;   /* page background */
  --ink:         #1E1E1F;   /* primary text — never pure black */
  --ink-2:       #4a4a4d;   /* secondary text */
  --line:        #d2d6e0;   /* hairline borders */
  --surface:     #FFFFFF;   /* cards/containers */
  --purple-tint: #e6e2f8;   /* subtle highlight bands */
}
```

### Typography
- Headings: **Mada**, weights 500/600/700
- Body: **Open Sans**, weights 400/500/600
- Base size: 16px / line-height 1.6
- H1: 32px / 1.2 / Mada 700
- H2: 24px / 1.25 / Mada 600
- H3: 18px / 1.3 / Mada 600
- Small/meta: 13px / 1.4 / Open Sans 500, color `var(--ink-2)`

### Layout grid
- Max content width: **720px** for legal/long-form, **560px** for forms, **480px** for status messages.
- Side padding: 24px desktop / 16px mobile.
- Vertical rhythm: 24px between sections, 16px between paragraphs.
- Border radius: 12px on all cards/containers.
- Shadow: `0 8px 24px rgba(15, 23, 42, 0.08)` on raised cards only.

### Header (shared)
- Sticky top bar, 64px tall, white surface, 1px bottom border `--line`.
- Left: brand wordmark (text logo, Mada 600, 20px, `--push-purple`) linking to the site root.
- Right: optional "Back to site" link, Open Sans 500, 14px.

### Footer (shared)
- Top border `--line`, 32px vertical padding.
- Three stacked rows on mobile / two columns on desktop:
  1. Small copyright line: `© <YEAR> <Site Name>. All rights reserved.`
  2. Inline legal links separated by a 12px dot: Privacy Policy · Terms · CCPA · Contact.
- Text color `--ink-2`, 13px.

### Accessibility
- Minimum body contrast 4.5:1 (use `--ink` on `--surface`).
- Focus state: 2px outline in `--push-purple` with 2px offset.
- Skip-to-content link visible on focus.
- All links underlined inside body copy; remove underline only in nav.
- Tap targets ≥ 44×44px on mobile.

### Responsive breakpoints
- Mobile: ≤ 640px
- Tablet: 641–960px
- Desktop: ≥ 961px



## How to make it cleaner than the original

1. **Strip stock-tool chrome.** The original was built in Unbounce or a similar drag-and-drop tool, so it likely has redundant wrappers, inline styles, and absolute-positioned blocks. Rebuild with a single semantic structure: `<header>`, `<main>`, `<footer>`.
2. **Single typography scale.** Replace the original mixed-font usage with Mada + Open Sans only.
3. **Single color palette.** Replace any off-brand greys/blues with the four-token system above.
4. **Predictable spacing.** Use the rhythm tokens (4 / 8 / 16 / 24 / 32 px) — never one-off margins.
5. **Remove dead weight.** Drop hero image carousels, redundant CTAs, social-proof badges that don't drive action, and trust-icon rows that double up.
6. **One primary CTA per view.** Anything else becomes a secondary text link.
7. **Real semantic HTML.** Headings are `<h1>/<h2>/<h3>`, lists are `<ul>/<ol>`, the form is a `<form>` with `<label>` and proper `name`/`autocomplete` attributes.
8. **Tighter legal copy formatting.** For long-form legal pages, use a sticky in-page TOC and numbered H2s with anchor IDs so users can deep-link to a clause.
9. **Mobile-first build.** Author at 360px first, then progressively enhance to 720/960px.
10. **Performance.** Inline critical CSS (<14kB), defer everything else. Use `font-display: swap`. No external JS unless the page actually needs it.


## Definition of done

- [ ] Every piece of copy from `https://www.prizestash.com/ccpa` is present in `index.html` (verbatim for legal sections).
- [ ] Page validates as HTML5 with no console errors.
- [ ] Lighthouse: Performance ≥ 95, Accessibility ≥ 100 on mobile.
- [ ] Renders cleanly at 360 / 768 / 1280 px viewports.
- [ ] All internal legal links (Privacy, Terms, CCPA, Contact) resolve to the matching sibling page in `pages/`.
- [ ] Page uses only the four Pushnami color tokens and the Mada / Open Sans font pair.
