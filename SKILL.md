---
name: pixel-perfect-mobile
description: >
  Mobile UI design system for production-ready component specs, design tokens, and code.
  Works with Claude, GPT, Gemini, Cursor, VS Code, Claude Code, OpenCode, Manus, and more.
  Use for: component specs (button, card, input, nav, toggle, snackbar), design tokens
  (colors, spacing, radius, typography), iOS HIG / Material Design 3 rules, Figma specs,
  Tailwind / SwiftUI / Jetpack Compose / React Native code, UI critique, or building a
  full mobile design system from scratch. Triggers on: "pixel perfect", "mobile component",
  "design system", "UI tokens", "8pt grid", "4pt grid", "component spec", "what size should X be".
---

# Pixel-Perfect Mobile UI Skill

A complete, opinionated mobile UI design system distilled from real-world best practices.
Use this skill to generate accurate, production-grade specs, tokens, and code for mobile apps.

---

## Core Philosophy

**4pt Grid System** — all spacing, sizing, and layout values are multiples of 4.
Gives finer control than 8pt for compact mobile canvases while staying compatible with 8pt grids.

```
4 | 8 | 12 | 16 | 20 | 24 | 28 | 32 | 36 | 40 | 48 | 56 | 64
```

**Hard Grid for structure. Soft Grid for flow.**
- Hard grid: all containers, cards, navigation snap to exact multiples
- Soft grid: body text, captions, decorative elements may deviate slightly for visual balance

---

## Typography System

See `references/typography.md` for full scale and platform details.

### Quick Reference

| Role | Size | Line Height | Letter Spacing | Weight |
|---|---|---|---|---|
| Headline XL | 32pt | 40pt | -2% | Medium |
| Headline L | 28pt | 36pt | -2% | Medium |
| Headline M | 24pt | 32pt | -2% | Medium |
| Headline S | 20pt | 28pt | -1% | Medium |
| Subheading | 18pt | 26pt | -1% | Medium |
| Body L | 16pt | 24pt | 0–0.5% | Regular |
| Body M | 14pt | 20pt | 0–0.5% | Regular |
| Caption | 12pt | 16pt | 1% | Regular |
| Menu Label | 10–12pt | 14pt | 0% | Medium |

**iOS baseline:** line-height ≈ 1.3× font size  
**Material Design:** 4pt increments, dp units (Body 16dp → 24dp line height)

---

## Color System

See `references/colors.md` for token naming and dark mode mapping.

### Minimum Contrast Requirements
- Body text on background: **≥ 4.5:1** (WCAG AA)
- Large text / headings: **≥ 3:1**
- Interactive elements: **≥ 3:1**

### Token Structure
```
color/
  primary/default, hover, pressed, disabled
  neutral/0(white)…900(black)
  semantic/success, warning, error, info
  surface/default, elevated, overlay
  text/primary, secondary, disabled, inverse
```

---

## Spacing & Layout

### Grid Setup (Figma)
```
Frame: 375×812 (iOS) | 360×800 (Android)
Columns: 4
Gutter: 12px
Margin: 16px
Base unit: 8px vertical
```

### Margin Patterns
| Layout | Side Padding |
|---|---|
| Single-column (minimal) | 16px |
| Dual-column (complex) | 6–12px outer, 16px inner |
| Cards in a list | 16px from screen edge |
| Full-bleed images | 0px |

---

## Component Library

See `references/components.md` for specs of all 25+ components.

### Component Quick Index
`Icon` `Avatar` `Tag` `Button` `Input` `Search` `Checkbox` `Toggle`
`Navigation Bar` `Tab Bar` `Tab` `Segment Control` `Tooltip` `Snackbar`
`Progress Indicator` `Progress Bar` `Card` `Item List` `Accordion`
`Empty State` `Form` `Banner` `Dialog` `Popover` `Bottom Sheet`
`Message Card` `Onboarding`

---

## Platform Output Formats

When generating specs or code, match platform to format:

