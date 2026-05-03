# Color System Reference

## Token Architecture

```
color/
├── primitive/      # Raw hex values — never use directly in components
├── semantic/       # Role-based tokens — use these in components
└── component/      # Component-specific overrides (rare)
```

---

## Primitive Palette

### Neutral Scale
```
neutral-0:   #FFFFFF
neutral-50:  #FAFAFA
neutral-100: #F5F5F5
neutral-200: #E5E5E5
neutral-300: #D4D4D4
neutral-400: #A3A3A3
neutral-500: #737373
neutral-600: #525252
neutral-700: #404040
neutral-800: #262626
neutral-900: #171717
neutral-950: #0A0A0A
```

### Blue (Primary Example)
```
blue-50:  #EFF6FF
blue-100: #DBEAFE
blue-200: #BFDBFE
blue-300: #93C5FD
blue-400: #60A5FA
blue-500: #3B82F6
blue-600: #2563EB  ← recommended primary
blue-700: #1D4ED8
blue-800: #1E40AF
blue-900: #1E3A8A
```

### Red (Destructive / Error)
```
red-50:  #FEF2F2
red-100: #FEE2E2
red-300: #FCA5A5
red-500: #EF4444
red-600: #DC2626  ← error default
red-700: #B91C1C
```

### Green (Success)
```
green-50:  #F0FDF4
green-500: #22C55E
green-600: #16A34A  ← success default
green-700: #15803D
```

### Amber (Warning)
```
amber-50:  #FFFBEB
amber-500: #F59E0B
amber-600: #D97706  ← warning default
amber-700: #B45309
```

---

## Semantic Tokens

### Light Mode
```yaml
# Background
bg-default:    neutral-0
bg-subtle:     neutral-50
bg-elevated:   neutral-0 + shadow
bg-overlay:    neutral-900/50

# Surface
surface-default:  neutral-0
surface-raised:   neutral-50

# Text
text-primary:     neutral-900
text-secondary:   neutral-600
text-tertiary:    neutral-400
text-disabled:    neutral-300
text-inverse:     neutral-0
text-on-primary:  neutral-0

# Border
border-default:   neutral-200
border-strong:    neutral-400
border-focus:     primary-600

# Interactive
interactive-primary:          primary-600
interactive-primary-hover:    primary-700
interactive-primary-pressed:  primary-800
interactive-primary-disabled: primary-600/38%

# Semantic States
state-error:    red-600
state-success:  green-600
state-warning:  amber-600
state-info:     blue-500
```

### Dark Mode
```yaml
bg-default:    neutral-950
bg-subtle:     neutral-900
surface-default: neutral-900
surface-raised:  neutral-800

text-primary:    neutral-50
text-secondary:  neutral-400
text-tertiary:   neutral-600
text-disabled:   neutral-700

border-default:  neutral-800
border-strong:   neutral-600

interactive-primary: primary-500  # lighter in dark mode
```

---

## Contrast Requirements (WCAG)

| Text Type | Minimum Ratio | Target |
|---|---|---|
| Body text | 4.5:1 | 7:1 |
| Large text (≥18pt bold or ≥24pt regular) | 3:1 | 4.5:1 |
| UI components & icons | 3:1 | 4.5:1 |
| Decorative / disabled | No requirement | — |

### Quick contrast check
- `neutral-900` on `neutral-0` = 19.1:1 ✅
- `neutral-600` on `neutral-0` = 5.9:1 ✅
- `neutral-400` on `neutral-0` = 2.9:1 ❌ (fail for body)
- `blue-600` on `neutral-0` = 4.5:1 ✅ (exactly AA)
- `blue-500` on `neutral-0` = 3.1:1 ❌ (fail for body, pass for large)

---

## Color Usage Patterns

### Never use color alone for state
- ❌ Red border = error (colorblind users can't see it)
- ✅ Red border + error icon + error message

### Opacity for states (Material Design)
| State | Opacity modifier |
|---|---|
| Hover | +8% primary overlay |
| Pressed/Active | +12% primary overlay |
| Focused | +12% primary overlay |
| Dragged | +16% primary overlay |
| Disabled | 38% opacity total |

### Elevation shadows (Light Mode)
```
Level 0: no shadow
Level 1: 0 1px 3px rgba(0,0,0,0.08), 0 1px 2px rgba(0,0,0,0.06)
Level 2: 0 4px 8px rgba(0,0,0,0.08), 0 2px 4px rgba(0,0,0,0.06)
Level 3: 0 8px 16px rgba(0,0,0,0.10), 0 4px 8px rgba(0,0,0,0.06)
Level 4: 0 16px 32px rgba(0,0,0,0.12), 0 8px 16px rgba(0,0,0,0.08)
```

---

## iOS System Colors (Reference)

```swift
// Always adapt to light/dark automatically
Color.primary         // #000000 / #FFFFFF
Color.secondary       // #8E8E93 / #8E8E93
Color.systemBackground // #FFFFFF / #1C1C1E
Color.secondarySystemBackground // #F2F2F7 / #2C2C2E
Color.systemBlue      // #007AFF
Color.systemRed       // #FF3B30
Color.systemGreen     // #34C759
Color.systemOrange    // #FF9500
Color.systemYellow    // #FFCC00
Color.label           // dynamic text color
Color.secondaryLabel  // 60% opacity label
Color.tertiaryLabel   // 30% opacity label
```

## Material Design 3 Color Roles (Reference)

```kotlin
// MaterialTheme.colorScheme.*
primary, onPrimary, primaryContainer, onPrimaryContainer
secondary, onSecondary, secondaryContainer, onSecondaryContainer
error, onError, errorContainer, onErrorContainer
background, onBackground
surface, onSurface, surfaceVariant, onSurfaceVariant
outline, outlineVariant
scrim
```
