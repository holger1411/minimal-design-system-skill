---
name: minimal-design-system
description: Minimalist black/white design system with generous whitespace for HTML artifacts, dashboards, and websites. Use when user says "Nutze mein Designsystem" or "use minimal design system" or requests minimal, clean design with Inter font, Tailwind CSS, and professional aesthetics. Provides design tokens (colors, typography, spacing), button components, and base templates. Never overwrite existing styles - this serves as a starting foundation that can be customized.
---

# Minimal Design System
**Version: v1.4**

A minimalist black/white design system with generous whitespace, inspired by modern clean aesthetics. Built with Tailwind CSS and Inter UI font.

## Tailwind CSS

This design system is built on **Tailwind CSS**. Always use the latest version via CDN:

```html
<script src="https://cdn.tailwindcss.com"></script>
```

### Documentation & Research

- **Official Documentation**: https://tailwindcss.com/docs/
- When implementing complex layouts or unfamiliar utilities, **always research the official Tailwind documentation** first
- Use Tailwind's standard patterns and utilities rather than custom CSS where possible
- The documentation is comprehensive and includes examples for all utilities

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

## Responsive Navigation

**IMPORTANT**: All navigation must be responsive. On smaller screens (below `md` breakpoint / 768px), use a hamburger menu.

### Navigation Pattern

- **Desktop (md and up)**: Horizontal navigation with visible links
- **Mobile (below md)**: Hamburger icon that reveals a vertical menu

### Hamburger Menu Implementation

Use CSS transitions for smooth animations. The menu should:
1. Be completely invisible when closed (no spacing/padding)
2. Animate smoothly when opening/closing
3. Include a visual icon transition (hamburger ↔ X)

```css
/* Mobile menu animation */
.mobile-menu {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease-out, opacity 0.3s ease-out, padding 0.3s ease-out, margin 0.3s ease-out;
  opacity: 0;
  padding: 0;
  margin: 0;
  border-top: 1px solid transparent;
}

.mobile-menu.open {
  max-height: 300px;
  opacity: 1;
  padding-top: 1rem;
  padding-bottom: 0.5rem;
  margin-top: 1rem;
  border-top-color: var(--color-border);
}

.menu-icon {
  transition: transform 0.2s ease-out;
}

.menu-icon.rotate {
  transform: rotate(90deg);
}
```

### Header Structure Example

```html
<header class="sticky top-0 z-50 bg-[var(--color-bg)] border-b border-[var(--color-border)]">
  <div class="max-w-6xl mx-auto px-6 py-4 md:py-6">
    <div class="flex items-center justify-between">
      <!-- Logo -->
      <a href="/" class="text-lg md:text-xl font-bold">Logo</a>
      
      <!-- Desktop Navigation -->
      <nav class="hidden md:flex items-center gap-8">
        <a href="/" class="font-medium">Home</a>
        <a href="/about" class="text-[var(--color-muted)] hover:text-[var(--color-fg)] transition-colors">About</a>
      </nav>

      <!-- Desktop CTA -->
      <div class="hidden md:block">
        <a href="/contact" class="px-6 py-3 bg-black text-white font-medium rounded-full">Contact</a>
      </div>

      <!-- Mobile Menu Button -->
      <button id="mobile-menu-btn" class="md:hidden p-2 -mr-2" aria-label="Toggle menu" aria-expanded="false">
        <svg class="w-6 h-6 menu-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path id="menu-icon" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
          <path id="close-icon" class="hidden" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
        </svg>
      </button>
    </div>

    <!-- Mobile Menu -->
    <nav id="mobile-menu" class="mobile-menu md:hidden">
      <div class="flex flex-col gap-4">
        <a href="/" class="font-medium py-2">Home</a>
        <a href="/about" class="text-[var(--color-muted)] py-2">About</a>
        <a href="/contact" class="inline-block text-center px-6 py-3 bg-black text-white font-medium rounded-full mt-2">Contact</a>
      </div>
    </nav>
  </div>
</header>

<script>
  const mobileMenuBtn = document.getElementById('mobile-menu-btn');
  const mobileMenu = document.getElementById('mobile-menu');
  const menuIcon = document.getElementById('menu-icon');
  const closeIcon = document.getElementById('close-icon');
  const menuSvg = mobileMenuBtn.querySelector('svg');

  mobileMenuBtn.addEventListener('click', () => {
    const isOpen = mobileMenu.classList.contains('open');
    mobileMenu.classList.toggle('open');
    menuIcon.classList.toggle('hidden');
    closeIcon.classList.toggle('hidden');
    menuSvg.classList.toggle('rotate');
    mobileMenuBtn.setAttribute('aria-expanded', !isOpen);
  });
</script>
```

### Navigation Accessibility

- Use `aria-label="Toggle menu"` on the hamburger button
- Update `aria-expanded` state when menu opens/closes
- Ensure all links are keyboard accessible
- Use semantic `<nav>` elements

## Page Structure Guidelines

When creating static websites (not interactive apps or dashboards), follow these structural patterns:

### Hero Section

**For landing pages, homepages, and content pages**: Always include a hero section at the top. This is standard web design practice and should be added automatically without the user explicitly requesting it.

A hero section typically includes:
- A prominent headline (h1, text-4xl or text-5xl)
- A supporting subheadline or description (text-xl, muted color)
- Optional: A call-to-action button or link
- Optional: A visual element (image, illustration, or decorative background)

**Hero styling options:**
- **Boxed hero**: Contained within a rounded container with background color (e.g., dark background with light text, or light gray background)
- **Full-width hero**: Spans the entire viewport width with generous padding
- **Minimal hero**: Simple text-based hero with extra whitespace

```html
<!-- Example: Boxed Hero -->
<div class="max-w-4xl mx-auto px-6 pt-12">
  <header class="bg-neutral-900 rounded-2xl px-10 py-16 mb-16">
    <h1 class="text-5xl font-bold text-white mb-4">Headline</h1>
    <p class="text-xl text-neutral-400">Supporting description text.</p>
  </header>
</div>
```

### When NOT to add a hero section

- **Dashboards and admin interfaces**: Start directly with the content/data
- **Interactive applications**: Focus on the UI controls
- **Documentation pages**: Start with navigation or table of contents
- **Forms and tools**: The form itself is the primary content

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
