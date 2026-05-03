# Typography Reference

## Full Type Scale

| Token | Size | Line Height | Letter Spacing | Weight | Use Case |
|---|---|---|---|---|---|
| `heading-4xl` | 32pt | 40pt | -2% | Medium 500 | Hero headers, splash screens |
| `heading-3xl` | 28pt | 36pt | -2% | Medium 500 | Section headers |
| `heading-2xl` | 24pt | 32pt | -2% | Medium 500 | Page titles |
| `heading-xl` | 20pt | 28pt | -1% | Medium 500 | Card titles, modal headers |
| `heading-lg` | 18pt | 26pt | -1% | Medium 500 | Subheadings |
| `heading-md` | 16pt | 24pt | -1% | Medium 500 | List item titles |
| `heading-sm` | 14pt | 20pt | -1% | Medium 500 | Small headings, overlines |
| `heading-xs` | 12pt | 16pt | 0% | Medium 500 | Tags, chip labels |
| `heading-xxs` | 10pt | 14pt | 0% | Medium 500 | Navigation/menu labels |
| `body-lg` | 16pt | 24pt | 0–0.5% | Regular 400 | Primary body text |
| `body-md` | 14pt | 20pt | 0–0.5% | Regular 400 | Secondary body text |
| `body-sm` | 12pt | 16pt | 1% | Regular 400 | Captions, helper text |

---

## Platform Specifics

### iOS (Human Interface Guidelines)
- System font: **SF Pro** (San Francisco)
- Dynamic Type: support all 11 text styles (`largeTitle`, `title1`…`caption2`)
- Line height: ≈ 1.3× font size
- Minimum body text: **17pt** (system default)
- Example specs:
  - Body (17pt) → line height 22pt
  - Subhead (15pt) → line height 20pt
  - Caption 1 (12pt) → line height 16pt

### Android (Material Design 3)
- System font: **Roboto** (default), or **Google Sans**
- Units: `sp` for text (scales with user preferences), `dp` for everything else
- Line height system: 4pt increments
- Example specs:
  - Body Large (16sp) → line height 24dp, letter spacing 0.005em
  - Body Medium (14sp) → line height 20dp, letter spacing 0.01em
  - Caption (12sp) → line height 16dp, letter spacing 0.02em

### Cross-Platform (React Native / Flutter)
- Use `sp` units mapped to CSS `rem` equivalent
- React Native: `fontSize` in the StyleSheet is in dp on Android, pt on iOS
- Flutter: `TextStyle(fontSize: 16, height: 1.5)` — `height` is multiplier

---

## Letter Spacing Rules

| Font Size Range | Adjustment | Reason |
|---|---|---|
| 10–14pt | +0.5% to +1% | Prevent character blending on small screens |
| 16–20pt | 0% (default) | No adjustment needed |
| 24pt+ | -0.5% to -2% | Maintain visual compactness for headings |

### Platform letter-spacing units
- **Figma**: use `%` (percentage) — most portable across export
- **CSS**: use `em` (e.g., `letter-spacing: 0.01em`)
- **iOS**: `NSAttributedString` kern values (points)
- **Android**: `letterSpacing` attribute in `sp`-relative floats

---

## Font Weight Naming

| Numeric | CSS Name | Usage |
|---|---|---|
| 300 | Light | Decorative only, never body |
| 400 | Regular | Body text, descriptions |
| 500 | Medium | Headings, labels, buttons |
| 600 | SemiBold | Strong emphasis |
| 700 | Bold | CTAs, critical alerts |

---

## Accessibility

- Minimum touch target for text links: 44pt height
- Never use `font-weight: 100` or `200` on mobile
- Avoid ALL CAPS for body text (reduces legibility ~12%)
- Ensure Dynamic Type support on iOS (use `UIFontMetrics`)
- On Android: respect `fontScale` in `Configuration`

---

## Recommended Font Pairings

| Primary (Headings) | Secondary (Body) | Vibe |
|---|---|---|
| Inter | Inter | Clean, modern SaaS |
| Poppins | DM Sans | Friendly, consumer app |
| Sora | Nunito | Rounded, playful |
| Plus Jakarta Sans | Outfit | Premium, contemporary |
| SF Pro (iOS only) | SF Pro | Native iOS |
| Google Sans | Roboto | Native Android |
