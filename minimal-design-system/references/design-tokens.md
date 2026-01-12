# Design Tokens & Guidelines

This document defines the core design tokens for the minimal design system v2.0, featuring a shadcn-inspired HSL color system combined with generous whitespace.

## Color System

### HSL-Based Semantic Tokens

The design system uses HSL values for maximum flexibility. Colors are defined as HSL components without the `hsl()` wrapper, allowing easy manipulation with opacity modifiers.

```css
:root {
  /* Backgrounds & Foregrounds */
  --background: 0 0% 100%;
  --foreground: 240 10% 3.9%;
  
  /* Card surfaces */
  --card: 0 0% 100%;
  --card-foreground: 240 10% 3.9%;
  
  /* Primary actions */
  --primary: 240 5.9% 10%;
  --primary-foreground: 0 0% 98%;
  
  /* Secondary/subtle elements */
  --secondary: 240 4.8% 95.9%;
  --secondary-foreground: 240 5.9% 10%;
  
  /* Muted/disabled states */
  --muted: 240 4.8% 95.9%;
  --muted-foreground: 240 3.8% 46.1%;
  
  /* Accent highlights */
  --accent: 240 4.8% 95.9%;
  --accent-foreground: 240 5.9% 10%;
  
  /* Borders & inputs */
  --border: 240 5.9% 90%;
  --input: 240 5.9% 90%;
  --ring: 240 5.9% 10%;
  
  /* Border radius */
  --radius: 0.5rem;
}
```

### Dark Mode (Auto via prefers-color-scheme)

```css
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

### Using HSL Tokens

```css
/* Apply colors using hsl() wrapper */
body {
  background-color: hsl(var(--background));
  color: hsl(var(--foreground));
}

/* With opacity modifier */
.overlay {
  background-color: hsl(var(--background) / 0.8);
}

/* Backdrop blur header pattern */
header {
  background-color: hsl(var(--background) / 0.95);
  backdrop-filter: blur(8px);
}
```

### Utility Classes

For convenience, define these utility classes:

```css
.text-muted { color: hsl(var(--muted-foreground)); }
.bg-muted { background-color: hsl(var(--muted)); }
.bg-card { background-color: hsl(var(--card)); }
.border-default { border-color: hsl(var(--border)); }
.bg-primary { background-color: hsl(var(--primary)); }
.text-primary-foreground { color: hsl(var(--primary-foreground)); }
```

### Semantic Colors (Status Indicators)

For status badges, alerts, and indicators, use Tailwind's built-in colors with opacity modifiers:

#### Success (Green)
```html
<!-- Badge -->
<span class="bg-emerald-500/10 text-emerald-600 dark:text-emerald-400 border border-emerald-500/20">Active</span>

<!-- Alert -->
<div class="bg-emerald-500/10 border border-emerald-500/20 text-emerald-400">Success message</div>
```

#### Warning (Yellow/Amber)
```html
<span class="bg-yellow-500/10 text-yellow-600 dark:text-yellow-400 border border-yellow-500/20">Warning</span>
```

#### Error (Red)
```html
<span class="bg-red-500/10 text-red-600 dark:text-red-400 border border-red-500/20">Error</span>
```

#### Info (Blue)
```html
<span class="bg-blue-500/10 text-blue-600 dark:text-blue-400 border border-blue-500/20">Info</span>
```

#### Neutral (Gray)
```html
<span class="border border-default bg-muted">Neutral</span>
```

### Contrast Ratios (WCAG AA Compliant)

| Combination | Ratio | Level |
|-------------|-------|-------|
| Foreground on Background (Light) | 21:1 | AAA ✓ |
| Muted-foreground on Background (Light) | 7:1 | AA ✓ |
| Foreground on Background (Dark) | 21:1 | AAA ✓ |
| Muted-foreground on Background (Dark) | 8.7:1 | AA+ ✓ |

## Typography

### Font Family

```css
* {
  font-family: 'Inter', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
}
```

Load via Google Fonts:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
```

### Font Sizes (Tailwind)

| Class | Size | Usage |
|-------|------|-------|
| `text-xs` | 12px | Badges, labels, timestamps |
| `text-sm` | 14px | Secondary text, captions |
| `text-base` | 16px | Body text |
| `text-lg` | 18px | Lead paragraphs |
| `text-xl` | 20px | Section titles |
| `text-2xl` | 24px | h2 headings |
| `text-3xl` | 30px | h1 subpages |
| `text-4xl` | 36px | h1 hero (mobile) |
| `text-5xl` | 48px | h1 hero (desktop) |

### Font Weights

| Class | Weight | Usage |
|-------|--------|-------|
| `font-normal` | 400 | Body text |
| `font-medium` | 500 | Links, buttons |
| `font-semibold` | 600 | Headings, emphasis |
| `font-bold` | 700 | Hero headlines |

### Tracking (Letter Spacing)

```css
/* Use tracking-tight for headings */
h1, h2, h3 {
  letter-spacing: -0.025em; /* tracking-tight */
}
```

## Spacing Scale

