# pixel-perfect-mobile

> A Claude skill that turns any AI tool into a senior mobile UI designer.

Drop this skill into Claude and get **production-ready component specs, design tokens, and code** — auto-formatted for Claude, GPT, Gemini, Cursor, VS Code, Claude Code, OpenCode, Manus, Antigravity, and more.

---

## What it does

Ask Claude anything about mobile UI — it responds with exact values, not guesses.

```
You:    spec me a button component, all sizes and states
Claude: [returns height, padding, radius, font, disabled opacity,
         touch target, pressed scale — in your platform's format]
```

No more googling "what line-height for mobile". No more inconsistent spacing. No more "it looks off but I don't know why."

---

## File Structure

```
pixel-perfect-mobile/
├── SKILL.md                  ← install this; triggers + routing logic
└── references/
    ├── typography.md         ← 12-level type scale, iOS HIG + Material D3
    ├── components.md         ← 25+ components with full px/pt/dp specs
    └── colors.md             ← token system, contrast rules, dark mode
```

---

## What's Inside

### Design Tokens
- **4pt grid system** — all spacing multiples of 4, compatible with 8pt grids
- **Color system** — primitive palette + semantic roles + dark mode mapping
- **Shadow levels** — 5 elevation tiers with exact rgba values
- **Border radius scale** — sm (4px) → full (9999px)
- Output formats: CSS variables, Tailwind config, React Native StyleSheet, Swift, Kotlin

### Typography
- 12-level scale from 10pt (menu labels) to 32pt (hero headings)
- Exact line heights and letter spacing per size
- iOS HIG values (SF Pro, Dynamic Type)
- Material Design 3 values (sp/dp units)
- Font pairing recommendations

### Component Specs (25+)
Button · Input · Search · Checkbox · Toggle · Avatar · Tag/Chip ·  
Card · Item List · Accordion · Navigation Bar · Tab Bar · Tab ·  
Segment Control · Tooltip · Snackbar · Progress Bar · Spinner ·  
Dialog · Bottom Sheet · Popover · Banner · Form · Empty State ·  
Message Card · Onboarding

Every component includes: sizes, states, internal spacing, variants, accessibility notes, good vs bad patterns.

### Platform Routing
| Tool | Output Format |
|---|---|
| Claude / Claude Code | Markdown spec + React Native |
| ChatGPT / GPT-4o | JSON tokens + JSX |
| Gemini / Gemini 2.5 Pro | Jetpack Compose + Material You |
| Cursor | TypeScript + Tailwind classes |
| VS Code + Copilot | TypeScript + CSS variables |
| OpenCode | Platform-agnostic spec |
| Manus | Step-by-step action plan + code |
| Antigravity | Markdown spec + CSS variables |

---

## Install

**1. Clone**
```bash
git clone https://github.com/your-handle/pixel-perfect-mobile
```

**2. Move to Claude skills folder**
```bash
mv pixel-perfect-mobile ~/.claude/skills/
```

**3. Done.** Reload Claude. The skill auto-triggers — no command needed.

---

## Example Prompts

```
spec me a card component for a food delivery app
```
```
give me a full typography scale for an iOS app, Material Design format
```
```
what's the correct touch target size for buttons? show good vs bad
```
```
generate Tailwind tokens for a 4pt spacing system
```
```
design a bottom sheet component with all states
```
```
critique this UI: nav bar 40px height, body text 11px, border radius 3px
```

---

## Good vs Bad (Preview)

| ❌ Bad | ✅ Good |
|---|---|
| Body text at 11pt | Body text 14–16pt |
| Touch target 32×32pt | Touch target ≥ 44×44pt |
| Color alone for error state | Red + icon + error message |
| Line height 1.0× font size | Line height 1.4–1.6× for body |
| Inconsistent border radii | Same radius token across siblings |
| Disabled at opacity 0.6 | Disabled at opacity 0.38 (Material) |

---

## Built From

Real-world mobile UI principles: iOS Human Interface Guidelines, Material Design 3, and production design system patterns. No AI hallucinations — every value is sourced and testable.

---

## License

MIT — free to use, modify, and distribute.

---

## Contributing

PRs welcome. If you add a new component spec, follow the format in `references/components.md`. Keep all values on the 4pt grid.
