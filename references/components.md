# Component Specs Reference

All measurements in 4pt grid. Values in `pt` (iOS) / `dp` (Android) unless noted.

---

## Button

### Sizes
| Variant | Height | Padding H | Font | Radius |
|---|---|---|---|---|
| Large | 52pt | 24pt | 16pt Medium | 12pt |
| Medium | 44pt | 20pt | 14pt Medium | 10pt |
| Small | 36pt | 16pt | 12pt Medium | 8pt |
| XSmall | 28pt | 12pt | 10pt Medium | 6pt |

### States
- **Default**: Primary color fill
- **Hover/Pressed**: 10–15% darker tint, scale 0.97
- **Disabled**: opacity 0.38 (Material) / 0.3 (HIG), no interaction
- **Loading**: replace label with 20pt spinner, maintain width

### Variants
- **Primary**: filled, high emphasis
- **Secondary/Outlined**: 1.5px border, transparent fill
- **Ghost/Text**: no border, no fill, label only
- **Destructive**: red-600 fill or red-600 text

### Good vs Bad
- ✅ Full-width buttons for single primary action per screen
- ✅ Icon + label for clarity (icon left, 8pt gap)
- ❌ More than 2 button variants on one screen
- ❌ Touch target below 44pt

---

## Input / Text Field

### Sizes
| Variant | Height | Padding H | Padding V | Font |
|---|---|---|---|---|
| Large | 56pt | 16pt | 16pt | 16pt |
| Medium | 48pt | 16pt | 12pt | 14pt |
| Small | 40pt | 12pt | 8pt | 12pt |

### Anatomy
- Label: 12pt Regular, 4pt above field, text-secondary color
- Placeholder: same size as input text, 40% opacity
- Helper text: 12pt, 4pt below field
- Error text: 12pt, red-600, with ⚠️ icon (16pt)
- Border: 1px neutral-300 default, 2px primary on focus, 1px red-600 on error

### States
- Default → Focus → Error → Disabled → Filled

### Good vs Bad
- ✅ Always show label (never placeholder-only)
- ✅ Error + icon + text (never color alone)
- ❌ Placeholder disappears before user types = no label visible
- ❌ Border radius inconsistent with other inputs on same screen

---

## Card

### Sizing
- Width: full column width (screen - 2× margin)
- Min height: 72pt
- Corner radius: 12–16pt
- Padding: 16pt all sides
- Shadow: `0 2px 8px rgba(0,0,0,0.08)`

### Variants
- **Elevated**: white bg + shadow, no border
- **Outlined**: transparent bg + 1px border, no shadow
- **Filled**: neutral-50/100 bg, no border, no shadow

### Internal Spacing
- Image → Title gap: 12pt
- Title → Description gap: 4–8pt
- Description → Actions gap: 16pt
- Between action buttons: 8pt

---

## Navigation Bar (Bottom)

| Property | Value |
|---|---|
| Height | 56pt + safe area bottom |
| Icon size | 24pt |
| Label size | 10–12pt |
| Icon → label gap | 4pt |
| Active color | primary |
| Inactive color | neutral-500 |
| Background | surface / white + blur |
| Border top | 0.5px neutral-200 |

### Tab count
- Minimum 2, maximum 5 items
- 4 items is ideal sweet spot

---

## Tab Bar / Segmented Control

### Tab Bar
- Height: 44pt
- Indicator: 2px underline (sliding animation)
- Label: 14pt Medium
- Padding horizontal per tab: 16pt

### Segment Control
- Height: 36pt
- Background: neutral-100
- Selected: white + shadow or primary bg
- Padding: 4pt vertical, 16pt horizontal
- Corner radius: 8pt container, 6pt selected pill

---

## Toggle / Switch

| Property | iOS | Android |
|---|---|---|
| Width | 51pt | 52dp |
| Height | 31pt | 32dp |
| Thumb size | 27pt | 20dp (off) / 24dp (on) |
| Track radius | 15.5pt | 16dp |
| Animation | spring | Material easing |

### States
- Off: neutral-300 track, white thumb
- On: primary track, white thumb
- Disabled: opacity 0.38

