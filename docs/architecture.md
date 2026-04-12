# Architecture

## Overview

Heart Sutra is a **static multi-page mini site** hosted on GitHub Pages. It is a spoke in the hub-and-spoke model under The Dharma Gate portal, following the same architecture as the DaoDeJing mini site under TheWayWithin.

- The **hub** is [The Dharma Gate](https://lugh3456.github.io/DharmaGate/)
- This **spoke** is a standalone repository with its own index and section pages
- The hub links to this site; this site links back via portal bar and footer

HTML + external CSS only. No frameworks, no build tools.

---

## Folder Structure

```
HeartSutra/
  index.html        <- intro page with 3 section cards
  section1.html     <- Opening 序分 (4 explanation cards)
  section2.html     <- Main Body 正宗分 (11 explanation cards)
  section3.html     <- Mantra 咒语 (3 explanation cards)
  css/
    style.css       <- all styles (design tokens, components, responsive)
  docs/
    readme.md       <- project overview
    architecture.md <- this file
    ai-context.md   <- instructions for AI assistants
    plan.md         <- vision and objectives
    roadmap.md      <- delivery checklist
```

---

## Page Structure — Index

```
<portal-bar>           <- link back to DharmaGate
<header.site-header>   <- "Heart Sutra" title, Chinese subtitle, tradition label
<main>
  .intro               <- brief description of the sutra
  .card-grid           <- 3 section cards (link to section pages)
    a.section-card     <- Chinese title + English title
<footer>
```

---

## Page Structure — Section Pages

```
<portal-bar>              <- link back to DharmaGate
<header.section-header>   <- section name (e.g. "Opening · 序分"), nav links
<main.section-container>
  section.full-text       <- full Chinese text + 🔊 聆听经文 button
  section.line-explanation
    h2                    <- "逐句解释"
    .explanation-card     <- one per phrase:
      p.line              <- Chinese phrase (bold)
      p.explanation-zh    <- short Chinese explanation (concept-focused)
      button.toggle-btn   <- "Details · 详细 ▾"
      .detail-content     <- hidden by default:
        p.translation     <- English translation (red)
        p.explanation     <- full English commentary (grey)
  section.summary
    h2                    <- "总结 · Summary"
    p.summary-zh          <- Chinese summary
    button.toggle-btn     <- "English · 英文 ▾"
    .detail-content       <- hidden by default:
      p.explanation       <- English summary
<script>                  <- toggleDetail() + speak()
<footer>
```

---

## CSS Architecture

All styles are in `css/style.css`, organised into labelled sections:

```
DESIGN TOKENS          <- CSS custom properties (:root)
SKIP LINK              <- accessibility
RESET & BASE
PORTAL BAR
HEADER — INDEX
HEADER — SECTION PAGE
INTRO — INDEX
SECTION CARD GRID
SECTION PAGE CONTAINER
FULL TEXT BLOCK
LINE-BY-LINE EXPLANATION
EXPAND / COLLAPSE TOGGLE
SUMMARY
FOOTER
RESPONSIVE             <- <= 600px
```

---

## Design Tokens

| Token | Value | Usage |
|-------|-------|-------|
| `--bg` | `#f7f0e6` | Page background (warm cream) |
| `--surface` | `#ffffff` | Card backgrounds |
| `--ink` | `#1c0f0f` | Header, footer, portal bar backgrounds |
| `--red` | `#b83232` | Primary accent |
| `--red-light` | `#d44e4e` | Hover states, heading colour |
| `--saffron` | `#c8820a` | Pinyin colour (legacy) |
| `--saffron-lt` | `#e09c2a` | Portal bar link colour |
| `--text` | `#2d1f1f` | Body text, Chinese explanations |
| `--muted` | `#7a6060` | English explanations, toggle button |
| `--border` | `#e0d0c8` | Card borders, dividers |

---

## Expand/Collapse Pattern

Each explanation card and the summary section use a simple toggle:

- A `<button class="toggle-btn">` sits after the Chinese content
- Its sibling `<div class="detail-content" hidden>` holds the English content
- `toggleDetail(btn)` flips the `hidden` attribute and swaps ▾/▴
- `aria-expanded` is updated for accessibility

No external JS libraries. Plain vanilla JavaScript.

---

## Speech Synthesis

Each section page has a 🔊 聆听经文 button that reads the full Chinese text aloud using the Web Speech API. It prefers a `zh-CN` voice and runs at 0.85x speed for clarity.

---

## External Dependencies

Google Fonts (loaded via `<link>`):
- Noto Serif SC — headings, Chinese phrases
- Noto Sans SC — body text, buttons, descriptions

No other external dependencies.

---

## Responsive Breakpoints

| Breakpoint | Change |
|-----------|--------|
| > 600px | Default layout |
| <= 600px | Single-column cards, reduced padding, smaller full-text font |

---

## Hosting

GitHub Pages via the `lugh3456` account.
Deployment: push files to repository root on `main` branch.
Planned URL: `https://lugh3456.github.io/HeartSutra/`
