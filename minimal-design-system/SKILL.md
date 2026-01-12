---
name: minimal-design-system
description: Minimalist design system with shadcn-inspired HSL color tokens and generous whitespace for HTML artifacts, dashboards, and websites. Use when user says "Nutze mein Designsystem" or "use minimal design system" or requests minimal, clean design with Inter font, Tailwind CSS, and professional aesthetics. Provides semantic design tokens (primary, muted, accent, card), button components, and base templates. Never overwrite existing styles - this serves as a starting foundation that can be customized.
---

# Minimal Design System
**Version: v2.0**

A minimalist design system combining shadcn-inspired HSL color tokens with generous whitespace. Built with Tailwind CSS and Inter font.

## What's New in v2.0

- **HSL Color System**: Flexible color tokens using HSL values (shadcn-style)
- **Semantic Token Names**: `--primary`, `--muted`, `--accent`, `--card`, etc.
- **Auto Dark Mode**: via `prefers-color-scheme` (no JavaScript required)
- **Backdrop Blur Headers**: Modern sticky header pattern
- **Improved Component Library**: Cards, badges, alerts with opacity modifiers

## Tailwind CSS

This design system is built on **Tailwind CSS**. Always use the latest version via CDN:

```html
<script src="https://cdn.tailwindcss.com"></script>
```

### Documentation & Research

- **Official Documentation**: https://tailwindcss.com/docs/
- When implementing complex layouts, **always research the official Tailwind documentation** first
- Use Tailwind's standard patterns and utilities rather than custom CSS where possible

## Core Design Philosophy

1. **Generous Whitespace**: Large gaps between sections for breathing room
2. **Clear Hierarchy**: Typography-driven visual hierarchy (size, weight, tracking)
3. **Minimal Color**: Semantic tokens with neutral palette, status colors only when needed
4. **Readable**: Max 65-75 characters per line for text content
5. **Auto Dark Mode**: Perfect light/dark mode symmetry via CSS media query
6. **Consistent**: Same design patterns across all pages and components
7. **Accessible**: WCAG AA compliance minimum, focus states, proper contrast

## When to Use This Skill

Apply this design system when:
- User says "Nutze mein Designsystem" or "use minimal design system"
- Creating new HTML artifacts, dashboards, or websites
- User requests minimal, clean, or professional design
- Starting a new project that needs consistent styling

## Quick Start Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Page Title</title>
  
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  
  <style>
    :root {
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
      --ring: 240 5.9% 10%;
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
        --ring: 240 4.9% 83.9%;
      }
    }
    
    * { font-family: 'Inter', system-ui, sans-serif; }
    body { background-color: hsl(var(--background)); color: hsl(var(--foreground)); }
    
    .text-muted { color: hsl(var(--muted-foreground)); }
    .bg-muted { background-color: hsl(var(--muted)); }
    .bg-card { background-color: hsl(var(--card)); }
    .border-default { border-color: hsl(var(--border)); }
    .bg-primary { background-color: hsl(var(--primary)); }
    .text-primary-foreground { color: hsl(var(--primary-foreground)); }
    
    a:focus-visible, button:focus-visible {
      outline: 2px solid hsl(var(--ring));
      outline-offset: 2px;
    }
  </style>
</head>
<body class="min-h-screen">
  
  <!-- Header -->
  <header class="sticky top-0 z-50 border-b border-default bg-[hsl(var(--background))]/95 backdrop-blur supports-[backdrop-filter]:bg-[hsl(var(--background))]/60">
    <div class="max-w-4xl mx-auto px-6 h-16 flex items-center justify-between">
      <a href="#" class="text-xl font-bold tracking-tight">Logo</a>
      <nav class="flex items-center gap-6">
        <a href="#" class="text-sm text-muted hover:text-[hsl(var(--foreground))] transition-colors">Link</a>
      </nav>
    </div>
  </header>

  <main class="max-w-4xl mx-auto px-6 py-16">
    <!-- Content -->
  </main>

  <footer class="border-t border-default mt-16">
    <div class="max-w-4xl mx-auto px-6 py-8">
      <p class="text-sm text-muted">© 2025 Company</p>
    </div>
  </footer>

