---
name: minimal-design-system
description: Minimalist black/white design system with generous whitespace for HTML artifacts, dashboards, and websites. Use when user says "Nutze mein Designsystem" or "use minimal design system" or requests minimal, clean design with Inter font, Tailwind CSS, and professional aesthetics. Provides design tokens (colors, typography, spacing), button components, and base templates. Never overwrite existing styles - this serves as a starting foundation that can be customized.
---

# Minimal Design System

A minimalist black/white design system with generous whitespace, inspired by modern clean aesthetics. Built with Tailwind CSS and Inter UI font.

## Core Design Philosophy

1. **Generous Whitespace**: Large gaps between sections for breathing room
2. **Clear Hierarchy**: Typography-driven visual hierarchy (size, weight)
3. **Minimal Color**: Black, white, and subtle grays only
4. **Readable**: Max 65-75 characters per line for text content
5. **Reversible**: Perfect light/dark mode symmetry

## When to Use This Skill

Apply this design system when:
- User says "Nutze mein Designsystem" or "use minimal design system"
- Creating new HTML artifacts, dashboards, or websites
- User requests minimal, clean, or professional design
- Starting a new project that needs consistent styling

## How to Apply

### Starting Fresh (New Projects)

1. Use `assets/base-template.html` as starting point
2. Modify content while keeping design foundation
3. Reference `references/design-tokens.md` for color/spacing values
4. Use `references/button-components.md` for interactive elements

### Applying to Existing Content

When user has existing HTML/content:
1. Add Inter font import and Tailwind CDN to `<head>`
2. Add CSS custom properties from design-tokens.md
3. Apply Tailwind utility classes following design tokens
4. Keep generous spacing (16, 24, 32 gaps between sections)
5. Use button components for CTAs

**Critical**: Never overwrite existing custom styles. Layer the design system underneath.

## Design Tokens

All design tokens are documented in `references/design-tokens.md`:
- Color system (light/dark mode)
- Typography (sizes, weights, line heights)
- Spacing scale (4px increments)
- Border radius
- Shadows

## Components

All components are documented in `references/components.md` and `references/button-components.md`:

### Buttons
- Primary, Secondary, Ghost, Link variants
- Three sizes (small, default, large)
- Disabled and loading states
- Icon integration (leading, trailing, icon-only)

### Forms
- Input fields (text, email, password, textarea)
- Checkboxes and radio buttons
- Complete login form example

### Cards
- Basic cards with hover states
- Stats cards for metrics
- Image cards with content

### Tables
- Responsive table layouts
- Hover states and striped rows
- Status badges integration

### Lists
- Checklist with icons
- Feature lists with icons
- Simple ordered/unordered lists

### Badges & Alerts
- Status badges (success, info, warning, error)
- Tags for categories
- Alert components with icons

### Charts
- Simple horizontal bar charts
- Progress indicators
- Data visualization patterns

## Implementation Pattern

```html
<!-- 1. Add to <head> -->
<script src="https://cdn.tailwindcss.com"></script>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">

<!-- 2. Add CSS variables (see design-tokens.md) -->
<style>
  :root {
    --color-bg: #ffffff;
    --color-fg: #000000;
    /* ... more tokens */
  }
</style>

<!-- 3. Structure with generous spacing -->
<div class="max-w-5xl mx-auto px-6 py-12">
  <header class="mb-16">
    <h1 class="text-4xl font-bold mb-4">Title</h1>
  </header>
  <main class="space-y-16">
    <!-- Content with 16-unit spacing between sections -->
  </main>
</div>
```

## Layout Guidelines

- **Max width**: 1280px (max-w-5xl or max-w-6xl)
- **Content width**: 672px (max-w-2xl) for reading text
- **Padding**: 24px on mobile, 32px on desktop
- **Section gaps**: 64px (space-y-16) between major sections
- **Element gaps**: 24px (space-y-6) within sections

## Typography Scale

```
Headings:
- h1: text-4xl sm:text-5xl (36px/48px)
- h2: text-2xl sm:text-3xl (24px/30px)  
- h3: text-xl sm:text-2xl (20px/24px)

Body:
- Default: text-base (16px)
- Large: text-lg (18px)
- Small: text-sm (14px)
- Muted: text-muted (gray-600/gray-400)
```

## Resources

- **assets/base-template.html** - Complete working template with design system
- **assets/showcase.html** - Full showcase website demonstrating all components
- **references/design-tokens.md** - All design tokens (colors, spacing, typography)
- **references/button-components.md** - Button variations and usage patterns
- **references/components.md** - Complete component library (forms, cards, tables, lists, badges, alerts, charts)
