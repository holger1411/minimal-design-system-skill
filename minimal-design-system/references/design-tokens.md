# Design Tokens & Guidelines

This document defines the core design tokens for the minimal design system v2.0, inspired by shadcn/ui's token structure while maintaining generous whitespace and simplicity.

## Color System (HSL-based)

The design system uses HSL color values for flexibility and easy theming. Colors are defined as CSS custom properties without the `hsl()` wrapper, allowing for opacity modifiers.

### Usage Pattern

```css
/* Define without hsl() wrapper */
--primary: 240 5.9% 10%;

/* Use with hsl() */
background-color: hsl(var(--primary));

/* Use with opacity */
background-color: hsl(var(--primary) / 0.5);
```

### Semantic Color Tokens

| Token | Purpose | Light Mode | Dark Mode |
|-------|---------|------------|-----------|
| `--background` | Page background | `0 0% 100%` | `240 10% 3.9%` |
| `--foreground` | Primary text | `240 10% 3.9%` | `0 0% 98%` |
| `--card` | Card backgrounds | `0 0% 100%` | `240 10% 3.9%` |
| `--card-foreground` | Card text | `240 10% 3.9%` | `0 0% 98%` |
| `--primary` | Primary actions, buttons | `240 5.9% 10%` | `0 0% 98%` |
| `--primary-foreground` | Text on primary | `0 0% 98%` | `240 5.9% 10%` |
| `--secondary` | Secondary backgrounds | `240 4.8% 95.9%` | `240 3.7% 15.9%` |
| `--secondary-foreground` | Text on secondary | `240 5.9% 10%` | `0 0% 98%` |
| `--muted` | Muted backgrounds | `240 4.8% 95.9%` | `240 3.7% 15.9%` |
| `--muted-foreground` | Muted/secondary text | `240 3.8% 46.1%` | `240 5% 64.9%` |
| `--accent` | Hover states, highlights | `240 4.8% 95.9%` | `240 3.7% 15.9%` |
| `--accent-foreground` | Text on accent | `240 5.9% 10%` | `0 0% 98%` |
| `--border` | Borders, dividers | `240 5.9% 90%` | `240 3.7% 15.9%` |
| `--input` | Input borders | `240 5.9% 90%` | `240 3.7% 15.9%` |
| `--ring` | Focus rings | `240 5.9% 10%` | `240 4.9% 83.9%` |

### Status Colors

For badges, alerts, and semantic feedback:

| Status | Background | Text | Border |
|--------|------------|------|--------|
| **Success** | `142 76% 36% / 0.1` | `142 76% 36%` | `142 76% 36% / 0.2` |
| **Info** | `221 83% 53% / 0.1` | `221 83% 53%` | `221 83% 53% / 0.2` |
| **Warning** | `38 92% 50% / 0.1` | `38 92% 50%` | `38 92% 50% / 0.2` |
| **Error** | `0 84% 60% / 0.1` | `0 84% 60%` | `0 84% 60% / 0.2` |

### Complete CSS Variables Block

```css
:root {
  /* Semantic Colors - Light Mode */
  --background: 0 0% 100%;
  --foreground: 240 10% 3.9%;
  --card: 0 0% 100%;
  --card-foreground: 240 10% 3.9%;
  --primary: 240 5.9% 10%;
  --primary-foreground: 0 0% 98%;
  --secondary: 240 4.8% 95.9%;
  --secondary-foreground: 240 5.9% 10%;
  --muted: 240 4.8% 95.9%;
  --muted-foreground: 240 3.8% 46.1%;
  --accent: 240 4.8% 95.9%;
  --accent-foreground: 240 5.9% 10%;
  --border: 240 5.9% 90%;
  --input: 240 5.9% 90%;
  --ring: 240 5.9% 10%;
  
  /* Border Radius */
  --radius: 0.5rem;
}

@media (prefers-color-scheme: dark) {
  :root {
    --background: 240 10% 3.9%;
    --foreground: 0 0% 98%;
    --card: 240 10% 3.9%;
    --card-foreground: 0 0% 98%;
    --primary: 0 0% 98%;
    --primary-foreground: 240 5.9% 10%;
    --secondary: 240 3.7% 15.9%;
    --secondary-foreground: 0 0% 98%;
    --muted: 240 3.7% 15.9%;
    --muted-foreground: 240 5% 64.9%;
    --accent: 240 3.7% 15.9%;
    --accent-foreground: 0 0% 98%;
    --border: 240 3.7% 15.9%;
    --input: 240 3.7% 15.9%;
    --ring: 240 4.9% 83.9%;
  }
}
```

### Contrast Ratios (WCAG Compliance)

**Light Mode:**
- Foreground on Background: 21:1 (AAA) ✓
- Muted-foreground on Background: 4.6:1 (AA) ✓

**Dark Mode:**
- Foreground on Background: 21:1 (AAA) ✓
- Muted-foreground on Background: 7.5:1 (AA+) ✓

## Typography

### Font Family

```css
font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
```

### Font Sizes (Tailwind)

| Class | Size | Usage |
|-------|------|-------|
| `text-xs` | 12px | Avoid for body (accessibility) |
| `text-sm` | 14px | Secondary text, badges, metadata |
| `text-base` | 16px | Body text (default) |
| `text-lg` | 18px | Lead paragraphs |
| `text-xl` | 20px | Section titles |
| `text-2xl` | 24px | h3, card titles |
| `text-3xl` | 30px | h2 |
| `text-4xl` | 36px | h1 |
| `text-5xl` | 48px | Hero headlines |

