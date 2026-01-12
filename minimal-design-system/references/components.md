# Component Library

Complete component reference for the minimal design system. All components support light/dark mode and follow WCAG AA accessibility standards.

## Navigation

Responsive navigation with animated hamburger menu for mobile. See SKILL.md for full implementation details.

### Key Classes

- Desktop nav: `hidden md:flex items-center gap-8`
- Mobile menu button: `md:hidden p-2`
- Mobile menu container: `mobile-menu md:hidden`
- Animation classes: `.mobile-menu`, `.mobile-menu.open`, `.menu-icon`, `.menu-icon.rotate`

### Accessibility Requirements

- `aria-label="Toggle menu"` on hamburger button
- `aria-expanded` state updates on toggle
- Semantic `<nav>` elements
- Keyboard accessible links

## Overflow Scroll Carousel

Horizontal "bleed" slider aligned to content container on the left, extending beyond viewport on the right. Also known as "Edge-to-Edge Carousel" or "Bleed Slider".

### Key Classes

**Container:**
- `scroll-container` - Custom class with `--scroll-padding` variable
- `overflow-x-auto` - Enable horizontal scrolling
- `flex gap-6` - Flexbox layout with gaps
- `snap-x snap-mandatory` - Scroll snap
- `overscroll-x-contain` - Prevent bounce
- `hide-scrollbar` - Custom class to hide scrollbar

**Cards:**
- `scroll-card` - Custom class with `scroll-margin-left`
- `shrink-0` - Prevent compression
- `w-72 sm:w-96` - Fixed responsive width
- `snap-start` - Snap point at card start

### Required CSS

```css
:root {
  --container-5xl: 64rem;
  --container-7xl: 80rem;
}

.scroll-container {
  --scroll-padding: max(1.5rem, calc((100vw - var(--container-5xl)) / 2));
  /* Add container padding (1.5rem = px-6) to start side only for content alignment */
  padding-inline-start: calc(var(--scroll-padding) + 1.5rem);
  padding-inline-end: var(--scroll-padding);
}

@media (min-width: 1024px) {
  .scroll-container {
    --scroll-padding: max(2rem, calc((100vw - var(--container-7xl)) / 2));
  }
}

.scroll-card {
  scroll-margin-inline-start: calc(var(--scroll-padding) + 1.5rem);
}

.hide-scrollbar {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
.hide-scrollbar::-webkit-scrollbar {
  display: none;
}
```

Uses logical properties (`padding-inline-start`, `scroll-margin-inline-start`) for RTL support.

### Accessibility Requirements

- Use semantic elements (`<article>`, `<figure>`, `<blockquote>`)
- Spacer element needs `aria-hidden="true"`
- Native scroll is keyboard accessible

See `references/overflow-carousel.md` for full documentation and variants.

## Badges & Status Indicators

The design system uses a complete 5-color semantic system for badges:

### Success Badge (Green)
```html
<span class="inline-flex px-2 py-1 text-xs font-medium rounded-full bg-green-100 text-green-800 dark:bg-green-900 dark:text-green-200">
  Success
</span>
```

### Info Badge (Blue)
```html
<span class="inline-flex px-2 py-1 text-xs font-medium rounded-full bg-blue-100 text-blue-800 dark:bg-blue-900 dark:text-blue-200">
  Info
</span>
```

### Warning Badge (Yellow)
```html
<span class="inline-flex px-2 py-1 text-xs font-medium rounded-full bg-yellow-100 text-yellow-800 dark:bg-yellow-900 dark:text-yellow-200">
  Warning
</span>
```

### Error Badge (Red)
```html
<span class="inline-flex px-2 py-1 text-xs font-medium rounded-full bg-red-100 text-red-800 dark:bg-red-900 dark:text-red-200">
  Error
</span>
```

### Neutral Badge (Gray)
```html
<span class="inline-flex px-2 py-1 text-xs font-medium rounded-full bg-gray-100 text-gray-800 dark:bg-gray-800 dark:text-gray-200">
  Neutral
</span>
```

## Alerts

Complete 5-color alert system with icons and proper contrast. The full alert documentation continues in separate sections for each alert type.

### Success Alert
```html
<div class="flex items-start gap-3 p-4 rounded-lg border border-green-200 bg-green-50 dark:border-green-900 dark:bg-green-950">
  <svg class="w-5 h-5 text-green-600 dark:text-green-400 flex-shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/>
  </svg>
  <p class="text-sm text-green-800 dark:text-green-200">Your changes have been saved successfully.</p>
</div>
```

[Continuing with remaining alert types, forms, cards, tables, lists, typography elements, and charts...]

Please see showcase.html for complete visual reference of all components.

## Accessibility Guidelines

When using components:

1. **Forms**: Always pair inputs with labels using `for` and `id` attributes
2. **Tables**: Include `<caption>` (use `.sr-only` if hidden visually)
3. **Icon-Only Buttons**: Add `aria-label` for screen readers
4. **Decorative SVGs**: Add `aria-hidden="true"` to prevent screen reader announcement
5. **Interactive Elements**: Ensure focus states are visible (handled by global CSS)
6. **Color Alone**: Never rely on color alone to convey meaning (use icons + text)
7. **Touch Targets**: Minimum 44x44px for all interactive elements
8. **Semantic HTML**: Use proper heading hierarchy (h1 → h2 → h3)

## Screen Reader Only Utility

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