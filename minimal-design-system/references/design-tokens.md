# Design Tokens & Guidelines

This document defines the core design tokens for the minimal black/white design system.

## Color System

### Base Colors - Light Mode
```css
--color-bg: #ffffff;
--color-fg: #000000;
--color-muted: #525252;      /* Updated: gray-600 for better contrast (WCAG AA) */
--color-border: #e5e7eb;
--color-subtle-bg: #f9fafb;
--color-hover-bg: #f3f4f6;
```

**Contrast Ratios (Light Mode):**
- Foreground (#000000) on Background (#ffffff): 21:1 (AAA) ✓
- Muted (#525252) on Background (#ffffff): 7:1 (AA) ✓

### Base Colors - Dark Mode
```css
--color-bg: #000000;
--color-fg: #ffffff;
--color-muted: #a3a3a3;      /* Updated: gray-400 for better contrast (WCAG AA) */
--color-border: #1f2937;
--color-subtle-bg: #111111;
--color-hover-bg: #1a1a1a;
```

**Contrast Ratios (Dark Mode):**
- Foreground (#ffffff) on Background (#000000): 21:1 (AAA) ✓
- Muted (#a3a3a3) on Background (#000000): 8.7:1 (AA+) ✓

### Semantic Colors (5-Color System)

The design system uses a complete 5-color semantic system across all components (badges, alerts, etc.):

#### Success (Green)
- Light Mode:
  - Background: `bg-green-50` (#f0fdf4)
  - Border: `border-green-200` (#bbf7d0)
  - Text: `text-green-800` (#166534)
  - Badge: `bg-green-100 text-green-800` (#dcfce7)
- Dark Mode:
  - Background: `bg-green-950` (#052e16)
  - Border: `border-green-900` (#14532d)
  - Text: `text-green-200` (#bbf7d0)
  - Badge: `bg-green-900 text-green-200` (#14532d)
- Usage: Success messages, confirmations, positive states, completed actions

#### Info (Blue)
- Light Mode:
  - Background: `bg-blue-50` (#eff6ff)
  - Border: `border-blue-200` (#bfdbfe)
  - Text: `text-blue-800` (#1e40af)
  - Badge: `bg-blue-100 text-blue-800` (#dbeafe)
- Dark Mode:
  - Background: `bg-blue-950` (#172554)
  - Border: `border-blue-900` (#1e3a8a)
  - Text: `text-blue-200` (#bfdbfe)
  - Badge: `bg-blue-900 text-blue-200` (#1e3a8a)
- Usage: Informational messages, tips, helpful context, FYI notices

#### Warning (Yellow)
- Light Mode:
  - Background: `bg-yellow-50` (#fefce8)
  - Border: `border-yellow-200` (#fef08a)
  - Text: `text-yellow-800` (#854d0e)
  - Badge: `bg-yellow-100 text-yellow-800` (#fef3c7)
- Dark Mode:
  - Background: `bg-yellow-950` (#422006)
  - Border: `border-yellow-900` (#713f12)
  - Text: `text-yellow-200` (#fef08a)
  - Badge: `bg-yellow-900 text-yellow-200` (#713f12)
- Usage: Warnings, cautions, important notices, review required

#### Error (Red)
- Light Mode:
  - Background: `bg-red-50` (#fef2f2)
  - Border: `border-red-200` (#fecaca)
  - Text: `text-red-800` (#991b1b)
  - Badge: `bg-red-100 text-red-800` (#fee2e2)
- Dark Mode:
  - Background: `bg-red-950` (#450a0a)
  - Border: `border-red-900` (#7f1d1d)
  - Text: `text-red-200` (#fecaca)
  - Badge: `bg-red-900 text-red-200` (#7f1d1d)
- Usage: Errors, destructive actions, critical alerts, failures

#### Neutral (Gray)
- Light Mode:
  - Background: `bg-gray-50` (#f9fafb)
  - Border: `border-gray-200` (#e5e7eb)
  - Text: `text-gray-800` (#1f2937)
  - Badge: `bg-gray-100 text-gray-800` (#f3f4f6)
- Dark Mode:
  - Background: `bg-gray-950` (#030712)
  - Border: `border-gray-900` (#111827)
  - Text: `text-gray-200` (#e5e7eb)
  - Badge: `bg-gray-800 text-gray-200` (#1f2937)
- Usage: Neutral information, inactive states, default notifications

## Typography

### Font Family
- Primary: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif
- Monospace: 'Monaco', 'Courier New', monospace

### Font Sizes (Tailwind equivalents)
- xs: 0.75rem / 12px (avoid for body text - accessibility concern)
- sm: 0.875rem / 14px (minimum for body text, good for footnotes)
- base: 1rem / 16px (default body text)
- lg: 1.125rem / 18px (lead paragraphs, large text threshold for contrast)
- xl: 1.25rem / 20px
- 2xl: 1.5rem / 24px (blockquotes, emphasized text)
- 3xl: 1.875rem / 30px
- 4xl: 2.25rem / 36px (h1)
- 5xl: 3rem / 48px (hero h1)

**Accessibility Note**: Text ≥18px (text-lg) or ≥14px bold requires 3:1 contrast ratio. Text <18px requires 4.5:1 contrast ratio (WCAG AA).

### Font Weights
- normal: 400
- medium: 500
- semibold: 600
- bold: 700

### Line Heights
- tight: 1.25 (headings)
- normal: 1.5 (body text)
- relaxed: 1.75 (long-form content)

## Spacing Scale

Use Tailwind's standard spacing scale (1 unit = 0.25rem / 4px):
- 1: 0.25rem / 4px
- 2: 0.5rem / 8px
- 3: 0.75rem / 12px
- 4: 1rem / 16px
- 6: 1.5rem / 24px
- 8: 2rem / 32px
- 12: 3rem / 48px
- 16: 4rem / 64px
- 24: 6rem / 96px
- 32: 8rem / 128px

## Border Radius

- none: 0
- sm: 0.125rem / 2px
- DEFAULT: 0.25rem / 4px
- md: 0.375rem / 6px (standard buttons)
- lg: 0.5rem / 8px
- xl: 0.75rem / 12px
- full: 9999px (pill-style buttons)

## Shadows

Light mode:
- sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05)
- DEFAULT: 0 1px 3px 0 rgba(0, 0, 0, 0.1)
- md: 0 4px 6px -1px rgba(0, 0, 0, 0.1)
- lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1)

Dark mode:
- sm: 0 1px 2px 0 rgba(255, 255, 255, 0.05)
- DEFAULT: 0 1px 3px 0 rgba(255, 255, 255, 0.1)
- md: 0 4px 6px -1px rgba(255, 255, 255, 0.1)
- lg: 0 10px 15px -3px rgba(255, 255, 255, 0.1)

## Focus States (Accessibility)

All interactive elements (buttons, links, inputs) must have visible focus indicators:

```css
button:focus-visible,
a:focus-visible,
input:focus-visible,
textarea:focus-visible,
select:focus-visible {
  outline: 2px solid var(--color-fg);
  outline-offset: 2px;
}
```

**Why**: WCAG 2.1 Success Criterion 2.4.7 (Focus Visible) Level AA requires keyboard focus to be visible.

## Touch Target Sizes (Mobile Usability)

Minimum touch target sizes per WCAG 2.5.5 (Level AAA):
- Minimum: 44x44px
- Recommended: 48x48px or larger

**Button Sizing:**
```
Small:   px-5 py-2.5 text-sm  → ~44px height ✓
Default: px-6 py-3            → ~48px height ✓
Large:   px-8 py-4 text-lg    → ~56px height ✓
```

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

Use for:
- Table captions that should be announced but not visible
- Icon button labels
- Skip links
- Additional context for screen readers

## Design Principles

1. **Generous Whitespace**: Use large gaps (8, 12, 16, 24) between sections
2. **Clear Hierarchy**: Rely on font size and weight, not color
3. **Subtle Accents**: Use muted colors for secondary text
4. **Minimal Borders**: Prefer subtle dividers or whitespace
5. **Readable Line Length**: Max 65-75 characters per line for text content (max-w-2xl)
6. **Semantic Colors**: Use complete 5-color system consistently across components
7. **Accessibility First**: Meet WCAG AA standards minimum (AAA when possible)
8. **Touch-Friendly**: 44px minimum touch targets
9. **Keyboard Navigation**: Always show focus states
10. **Consistent Patterns**: Same design language across all pages

## Accessibility Checklist

When implementing design tokens:

- [ ] Color contrast meets 4.5:1 for normal text, 3:1 for large text (≥18px)
- [ ] Focus visible indicators (2px outline with offset)
- [ ] Touch targets ≥44x44px
- [ ] Text sized ≥14px for body content (prefer 16px)
- [ ] Semantic HTML structure
- [ ] Aria labels for icon-only buttons
- [ ] Aria-hidden on decorative SVGs
- [ ] Table captions (can be .sr-only)
- [ ] Proper heading hierarchy (h1 → h2 → h3, no skipping)
- [ ] Skip links for keyboard navigation (optional but recommended)