Use Tailwind's standard spacing with emphasis on generous whitespace:

### Section Spacing
- Hero to content: `py-24` or `py-32` (96px-128px)
- Between sections: `py-16` (64px)
- Section borders: `border-t border-default`

### Element Spacing
- Card padding: `p-6` (24px)
- Button padding: `px-6 py-3` or `h-11 px-8`
- Badge padding: `px-2.5 py-1` or `px-3 py-1.5`
- Gap between elements: `gap-4` (16px)
- Gap between sections: `gap-6` or `gap-8`

### Container Widths
- Full content: `max-w-7xl` (1280px) - dashboards
- Content pages: `max-w-4xl` (896px) - personal pages
- Reading content: `max-w-3xl` (768px) - blogs
- Text blocks: `max-w-2xl` (672px) - paragraphs

## Border Radius

```css
--radius: 0.5rem; /* 8px base */
```

| Class | Value | Usage |
|-------|-------|-------|
| `rounded-sm` | calc(var(--radius) - 4px) | Small badges |
| `rounded-md` | calc(var(--radius) - 2px) | Buttons |
| `rounded-lg` | var(--radius) | Cards, inputs |
| `rounded-full` | 9999px | Pills, avatars |

## Shadows

Minimal shadow usage - prefer borders. When needed:

```css
/* Hover state for cards */
.card:hover {
  box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1);
}

/* Or use Tailwind */
<div class="hover:shadow-md transition-shadow">
```

## Focus States

All interactive elements must have visible focus indicators:

```css
a:focus-visible,
button:focus-visible,
input:focus-visible {
  outline: 2px solid hsl(var(--ring));
  outline-offset: 2px;
}
```

## Interactive Elements

### Buttons

#### Primary Button
```html
<button class="inline-flex items-center justify-center h-11 px-8 bg-primary text-primary-foreground text-sm font-medium rounded-md hover:opacity-90 transition-opacity">
  Button
</button>
```

#### Secondary/Outline Button
```html
<button class="inline-flex items-center justify-center h-11 px-8 border border-default text-sm font-medium rounded-md hover:bg-muted transition-colors">
  Button
</button>
```

#### Button with Icon
```html
<button class="inline-flex items-center justify-center gap-2 h-10 px-4 ...">
  <svg class="w-4 h-4" ...></svg>
  Button
</button>
```

### Links

```html
<a href="#" class="text-sm text-muted hover:text-[hsl(var(--foreground))] transition-colors">Link</a>
```

### Inputs

```html
<input 
  type="email" 
  class="h-11 px-4 rounded-md border border-default bg-[hsl(var(--background))] text-sm focus:outline-none focus:ring-2 focus:ring-[hsl(var(--ring))] focus:ring-offset-2"
>
```

## Component Patterns

### Sticky Header with Backdrop Blur

```html
<header class="sticky top-0 z-50 border-b border-default bg-[hsl(var(--background))]/95 backdrop-blur supports-[backdrop-filter]:bg-[hsl(var(--background))]/60">
  <div class="max-w-4xl mx-auto px-6 h-16 flex items-center justify-between">
    <!-- Logo -->
    <!-- Navigation -->
  </div>
</header>
```

### Card

```html
<article class="p-6 rounded-lg border border-default bg-card hover:shadow-md transition-shadow">
  <!-- Content -->
</article>
```

### Badge

```html
<!-- Neutral -->
<span class="text-xs px-2.5 py-1 rounded-full bg-muted">Tag</span>

<!-- Status -->
<span class="text-xs px-2.5 py-1 rounded-full bg-emerald-500/10 text-emerald-600 dark:text-emerald-400 border border-emerald-500/20">Active</span>
```

### Progress Bar

```html
<div class="h-2 rounded-full bg-muted overflow-hidden">
  <div class="h-full w-[75%] bg-emerald-500 rounded-full"></div>
</div>
```

### Alert

```html
<div class="p-3 rounded bg-yellow-500/10 border border-yellow-500/20">
  <p class="text-sm text-yellow-400">⚠️ Warning message here.</p>
</div>
```

## Accessibility Checklist

- [ ] Color contrast meets 4.5:1 for normal text, 3:1 for large text
- [ ] Focus visible indicators on all interactive elements
- [ ] Touch targets ≥44x44px (use h-11 for buttons)
- [ ] Semantic HTML structure (header, main, section, article, footer)
- [ ] Aria labels for icon-only buttons
- [ ] Aria-hidden on decorative SVGs
- [ ] Proper heading hierarchy (h1 → h2 → h3)

## Migration from v1.x

### Key Changes

| v1.x | v2.0 |
|------|------|
| HEX colors (`#ffffff`) | HSL tokens (`0 0% 100%`) |
| `--color-bg` | `--background` |
| `--color-fg` | `--foreground` |
| `--color-muted` | `--muted-foreground` |
| `--color-border` | `--border` |
| `--color-subtle-bg` | `--muted` or `--secondary` |

### Quick Migration

Replace the CSS variables block in your HTML with the new HSL-based tokens from this document.
