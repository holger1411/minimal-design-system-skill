---
name: minimal-design-system
description: Minimalist black/white design system with generous whitespace for HTML artifacts, dashboards, and websites. Use when user says "Nutze mein Designsystem" or "use minimal design system" or requests minimal, clean design with Inter font, Tailwind CSS, and professional aesthetics. Provides semantic color tokens (primary, muted, accent), button components, and base templates. Never overwrite existing styles - this serves as a starting foundation that can be customized.
---

# Minimal Design System
**Version: v2.0**

A minimalist design system with generous whitespace, semantic color tokens (inspired by shadcn/ui), and modern aesthetics. Built with Tailwind CSS and Inter font.

## What's New in v2.0

- **HSL-based color system** for flexible theming and opacity support
- **Semantic token names** (`primary`, `muted`, `accent`, `card`, etc.)
- **Backdrop-blur headers** for modern sticky navigation
- **Refined badge styles** (pill-shaped, compact)
- **`--radius` CSS variable** for consistent border-radius
- **`tracking-tight`** for polished headline typography

## Tailwind CSS

This design system is built on **Tailwind CSS**. Always use the latest version via CDN:

```html
<script src="https://cdn.tailwindcss.com"></script>
```

### Documentation & Research

- **Official Documentation**: https://tailwindcss.com/docs/
- When implementing complex layouts or unfamiliar utilities, **always research the official Tailwind documentation** first
- Use Tailwind's standard patterns and utilities rather than custom CSS where possible

## Core Design Philosophy

1. **Generous Whitespace**: Large gaps between sections for breathing room
2. **Clear Hierarchy**: Typography-driven visual hierarchy (size, weight, tracking)
3. **Semantic Colors**: Named tokens (`primary`, `muted`) instead of raw values
4. **Readable**: Max 65-75 characters per line for text content
5. **Reversible**: Perfect light/dark mode symmetry (auto via prefers-color-scheme)
6. **Consistent**: Same design patterns across all pages and components
7. **Accessible**: WCAG AA compliance minimum, focus states, proper contrast

## Quick Start

### Minimal HTML Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Page Title</title>
  
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Inter Font -->
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
      --input: 240 5.9% 90%;
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
        --input: 240 3.7% 15.9%;
        --ring: 240 4.9% 83.9%;
      }
    }
    
    * {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
      border-color: hsl(var(--border));
    }
    
    body {
      background-color: hsl(var(--background));
      color: hsl(var(--foreground));
    }
    
    /* Focus visible styles */
    button:focus-visible,
    a:focus-visible,
    input:focus-visible {
      outline: 2px solid hsl(var(--ring));
      outline-offset: 2px;
    }
  </style>
</head>
<body class="min-h-screen antialiased">
  <main class="max-w-4xl mx-auto px-6 py-16">
    <!-- Content here -->
  </main>
</body>
</html>
```

## Color System

### Semantic Tokens

Use semantic names for maintainability and theming:

| Token | Usage | Tailwind Class |
|-------|-------|----------------|
| `--background` | Page background | `bg-[hsl(var(--background))]` |
| `--foreground` | Primary text | `text-[hsl(var(--foreground))]` |
| `--primary` | Buttons, CTAs | `bg-[hsl(var(--primary))]` |
| `--primary-foreground` | Text on primary | `text-[hsl(var(--primary-foreground))]` |
| `--secondary` | Secondary backgrounds | `bg-[hsl(var(--secondary))]` |
| `--muted` | Muted backgrounds | `bg-[hsl(var(--muted))]` |
| `--muted-foreground` | Secondary text | `text-[hsl(var(--muted-foreground))]` |
| `--accent` | Hover states | `bg-[hsl(var(--accent))]` |
| `--border` | Borders, dividers | `border-[hsl(var(--border))]` |
| `--card` | Card backgrounds | `bg-[hsl(var(--card))]` |
| `--ring` | Focus rings | `ring-[hsl(var(--ring))]` |

### Opacity Support

HSL format allows easy opacity modifiers:

```html
<!-- 50% opacity background -->
<div class="bg-[hsl(var(--primary)/0.5)]">Semi-transparent</div>

<!-- 10% opacity for subtle backgrounds -->
<div class="bg-[hsl(var(--primary)/0.1)]">Very subtle</div>
```

### Status Colors

For badges and alerts, use Tailwind's built-in colors with opacity:

```html
<!-- Success -->
<span class="bg-emerald-500/10 text-emerald-600 dark:text-emerald-400">Success</span>

<!-- Info -->
<span class="bg-blue-500/10 text-blue-600 dark:text-blue-400">Info</span>