</body>
</html>
```

## Design Tokens

All design tokens are documented in `references/design-tokens.md`.

### Color Token Reference

| Token | Light Mode | Dark Mode | Usage |
|-------|-----------|-----------|-------|
| `--background` | White | Near-black | Page background |
| `--foreground` | Near-black | White | Primary text |
| `--primary` | Near-black | White | Buttons, emphasis |
| `--primary-foreground` | White | Near-black | Text on primary |
| `--muted` | Light gray | Dark gray | Subtle backgrounds |
| `--muted-foreground` | Medium gray | Light gray | Secondary text |
| `--border` | Light gray | Dark gray | Borders, dividers |
| `--card` | White | Near-black | Card backgrounds |
| `--ring` | Near-black | Light gray | Focus rings |

### Using Colors

```css
/* Basic usage */
background-color: hsl(var(--background));
color: hsl(var(--foreground));

/* With opacity */
background-color: hsl(var(--background) / 0.8);

/* In Tailwind classes */
class="bg-[hsl(var(--primary))] text-[hsl(var(--primary-foreground))]"

/* Using utility classes */
class="text-muted bg-muted border-default"
```

## Components

### Buttons

#### Primary Button
```html
<button class="inline-flex items-center justify-center h-11 px-8 bg-primary text-primary-foreground text-sm font-medium rounded-md hover:opacity-90 transition-opacity">
  Button
</button>
```

#### Secondary Button
```html
<button class="inline-flex items-center justify-center h-11 px-8 border border-default text-sm font-medium rounded-md hover:bg-muted transition-colors">
  Button
</button>
```

#### Button with Icon
```html
<button class="inline-flex items-center justify-center gap-2 h-10 px-4 bg-primary text-primary-foreground text-sm font-medium rounded-md hover:opacity-90 transition-opacity">
  <svg class="w-4 h-4" ...></svg>
  Button
</button>
```

### Cards

```html
<article class="p-6 rounded-lg border border-default bg-card hover:shadow-md transition-shadow">
  <h3 class="font-semibold mb-2">Card Title</h3>
  <p class="text-sm text-muted">Card description text.</p>
</article>
```

### Badges

```html
<!-- Neutral -->
<span class="text-xs px-2.5 py-1 rounded-full bg-muted">Tag</span>

<!-- Status: Active/Success -->
<span class="text-xs px-2.5 py-1 rounded-full bg-emerald-500/10 text-emerald-600 dark:text-emerald-400 border border-emerald-500/20">Active</span>

<!-- Status: Warning -->
<span class="text-xs px-2.5 py-1 rounded-full bg-yellow-500/10 text-yellow-600 dark:text-yellow-400 border border-yellow-500/20">Warning</span>

<!-- Status: Info -->
<span class="text-xs px-2.5 py-1 rounded-full bg-blue-500/10 text-blue-600 dark:text-blue-400 border border-blue-500/20">Info</span>

<!-- Status: Error -->
<span class="text-xs px-2.5 py-1 rounded-full bg-red-500/10 text-red-600 dark:text-red-400 border border-red-500/20">Error</span>
```

### Alerts

```html
<!-- Warning Alert -->
<div class="p-3 rounded bg-yellow-500/10 border border-yellow-500/20">
  <p class="text-sm text-yellow-600 dark:text-yellow-400">⚠️ Warning message here.</p>
</div>

<!-- Info Alert -->
<div class="p-3 rounded bg-blue-500/10 border border-blue-500/20">
  <p class="text-sm text-blue-600 dark:text-blue-400">ℹ️ Info message here.</p>
</div>

<!-- Success Alert -->
<div class="p-3 rounded bg-emerald-500/10 border border-emerald-500/20">
  <p class="text-sm text-emerald-600 dark:text-emerald-400">✓ Success message here.</p>
</div>
```

### Progress Bars

```html
<div class="h-2 rounded-full bg-muted overflow-hidden">
  <div class="h-full w-[75%] bg-emerald-500 rounded-full"></div>
</div>
```

### Forms

```html
<input 
  type="email" 
  placeholder="your@email.com"
  class="h-11 px-4 rounded-md border border-default bg-[hsl(var(--background))] text-sm focus:outline-none focus:ring-2 focus:ring-[hsl(var(--ring))] focus:ring-offset-2"
  aria-label="Email address"
