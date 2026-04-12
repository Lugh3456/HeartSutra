# AI Context — Heart Sutra

## What this project is

A static mini site for studying the Heart Sutra (般若波罗蜜多心经), one of nine scripture sites under The Dharma Gate portal. Same architecture as DaoDeJing — HTML + external CSS, no frameworks.

## Current state (as of 2026-04-11)

- All files built and ready for deployment
- 3 section pages: Opening (序分, 4 cards), Main Body (正宗分, 11 cards), Mantra (咒语, 3 cards)
- Each card: Chinese phrase (bold) + short Chinese explanation (concept-focused, accessible register) + collapsible "Details" toggle containing English translation + full English commentary
- Summary at end of each section: Chinese by default, expandable English
- Speech button label: 🔊 聆听经文
- Section heading: 逐句解释
- Summary heading: 总结 · Summary
- Portal bar and footer link back to DharmaGate
- Not yet deployed to GitHub Pages

## Explanation card pattern

```html
<div class="explanation-card">
  <p class="line"><strong>Chinese phrase</strong></p>
  <p class="explanation-zh">Short Chinese explanation (2-3 sentences, concept-focused)</p>
  <button class="toggle-btn" onclick="toggleDetail(this)" aria-expanded="false">Details · 详细 ▾</button>
  <div class="detail-content" hidden>
    <p class="translation">English translation (red)</p>
    <p class="explanation">Full English commentary (grey, with analogies)</p>
  </div>
</div>
```

## Summary pattern

```html
<section class="summary">
  <h2>总结 · Summary</h2>
  <p class="summary-zh">Chinese summary</p>
  <button class="toggle-btn" onclick="toggleDetail(this)" aria-expanded="false">English · 英文 ▾</button>
  <div class="detail-content" hidden>
    <p class="explanation">English summary</p>
  </div>
</section>
```

## File structure

```
HeartSutra/
  index.html       <- intro + 3 section cards
  section1.html    <- Opening 序分
  section2.html    <- Main Body 正宗分
  section3.html    <- Mantra 咒语
  css/
    style.css      <- all styles (red/saffron tokens)
  docs/
    readme.md
    architecture.md
    ai-context.md  <- this file
    plan.md
    roadmap.md
```

## Design tokens

| Token | Value | Usage |
|-------|-------|-------|
| `--red` | `#b83232` | Primary accent |
| `--red-light` | `#d44e4e` | Hover states, headings |
| `--saffron` | `#c8820a` | Legacy pinyin colour |
| `--saffron-lt` | `#e09c2a` | Portal bar links |
| `--ink` | `#1c0f0f` | Header/footer backgrounds |
| `--bg` | `#f7f0e6` | Page background |
| `--text` | `#2d1f1f` | Body text, Chinese explanations |
| `--muted` | `#7a6060` | English text, toggle buttons |
| `--border` | `#e0d0c8` | Card borders, dividers |

## Portal link

Portal bar and footer both link to: `https://lugh3456.github.io/DharmaGate/`

## Planned GitHub repo

`https://lugh3456.github.io/HeartSutra/`
