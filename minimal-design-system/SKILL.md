---
name: minimal-design-system
description: Minimalist black/white design system with generous whitespace for HTML artifacts, dashboards, and websites. Use when user says "Nutze mein Designsystem" or "use minimal design system" or requests minimal, clean design with Inter font, Tailwind CSS, and professional aesthetics. Provides design tokens (colors, typography, spacing), button components, and base templates. Never overwrite existing styles - this serves as a starting foundation that can be customized.
---

# Minimal Design System
**Version: v1.1**

A minimalist black/white design system with generous whitespace, inspired by modern clean aesthetics. Built with Tailwind CSS and Inter UI font.

## Core Design Philosophy

1. **Generous Whitespace**: Large gaps between sections for breathing room
2. **Clear Hierarchy**: Typography-driven visual hierarchy (size, weight)
3. **Minimal Color**: Black, white, and subtle grays only
4. **Readable**: Max 65-75 characters per line for text content
5. **Reversible**: Perfect light/dark mode symmetry
6. **Consistent**: Same design patterns across all pages and components
7. **Accessible**: WCAG AA compliance minimum, focus states, proper contrast

## Quality Standards

### When Creating Production-Ready Sites

If the user intends to use the result productively, ensure:

- ✅ **Accessibility (WCAG)**: AA compliance minimum
  - Color contrast ratios (4.5:1 for normal text, 3:1 for large text)
  - Focus indicators on all interactive elements
  - Aria labels for icon-only buttons
  - Semantic HTML (proper landmarks, headings hierarchy)
  - Keyboard navigation support
  
- ✅ **Usability & UI Best Practices**
  - Touch targets minimum 44x44px
  - Clear visual feedback for interactions
  - Consistent design patterns across pages
  - Responsive design (mobile-first approach)
  
