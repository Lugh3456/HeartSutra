# Plan — Heart Sutra

## Vision

A clean, bilingual study companion for the Heart Sutra — the most widely recited sutra in Mahayana Buddhism. Designed for beginners (especially bilingual Chinese/English readers in Singapore and Southeast Asia) who want to understand the sutra line by line, at their own pace.

## Goals

1. **Accessible** — Chinese explanations use everyday vocabulary, not literary Buddhist register; English explanations go deeper with analogies a layperson can relate to
2. **Progressive disclosure** — default view is Chinese-only and scannable; English details expand on demand, keeping the page uncluttered
3. **Study-friendly** — each phrase gets its own card so the reader can pause, reflect, and revisit without losing their place
4. **Consistent with the portal** — shares design language (red/saffron tokens, Noto fonts) with The Dharma Gate and sibling scripture sites
5. **Mobile-first** — optimised for phone reading, the most likely study context

## Content Structure

The Heart Sutra is divided into three sections following the traditional Chinese Buddhist division:

| Section | Name | Content |
|---------|------|---------|
| 1. Opening (序分) | Sets the scene | Avalokiteshvara in deep meditation, perceives emptiness, overcomes suffering |
| 2. Main Body (正宗分) | Core teaching | Form is emptiness; dismantles aggregates, senses, dependent origination, Four Noble Truths; liberation through non-grasping |
| 3. Mantra (咒语) | Culmination | Declares the teaching a great mantra; the untranslated Sanskrit mantra as a direct pointing toward awakening |

## Design Decisions

- **Chinese explanations first**: The default collapsed view prioritises Chinese to encourage readers to engage with the Chinese text before reaching for the English
- **No pinyin**: Removed after initial build — it added visual clutter and most bilingual readers in the target audience don't need it
- **Collapsible English**: Keeps pages scannable on mobile; readers who want the full English commentary tap to expand
- **Short Chinese, long English**: Chinese explanations are 2–3 sentences (concept and principle only); English explanations are full paragraphs with analogies and context
- **Bilingual summary**: Each section ends with a Chinese summary (default) and expandable English summary

## Not in scope (for now)

- Audio recordings (currently using Web Speech API as a lightweight alternative)
- Bookmarking or progress tracking
- Commentary from multiple traditions
- Simplified/Traditional Chinese toggle