| AI Tool / Platform | Output Format |
|---|---|
| Claude / Claude Code | Markdown spec + React Native / Swift snippet |
| GPT / ChatGPT | Structured JSON tokens + JSX |
| Gemini / Gemini models | Kotlin Compose + Material You tokens |
| Cursor / VS Code | TypeScript component + Tailwind classes |
| OpenCode | Plain spec + platform-agnostic tokens |
| Manus | Step-by-step action plan + code blocks |
| Antigravity / other | Markdown spec + CSS variables |
| Figma (design) | Auto Layout specs + component variant table |

---

## Code Token Templates

### CSS Custom Properties
```css
:root {
  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-8: 32px;
  --space-10: 40px;

  /* Typography */
  --text-xs: 10px;
  --text-sm: 12px;
  --text-base: 14px;
  --text-md: 16px;
  --text-lg: 18px;
  --text-xl: 20px;
  --text-2xl: 24px;
  --text-3xl: 28px;
  --text-4xl: 32px;

  /* Radius */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-xl: 16px;
  --radius-2xl: 24px;
  --radius-full: 9999px;
}
```

### Tailwind Config Extension
```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      spacing: { 1: '4px', 2: '8px', 3: '12px', 4: '16px', 5: '20px', 6: '24px', 8: '32px', 10: '40px' },
      fontSize: {
        'xs': ['10px', { lineHeight: '14px' }],
        'sm': ['12px', { lineHeight: '16px' }],
        'base': ['14px', { lineHeight: '20px' }],
        'md': ['16px', { lineHeight: '24px' }],
        'lg': ['18px', { lineHeight: '26px' }],
        'xl': ['20px', { lineHeight: '28px' }],
        '2xl': ['24px', { lineHeight: '32px' }],
        '3xl': ['28px', { lineHeight: '36px' }],
        '4xl': ['32px', { lineHeight: '40px' }],
      },
      borderRadius: {
        'sm': '4px', DEFAULT: '8px', 'lg': '12px',
        'xl': '16px', '2xl': '24px', 'full': '9999px',
      },
    },
  },
}
```

### React Native StyleSheet Tokens
```ts
// tokens.ts
export const spacing = { xs: 4, sm: 8, md: 12, base: 16, lg: 20, xl: 24, '2xl': 32, '3xl': 40 } as const;
export const fontSize = { xs: 10, sm: 12, base: 14, md: 16, lg: 18, xl: 20, '2xl': 24, '3xl': 28, '4xl': 32 } as const;
export const lineHeight = { xs: 14, sm: 16, base: 20, md: 24, lg: 26, xl: 28, '2xl': 32, '3xl': 36, '4xl': 40 } as const;
export const radius = { sm: 4, md: 8, lg: 12, xl: 16, '2xl': 24, full: 9999 } as const;
```

---

## Good vs Bad Patterns

**❌ Bad:**
- Font sizes below 12pt for any readable content
- Line heights below 1.2× font size
- Touch targets smaller than 44×44pt (iOS) / 48×48dp (Android)
- Less than 8px spacing between interactive elements
- Text-on-image without overlay (contrast failure)
- Inconsistent border radii across sibling components

**✅ Good:**
- All touch targets ≥ 44pt × 44pt
- Body text 14–16pt with 1.4–1.6× line height
- Consistent 4pt-grid spacing throughout
- Color contrast ≥ 4.5:1 for body, ≥ 3:1 for large text
- Disabled states use opacity 0.38 (Material) or 0.3 (HIG)
- Error states: red + icon + text (never color alone)

---

## How to Use This Skill

1. **User asks for a component** → read `references/components.md` for that component's full spec
2. **User asks for tokens / design system** → use the CSS/Tailwind/RN templates above
3. **User asks for typography** → read `references/typography.md`
4. **User asks for good vs bad critique** → apply Good vs Bad Patterns above
5. **User asks for platform-specific output** → match Platform Output Formats table
6. **User asks for a full app design system** → combine typography + color + spacing tokens into one output