---

## Checkbox

| Property | Value |
|---|---|
| Size | 20×20pt |
| Border | 1.5px, radius 4pt |
| Check icon | 12pt, white |
| Gap to label | 8pt |
| Label font | 14pt Regular |

### States: Unchecked → Checked → Indeterminate → Disabled

---

## Avatar

| Size | Diameter | Font (initials) |
|---|---|---|
| XS | 24pt | 10pt |
| S | 32pt | 12pt |
| M | 40pt | 14pt |
| L | 48pt | 16pt |
| XL | 64pt | 20pt |
| XXL | 80pt | 24pt |

- Always circular (`border-radius: 9999px`)
- Fallback: colored bg + initials (1–2 chars)
- Status indicator: 10pt dot, 2pt white border, bottom-right

---

## Tag / Chip / Badge

| Size | Height | Padding H | Font | Radius |
|---|---|---|---|---|
| Small | 20pt | 8pt | 10pt | 10pt (pill) |
| Medium | 24pt | 10pt | 12pt | 12pt (pill) |
| Large | 28pt | 12pt | 12pt | 14pt (pill) |

### Variants
- **Label only**: minimal, just text
- **With icon**: 16pt icon + 4pt gap + text
- **Dismissible**: text + × (12pt) with 4pt gap

---

## Tooltip

- Max width: 200pt
- Padding: 8pt vertical, 12pt horizontal
- Background: neutral-900
- Text: 12pt Regular, white
- Radius: 6pt
- Arrow: 6pt × 4pt triangle
- Delay: 300ms show, 100ms hide

---

## Snackbar / Toast

| Property | Value |
|---|---|
| Height | 48pt min |
| Margin from edge | 16pt |
| Margin from bottom | 24pt + safe area |
| Padding H | 16pt |
| Padding V | 12pt |
| Radius | 8pt |
| Max width | screen - 32pt |
| Background | neutral-800 |
| Text | 14pt Regular, white |
| Action text | 14pt Medium, primary-300 |
| Duration | 3s (no action) / persistent (with action) |

---

## Progress Indicator

### Circular (Spinner)
| Size | Diameter | Stroke |
|---|---|---|
| Small | 16pt | 2pt |
| Medium | 24pt | 2.5pt |
| Large | 36pt | 3pt |
| XL | 48pt | 4pt |

### Linear (Progress Bar)
- Height: 4pt
- Radius: 2pt (full pill)
- Track: neutral-200
- Fill: primary

---

## Dialog / Modal

- Width: screen width - 48pt (24pt each side)
- Max width: 320pt
- Padding: 24pt
- Radius: 16pt
- Title: 18pt Medium
- Body: 14pt Regular
- Button area: 12pt top padding, right-aligned actions
- Overlay: black at 50% opacity

---

## Bottom Sheet

| State | Position |
|---|---|
| Collapsed | peek height = 0 or partial (120–200pt) |
| Half | 50% screen height |
| Full | 100% - status bar |

- Handle: 4×36pt, neutral-300, radius 2pt, centered, 8pt from top
- Radius: 24pt top corners only
- Padding: 16pt horizontal, 8pt top (after handle)
- Background: surface/white

---

## Empty State

- Icon: 64–80pt illustration or icon
- Heading: 18–20pt Medium
- Description: 14pt Regular, text-secondary, max 2 lines
- CTA button: Medium size, primary
- Vertical centering: center of available space
- Internal stack spacing: 12pt between elements, 24pt before CTA

---

## Navigation Patterns

### Top App Bar
- Height: 56pt
- Leading icon: 24pt, 16pt from edge
- Title: 18–20pt Medium, centered or left
- Trailing actions: 24pt icons, 8pt between, 16pt from edge

### Back navigation
- Always: `←` chevron (24pt) + optional "Back" label (14pt)
- Touch target: 44×44pt minimum

---

## Form Layout

- Label above field: 4–8pt gap
- Field → helper/error: 4pt gap
- Field → next field: 16pt gap
- Section → section: 24–32pt gap
- Submit button: 24pt top margin from last field
- Group related fields with 8pt internal / 20pt external spacing