### Font Weights

| Weight | Class | Usage |
|--------|-------|-------|
| 400 | `font-normal` | Body text |
| 500 | `font-medium` | Buttons, labels |
| 600 | `font-semibold` | Headings, emphasis |
| 700 | `font-bold` | Hero headlines |

### Tracking (Letter Spacing)

Use `tracking-tight` (-0.025em) for headings to achieve a modern, polished look.

```html
<h1 class="text-4xl font-bold tracking-tight">Headline</h1>
```

### Line Heights

| Class | Value | Usage |
|-------|-------|-------|
| `leading-tight` | 1.25 | Headings |
| `leading-normal` | 1.5 | Body text |
| `leading-relaxed` | 1.75 | Long-form content |

## Spacing Scale

Generous whitespace is core to this design system. Use large gaps between sections.

### Recommended Section Spacing

| Context | Tailwind Class | Value |
|---------|---------------|-------|
| Between major sections | `py-16` or `py-24` | 64px / 96px |
| Within sections | `space-y-8` | 32px |
| Between cards/items | `space-y-4` | 16px |
| Between elements | `space-y-2` | 8px |

### Layout Widths

| Purpose | Class | Width |
|---------|-------|-------|
| Max content width | `max-w-4xl` | 896px |
| Wide layouts | `max-w-6xl` | 1152px |
| Reading text | `max-w-2xl` | 672px |
| Prose/articles | `max-w-prose` | 65ch |

### Padding

| Context | Class | Value |
|---------|-------|-------|
| Page horizontal | `px-6` | 24px |
| Card internal | `p-6` | 24px |
| Button horizontal | `px-4` to `px-8` | 16-32px |

## Border Radius

Use the `--radius` CSS variable for consistency:

| Element | Tailwind | CSS |
|---------|----------|-----|
| Buttons, inputs | `rounded-md` | `calc(var(--radius) - 2px)` |
| Cards, containers | `rounded-lg` | `var(--radius)` |
| Large cards | `rounded-xl` | `calc(var(--radius) + 4px)` |
| Badges, pills | `rounded-full` | `9999px` |

## Shadows

Minimal shadows, used sparingly for elevation:

```css
/* Card hover state */
.card:hover {
  box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1);
}

/* Elevated elements */
.elevated {
  box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1);
}
```

## Focus States

All interactive elements must have visible focus indicators:

```css
button:focus-visible,
a:focus-visible,
input:focus-visible,
textarea:focus-visible,
select:focus-visible {
  outline: 2px solid hsl(var(--ring));
  outline-offset: 2px;
}
```

## Touch Target Sizes

WCAG 2.5.5 compliant minimum sizes:

| Size | Height | Usage |
|------|--------|-------|
| Small | `h-9` (36px) | Compact UI, badges |
| Default | `h-10` (40px) | Standard buttons |
| Large | `h-11` (44px) | Primary CTAs, mobile |

**Note:** 44px is the WCAG AAA minimum. Always prefer `h-11` for important actions.

## Screen Reader Utilities

```css
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border-width: 0;
}
```

## Design Principles

1. **Generous Whitespace**: Large gaps (py-16, py-24) between sections
2. **Clear Hierarchy**: Font size and weight, not color variations
3. **Semantic Colors**: Use token names (`primary`, `muted`) not raw values
4. **Subtle Accents**: Muted colors for secondary elements
5. **Minimal Borders**: Prefer whitespace over dividers
6. **Readable Lines**: Max 65-75 characters (max-w-2xl or max-w-prose)
7. **Accessibility First**: WCAG AA minimum, prefer AAA
8. **Touch-Friendly**: 44px minimum touch targets
9. **Keyboard Navigation**: Visible focus states always
10. **Consistent Patterns**: Same design language across all pages

## Migration from v1.x

### Color Token Mapping

| Old (v1.x) | New (v2.0) |
|------------|------------|
| `--color-bg` | `--background` |
| `--color-fg` | `--foreground` |
| `--color-muted` | `--muted-foreground` |
| `--color-border` | `--border` |
| `--color-subtle-bg` | `--secondary` or `--muted` |
| `--color-hover-bg` | `--accent` |

### Usage Migration

```html
<!-- Old -->
<p class="text-[var(--color-muted)]">Text</p>
<div class="bg-[var(--color-subtle-bg)]">Card</div>

<!-- New -->
<p class="text-[hsl(var(--muted-foreground))]">Text</p>
<div class="bg-[hsl(var(--secondary))]">Card</div>
```

## Accessibility Checklist

- [ ] Color contrast meets 4.5:1 for normal text, 3:1 for large text (≥18px)
- [ ] Focus visible indicators (2px outline with offset)
- [ ] Touch targets ≥44px (`h-11`)
- [ ] Text sized ≥14px for body content (prefer 16px)
- [ ] Semantic HTML structure
- [ ] Aria labels for icon-only buttons
- [ ] Aria-hidden on decorative SVGs
- [ ] Table captions (can be .sr-only)
- [ ] Proper heading hierarchy (h1 → h2 → h3, no skipping)
- [ ] Skip links for keyboard navigation
