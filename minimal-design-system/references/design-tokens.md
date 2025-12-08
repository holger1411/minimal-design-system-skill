# Design Tokens & Guidelines

This document defines the core design tokens for the minimal black/white design system.

## Color System

### Base Colors - Light Mode
```css
--color-bg: #ffffff;
--color-fg: #000000;
--color-muted: #6b7280;
--color-border: #e5e7eb;
--color-subtle-bg: #f9fafb;
--color-hover-bg: #f3f4f6;
```

### Base Colors - Dark Mode
```css
--color-bg: #000000;
--color-fg: #ffffff;
--color-muted: #9ca3af;
--color-border: #1f2937;
--color-subtle-bg: #111111;
--color-hover-bg: #1a1a1a;
```

### Semantic Colors

#### Success (Green)
- Light Background: #dcfce7 (green-100)
- Text: #166534 (green-800)
- Dark Background: #14532d (green-900)
- Usage: Success messages, confirmations, positive states

#### Info (Blue)
- Light Background: #dbeafe (blue-100)
- Text: #1e40af (blue-800)
- Dark Background: #1e3a8a (blue-900)
- Usage: Informational messages, tips, neutral notifications

#### Warning (Yellow)
- Light Background: #fef3c7 (yellow-100)
- Text: #92400e (yellow-800)
- Dark Background: #78350f (yellow-900)
- Usage: Warnings, cautions, important notices

#### Danger/Error (Red)
- Light Background: #fee2e2 (red-100)
- Text: #991b1b (red-800)
- Dark Background: #7f1d1d (red-900)
- Usage: Errors, destructive actions, critical alerts

#### Neutral (Gray)
- Light Background: #f3f4f6 (gray-100)
- Text: #1f2937 (gray-800)
- Dark Background: #1f2937 (gray-800)
- Usage: Neutral information, inactive states

## Typography

### Font Family
- Primary: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif
- Monospace: 'Monaco', 'Courier New', monospace

### Font Sizes (Tailwind equivalents)
- xs: 0.75rem / 12px
- sm: 0.875rem / 14px
- base: 1rem / 16px
- lg: 1.125rem / 18px
- xl: 1.25rem / 20px
- 2xl: 1.5rem / 24px
- 3xl: 1.875rem / 30px
- 4xl: 2.25rem / 36px
- 5xl: 3rem / 48px

### Font Weights
- normal: 400
- medium: 500
- semibold: 600
- bold: 700

### Line Heights
- tight: 1.25
- normal: 1.5
- relaxed: 1.75

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
- md: 0.375rem / 6px
- lg: 0.5rem / 8px
- xl: 0.75rem / 12px

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

## Design Principles

1. **Generous Whitespace**: Use large gaps (8, 12, 16, 24) between sections
2. **Clear Hierarchy**: Rely on font size and weight, not color
3. **Subtle Accents**: Use muted colors for secondary text
4. **Minimal Borders**: Prefer subtle dividers or whitespace
5. **Readable Line Length**: Max 65-75 characters per line for text content
6. **Semantic Colors**: Use appropriate semantic colors for status and feedback