<!-- Warning -->
<span class="bg-amber-500/10 text-amber-600 dark:text-amber-400">Warning</span>

<!-- Error -->
<span class="bg-red-500/10 text-red-600 dark:text-red-400">Error</span>
```

## Typography

### Headlines

Use `tracking-tight` for a modern, polished look:

```html
<h1 class="text-4xl md:text-5xl font-bold tracking-tight">Hero Headline</h1>
<h2 class="text-2xl md:text-3xl font-semibold tracking-tight">Section Title</h2>
<h3 class="text-xl font-semibold">Subsection</h3>
```

### Body Text

```html
<p class="text-[hsl(var(--muted-foreground))] leading-relaxed">
  Secondary paragraph text with muted color.
</p>
```

### Scale Reference

| Element | Classes |
|---------|---------|
| Hero h1 | `text-4xl md:text-5xl font-bold tracking-tight` |
| Section h2 | `text-2xl font-semibold tracking-tight` |
| Card title | `text-lg font-semibold` or `font-semibold` (base size) |
| Body | `text-base` (default) |
| Small/meta | `text-sm text-[hsl(var(--muted-foreground))]` |

## Components

### Primary Button

```html
<button class="inline-flex items-center justify-center h-11 px-8 bg-[hsl(var(--primary))] text-[hsl(var(--primary-foreground))] text-sm font-medium rounded-md hover:bg-[hsl(var(--primary)/0.9)] transition-colors">
  Button Text
</button>
```

### Secondary/Outline Button

```html
<button class="inline-flex items-center justify-center h-11 px-8 border border-[hsl(var(--input))] bg-[hsl(var(--background))] text-sm font-medium rounded-md hover:bg-[hsl(var(--accent))] hover:text-[hsl(var(--accent-foreground))] transition-colors">
  Secondary
</button>
```

### Ghost Button

```html
<button class="inline-flex items-center justify-center h-10 px-4 text-sm font-medium rounded-md hover:bg-[hsl(var(--accent))] hover:text-[hsl(var(--accent-foreground))] transition-colors">
  Ghost
</button>
```

### Card

```html
<div class="rounded-lg border border-[hsl(var(--border))] bg-[hsl(var(--card))] text-[hsl(var(--card-foreground))] p-6 hover:shadow-md transition-shadow">
  <h3 class="font-semibold mb-2">Card Title</h3>
  <p class="text-sm text-[hsl(var(--muted-foreground))]">Card description text.</p>
</div>
```

### Badge (Pill Style)

```html
<!-- Neutral -->
<span class="inline-flex items-center rounded-full border border-[hsl(var(--border))] bg-[hsl(var(--secondary))] px-2.5 py-0.5 text-xs font-semibold text-[hsl(var(--secondary-foreground))]">
  Badge
</span>

<!-- Status badges -->
<span class="inline-flex items-center rounded-full px-2.5 py-0.5 text-xs font-semibold bg-emerald-500/10 text-emerald-600 border border-emerald-500/20">Active</span>
<span class="inline-flex items-center rounded-full px-2.5 py-0.5 text-xs font-semibold bg-blue-500/10 text-blue-600 border border-blue-500/20">New</span>
```

### Input Field

```html
<input 
  type="text" 
  placeholder="Enter text..."
  class="h-10 w-full rounded-md border border-[hsl(var(--input))] bg-[hsl(var(--background))] px-3 py-2 text-sm placeholder:text-[hsl(var(--muted-foreground))] focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-[hsl(var(--ring))] focus-visible:ring-offset-2"
>
```

## Layout Patterns

### Sticky Header with Backdrop Blur

```html
<header class="sticky top-0 z-50 w-full border-b border-[hsl(var(--border))] bg-[hsl(var(--background)/0.95)] backdrop-blur supports-[backdrop-filter]:bg-[hsl(var(--background)/0.6)]">
  <div class="max-w-4xl mx-auto px-6 h-16 flex items-center justify-between">
    <a href="#" class="text-xl font-bold tracking-tight">Logo</a>
    <nav class="flex items-center gap-6">
      <a href="#" class="text-sm font-medium text-[hsl(var(--muted-foreground))] hover:text-[hsl(var(--foreground))] transition-colors">Link</a>
    </nav>
  </div>
</header>
```

### Section Spacing

```html
<main class="max-w-4xl mx-auto px-6">
  <!-- Hero: extra top padding -->
  <section class="py-24 md:py-32">
    <h1 class="text-5xl font-bold tracking-tight mb-6">Headline</h1>
  </section>
  
  <!-- Content sections: consistent spacing with border -->
  <section class="py-16 border-t border-[hsl(var(--border))]">
    <h2 class="text-2xl font-semibold tracking-tight mb-8">Section</h2>
  </section>
