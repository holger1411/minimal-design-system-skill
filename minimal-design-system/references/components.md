# Component Library

Complete component reference for the minimal design system. All components support light/dark mode and follow WCAG AA accessibility standards.

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