>
```

## Layout Patterns

### Sticky Header with Backdrop Blur

```html
<header class="sticky top-0 z-50 border-b border-default bg-[hsl(var(--background))]/95 backdrop-blur supports-[backdrop-filter]:bg-[hsl(var(--background))]/60">
  <div class="max-w-4xl mx-auto px-6 h-16 flex items-center justify-between">
    <!-- Content -->
  </div>
</header>
```

### Hero Section (for landing pages)

```html
<section class="py-24 md:py-32">
  <div class="max-w-2xl">
    <p class="text-muted mb-4">Tagline</p>
    <h1 class="text-4xl md:text-5xl font-bold tracking-tight mb-6">Main Headline</h1>
    <p class="text-xl text-muted mb-8 leading-relaxed">Supporting description.</p>
    <div class="flex flex-wrap gap-4">
      <!-- Buttons -->
    </div>
  </div>
</section>
```

### Section with Border

```html
<section class="py-16 border-t border-default">
  <h2 class="text-2xl font-semibold tracking-tight mb-8">Section Title</h2>
  <!-- Content -->
</section>
```

### Grid Layouts

```html
<!-- Stats Grid -->
<div class="grid grid-cols-2 md:grid-cols-4 gap-4">
  <!-- Cards -->
</div>

<!-- Content + Sidebar -->
<div class="grid md:grid-cols-3 gap-12">
  <div class="md:col-span-2">Main content</div>
  <div>Sidebar</div>
</div>

<!-- Dashboard Grid -->
<div class="grid md:grid-cols-3 gap-6">
  <!-- Cards -->
</div>
```

## Typography

### Headings

```html
<h1 class="text-4xl md:text-5xl font-bold tracking-tight">Hero Title</h1>
<h2 class="text-2xl font-semibold tracking-tight">Section Title</h2>
<h3 class="font-semibold">Card Title</h3>
```

### Body Text

```html
<p class="text-muted leading-relaxed">Body paragraph with relaxed line height.</p>
<p class="text-xl text-muted">Lead paragraph, larger text.</p>
<p class="text-sm text-muted">Caption or secondary text.</p>
```

### Links

```html
<a href="#" class="text-sm text-muted hover:text-[hsl(var(--foreground))] transition-colors">Link</a>
```

## Container Widths

| Class | Width | Use Case |
|-------|-------|----------|
| `max-w-7xl` | 1280px | Dashboards, admin panels |
| `max-w-4xl` | 896px | Personal pages, portfolios |
| `max-w-3xl` | 768px | Blog posts, articles |
| `max-w-2xl` | 672px | Text blocks, forms |

## Spacing Guidelines

### Section Spacing
- Hero padding: `py-24` or `py-32`
- Section padding: `py-16`
- Footer margin: `mt-16`

### Element Spacing
- Card padding: `p-6`
- Button height: `h-11` (44px) or `h-10` (40px)
- Gaps: `gap-4`, `gap-6`, `gap-8`
- Margins between elements: `mb-4`, `mb-6`, `mb-8`

## Dark Mode

The design system uses `prefers-color-scheme: dark` for automatic dark mode. No JavaScript required.

For dashboards that should always be dark, use only the dark mode tokens:

```css
:root {
  --background: 240 10% 3.9%;
  --foreground: 0 0% 98%;
  /* ... all dark mode values ... */
}
```

## Accessibility Checklist

- [ ] Color contrast ≥ 4.5:1 for text, ≥ 3:1 for large text
- [ ] Focus visible indicators (`focus:ring-2`)
- [ ] Touch targets ≥ 44x44px (`h-11`)
- [ ] Semantic HTML (header, main, section, article, footer)
- [ ] Aria labels for icon-only buttons
- [ ] Aria-hidden on decorative SVGs
- [ ] Proper heading hierarchy

## Resources

- **assets/base-template.html** - Starter template
- **assets/showcase.html** - Component reference
- **references/design-tokens.md** - Complete token documentation
- **references/button-components.md** - Button variations
- **references/components.md** - Full component library
- **references/overflow-carousel.md** - Carousel pattern

## Examples

See the `/examples` folder for complete implementations:
- **blog.html** - Minimalist blog with articles
- **frontend-engineer.html** - Personal portfolio page
- **mars-dashboard.html** - Dashboard (dark mode)