</main>
```

### Two-Column Layout

```html
<div class="grid md:grid-cols-3 gap-12">
  <div class="md:col-span-2">
    <!-- Main content (2/3) -->
  </div>
  <div>
    <!-- Sidebar (1/3) -->
  </div>
</div>
```

## Responsive Navigation

### Desktop + Mobile Menu Pattern

```html
<header class="sticky top-0 z-50 w-full border-b border-[hsl(var(--border))] bg-[hsl(var(--background)/0.95)] backdrop-blur">
  <div class="max-w-4xl mx-auto px-6">
    <div class="h-16 flex items-center justify-between">
      <a href="#" class="text-xl font-bold tracking-tight">Logo</a>
      
      <!-- Desktop Nav -->
      <nav class="hidden md:flex items-center gap-6">
        <a href="#" class="text-sm font-medium">Home</a>
        <a href="#" class="text-sm text-[hsl(var(--muted-foreground))] hover:text-[hsl(var(--foreground))]">About</a>
      </nav>
      
      <!-- Mobile Menu Button -->
      <button id="menu-btn" class="md:hidden p-2" aria-label="Toggle menu">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
        </svg>
      </button>
    </div>
    
    <!-- Mobile Nav -->
    <nav id="mobile-menu" class="hidden md:hidden pb-4">
      <a href="#" class="block py-2 text-sm font-medium">Home</a>
      <a href="#" class="block py-2 text-sm text-[hsl(var(--muted-foreground))]">About</a>
    </nav>
  </div>
</header>

<script>
  document.getElementById('menu-btn').addEventListener('click', () => {
    document.getElementById('mobile-menu').classList.toggle('hidden');
  });
</script>
```

## Page Structure Guidelines

### When to Add Hero Sections

**Add hero for:** Landing pages, homepages, personal sites, marketing pages
**Skip hero for:** Dashboards, admin panels, forms, documentation

### Hero Example

```html
<section class="py-24 md:py-32">
  <div class="max-w-2xl">
    <p class="text-[hsl(var(--muted-foreground))] mb-4">Tagline or greeting</p>
    <h1 class="text-4xl md:text-5xl font-bold tracking-tight mb-6">
      Main headline goes here
    </h1>
    <p class="text-xl text-[hsl(var(--muted-foreground))] mb-8 leading-relaxed">
      Supporting description that explains the value proposition.
    </p>
    <div class="flex flex-wrap gap-4">
      <a href="#" class="inline-flex items-center justify-center h-11 px-8 bg-[hsl(var(--primary))] text-[hsl(var(--primary-foreground))] text-sm font-medium rounded-md">
        Primary CTA
      </a>
      <a href="#" class="inline-flex items-center justify-center h-11 px-8 border border-[hsl(var(--input))] text-sm font-medium rounded-md">
        Secondary CTA
      </a>
    </div>
  </div>
</section>
```

## Quality Standards

### For Production Sites

- ✅ WCAG AA compliance (4.5:1 contrast, focus indicators)
- ✅ Semantic HTML (`<main>`, `<header>`, `<nav>`, `<section>`)
- ✅ Touch targets ≥44px (`h-11`)
- ✅ Responsive design (mobile-first)
- ✅ Keyboard navigation support

### For Prototyping

Focus on: Clean visual design, basic accessibility, responsive layout

## Accessibility Checklist

- [ ] Use semantic HTML landmarks
- [ ] Add `aria-label` to icon-only buttons
- [ ] Add `aria-hidden="true"` to decorative SVGs
- [ ] Ensure 4.5:1 contrast for normal text
- [ ] Add focus visible styles (included in base CSS)
- [ ] Minimum touch target: 44px
- [ ] Proper heading hierarchy (h1 → h2 → h3)
- [ ] Test keyboard navigation

## Resources

- **assets/base-template.html** - Complete starter template
- **assets/showcase.html** - Component library reference
- **references/design-tokens.md** - All design tokens with HSL values
- **references/button-components.md** - Button variations
- **references/components.md** - Full component library

## Migration from v1.x

| Old Token | New Token |
|-----------|-----------|
| `--color-bg` | `--background` |
| `--color-fg` | `--foreground` |
| `--color-muted` | `--muted-foreground` |
| `--color-border` | `--border` |
| `--color-subtle-bg` | `--secondary` |
| `--color-hover-bg` | `--accent` |

Usage change:
```html
<!-- v1.x -->
<p class="text-[var(--color-muted)]">Text</p>

<!-- v2.0 -->
<p class="text-[hsl(var(--muted-foreground))]">Text</p>
```