- ✅ **Performance**
  - Optimized font loading (preconnect, display=swap)
  - Minimal CSS (use Tailwind's utility classes)
  - No unnecessary JavaScript
  
- ✅ **SEO**
  - Semantic HTML structure
  - Proper heading hierarchy (h1 → h2 → h3)
  - Meta descriptions
  - Alt text for images

### For Prototyping/Rapid Development

When creating quick prototypes or internal tools, focus on:
- Clean visual design
- Basic accessibility (contrast, semantic HTML)
- Responsive layout

## Documentation Consistency

**CRITICAL**: The HTML files (`assets/base-template.html`, `assets/showcase.html`) and the documentation files (`.md` files) must always be synchronized:

- Changes to HTML → Update corresponding .md documentation
- Changes to .md docs → Update HTML examples
- Design decisions in HTML must match written guidelines
- Component examples must reflect actual implementation

This ensures the skill remains a reliable reference for both Claude and users.

## When to Use This Skill

Apply this design system when:
- User says "Nutze mein Designsystem" or "use minimal design system"
- Creating new HTML artifacts, dashboards, or websites
- User requests minimal, clean, or professional design
- Starting a new project that needs consistent styling

## How to Apply

### Starting Fresh (New Projects)

1. Use `assets/base-template.html` as starting point for text-heavy content
2. Use `assets/showcase.html` as reference for all available components
3. Modify content while keeping design foundation
4. Reference `references/design-tokens.md` for color/spacing values
5. Use `references/button-components.md` for interactive elements

### Applying to Existing Content

When user has existing HTML/content:
1. Add Inter font import and Tailwind CDN to `<head>`
2. Add CSS custom properties from design-tokens.md
3. Apply Tailwind utility classes following design tokens
4. Keep generous spacing (16, 24, 32 gaps between sections)
5. Use button components for CTAs
6. Add focus states and accessibility attributes

**Critical**: Never overwrite existing custom styles. Layer the design system underneath.

## Design Tokens

All design tokens are documented in `references/design-tokens.md`:
- Color system (light/dark mode) with improved contrast
- Typography (sizes, weights, line heights)
- Spacing scale (4px increments)
- Border radius
- Shadows
- Focus states (2px outline with offset)

### Updated Color Values (Better Contrast)

```css
--color-muted: #525252; /* gray-600 → WCAG AA compliant */
/* Dark mode: #a3a3a3 (gray-400) */
```

## Components

All components are documented in `references/components.md` and `references/button-components.md`:

### Buttons
- Primary, Secondary, Ghost, Link variants
- Two corner styles: Standard (rounded-md) and Pill (rounded-full)
- Three sizes (small: 44px height minimum, default, large)
- Disabled and loading states
- Icon integration (leading, trailing, icon-only with aria-labels)
- Focus visible states for keyboard navigation

### Forms
- Input fields (text, email, password, textarea)
- Checkboxes and radio buttons
- Focus states for all inputs
- Complete login form example

### Cards
- Basic cards with hover states
- Stats cards for metrics
- Image cards with content

### Tables
- Responsive table layouts with caption (screen reader support)
- Hover states and striped rows
- Status badges integration

### Lists
- Checklist with icons
- Feature lists with icons
- Simple ordered/unordered lists

### Badges & Alerts
- Status badges (success, info, warning, error, neutral)
- Full semantic color system (5 colors)
- Alert components with icons and proper contrast
- Tags for categories

### Charts
- Simple horizontal bar charts
- Progress indicators
- Data visualization patterns

### Typography Elements
- Blockquotes with semantic cite elements
- Small text (text-sm) for footnotes and meta information
- Proper heading hierarchy

## Implementation Pattern

```html
<!-- 1. Add to <head> -->
<script src="https://cdn.tailwindcss.com"></script>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">

<!-- 2. Add CSS variables (see design-tokens.md) -->
<style>
  :root {
    --color-bg: #ffffff;
    --color-fg: #000000;
    --color-muted: #525252; /* Updated for better contrast */
    /* ... more tokens */
  }
  
  /* Focus visible styles */
  button:focus-visible,
  a:focus-visible,
  input:focus-visible {
    outline: 2px solid var(--color-fg);
    outline-offset: 2px;
  }
</style>

<!-- 3. Structure with semantic HTML -->
<main class="max-w-5xl mx-auto px-6 py-12">
  <header class="mb-16">
    <h1 class="text-4xl font-bold mb-4">Title</h1>
  </header>
  <section class="space-y-16">
    <!-- Content with 16-unit spacing between sections -->
  </section>
</main>
```

## Accessibility Checklist

When creating pages with this design system:

- [ ] Use semantic HTML (`<main>`, `<header>`, `<nav>`, `<section>`)
- [ ] Add `aria-label` to icon-only buttons
- [ ] Add `aria-hidden="true"` to decorative SVG icons
- [ ] Include `<caption>` for tables (can use `.sr-only` class)
- [ ] Ensure 4.5:1 contrast for normal text, 3:1 for large text (≥18px)
- [ ] Add focus visible styles (2px outline with offset)
- [ ] Minimum touch target size: 44x44px
- [ ] Use `<cite>` in blockquotes for attribution
- [ ] Proper heading hierarchy (don't skip levels)
- [ ] Test keyboard navigation (Tab, Enter, Space)

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
- Default: text-base (16px) - 1.5 line-height
- Large: text-lg (18px) - for lead paragraphs
- Small: text-sm (14px) - for footnotes, meta info
- Muted: text-muted (#525252 light, #a3a3a3 dark)
```

## Button Sizing (WCAG Compliant)

```
Small:   px-5 py-2.5 text-sm  → ~44px height ✓
Default: px-6 py-3            → ~48px height ✓
Large:   px-8 py-4 text-lg    → ~56px height ✓
```

## Resources

- **assets/base-template.html** - Text-focused template with articles, blockquotes, images
- **assets/showcase.html** - Complete component library reference
- **references/design-tokens.md** - All design tokens (colors, spacing, typography)
- **references/button-components.md** - Button variations and usage patterns
- **references/components.md** - Complete component library (forms, cards, tables, lists, badges, alerts, charts)

## Maintenance Notes

When updating this skill:
1. Make changes to HTML files first
2. Update corresponding documentation immediately
3. Verify consistency across all files
4. Test accessibility with keyboard navigation
5. Validate color contrast ratios
6. Check responsive behavior on mobile
