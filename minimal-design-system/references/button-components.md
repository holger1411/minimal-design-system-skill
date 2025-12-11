# Button Components

This document provides implementation examples for button components in the minimal design system.

## Button Variants

### Primary Button
Use for main actions. High contrast, clear visual weight.

**Standard (rounded-md):**
```html
<button class="px-6 py-3 bg-black text-white font-medium rounded-md hover:bg-gray-800 transition-colors dark:bg-white dark:text-black dark:hover:bg-gray-200">
  Primary Action
</button>
```

**Pill Style (rounded-full):**
```html
<button class="px-6 py-3 bg-black text-white font-medium rounded-full hover:bg-gray-800 transition-colors dark:bg-white dark:text-black dark:hover:bg-gray-200">
  Primary Pill
</button>
```

### Secondary Button
Use for secondary actions. More subtle appearance.

**Standard (rounded-md):**
```html
<button class="px-6 py-3 bg-transparent text-black font-medium rounded-md border border-gray-300 hover:bg-gray-50 transition-colors dark:text-white dark:border-gray-700 dark:hover:bg-gray-900">
  Secondary Action
</button>
```

**Pill Style (rounded-full):**
```html
<button class="px-6 py-3 bg-transparent text-black font-medium rounded-full border border-gray-300 hover:bg-gray-50 transition-colors dark:text-white dark:border-gray-700 dark:hover:bg-gray-900">
  Secondary Pill
</button>
```

### Ghost Button
Use for tertiary actions. Minimal visual weight.

**Standard (rounded-md):**
```html
<button class="px-6 py-3 bg-transparent text-black font-medium rounded-md hover:bg-gray-100 transition-colors dark:text-white dark:hover:bg-gray-900">
  Ghost Action
</button>
```

**Pill Style (rounded-full):**
```html
<button class="px-6 py-3 bg-transparent text-black font-medium rounded-full hover:bg-gray-100 transition-colors dark:text-white dark:hover:bg-gray-900">
  Ghost Pill
</button>
```

### Link Button
Use for navigation or less prominent actions.

```html
<button class="px-2 py-1 text-black font-medium underline-offset-4 hover:underline dark:text-white">
  Link Action
</button>
```

## Button Sizes (WCAG Compliant)

All button sizes meet WCAG 2.5.5 minimum touch target requirements (44x44px).

### Large
```html
<button class="px-8 py-4 text-lg ...">Large Button</button>
<!-- Height: ~56px ✓ -->
```

### Default (Medium)
```html
<button class="px-6 py-3 text-base ...">Default Button</button>
<!-- Height: ~48px ✓ -->
```

### Small
```html
<button class="px-5 py-2.5 text-sm ...">Small Button</button>
<!-- Height: ~44px ✓ (updated from px-4 py-2 for accessibility) -->
```

**Note**: Small buttons updated from `px-4 py-2` to `px-5 py-2.5` to meet 44px minimum height requirement.

## Button States

### Focus State (Required for Accessibility)
All buttons automatically receive focus visible styles via global CSS:

```css
button:focus-visible {
  outline: 2px solid var(--color-fg);
  outline-offset: 2px;
}
```

**Why**: WCAG 2.1 Success Criterion 2.4.7 (Focus Visible) Level AA compliance for keyboard navigation.

### Disabled
Add opacity and prevent interaction:
```html
<button disabled class="px-6 py-3 ... opacity-50 cursor-not-allowed">
  Disabled Button
</button>
```

### Loading
Show loading state with subtle animation:
```html
<button disabled class="px-6 py-3 ... opacity-75 cursor-wait">
  <span class="inline-block animate-pulse">Loading...</span>
</button>
```

## Icon Buttons

### With Icon (Leading)

**Standard:**
```html
<button class="px-6 py-3 flex items-center gap-2 bg-black text-white font-medium rounded-md hover:bg-gray-800 dark:bg-white dark:text-black dark:hover:bg-gray-200">
  <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4"/>
  </svg>
  Add Item
</button>
```

**Pill:**
```html
<button class="px-6 py-3 flex items-center gap-2 bg-black text-white font-medium rounded-full hover:bg-gray-800 dark:bg-white dark:text-black dark:hover:bg-gray-200">
  <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4"/>
  </svg>
  Add Item
</button>
```

### With Icon (Trailing)

**Standard:**
```html
<button class="px-6 py-3 flex items-center gap-2 bg-black text-white font-medium rounded-md hover:bg-gray-800 dark:bg-white dark:text-black dark:hover:bg-gray-200">
  Continue
  <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
  </svg>
</button>
```

**Pill:**
```html
<button class="px-6 py-3 flex items-center gap-2 bg-black text-white font-medium rounded-full hover:bg-gray-800 dark:bg-white dark:text-black dark:hover:bg-gray-200">
  Continue
  <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
  </svg>
</button>
```

### Icon Only (Requires aria-label)

**CRITICAL**: Icon-only buttons MUST have `aria-label` for accessibility.

**Standard:**
```html
<button class="p-3 rounded-md hover:bg-gray-100 dark:hover:bg-gray-900 transition-colors border border-gray-300 dark:border-gray-700" aria-label="Close">
  <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
  </svg>
</button>
```

**Pill:**
```html
<button class="p-3 rounded-full hover:bg-gray-100 dark:hover:bg-gray-900 transition-colors border border-gray-300 dark:border-gray-700" aria-label="Close">
  <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
  </svg>
</button>
```

**Note**: Always add `aria-hidden="true"` to decorative SVG icons so screen readers announce the button label, not the SVG markup.

## Accessibility Requirements

When implementing buttons:

1. ✅ **Minimum Touch Target**: 44x44px (use py-2.5 minimum for small buttons)
2. ✅ **Focus Visible**: 2px outline with 2px offset (handled by global CSS)
3. ✅ **Aria Label**: Required for icon-only buttons
4. ✅ **Aria Hidden**: Add to decorative SVG icons (`aria-hidden="true"`)
5. ✅ **Keyboard Navigation**: All buttons must be keyboard accessible (native `<button>` element handles this)

## Usage Guidelines

1. **Use Primary sparingly**: Typically one primary button per view
2. **Group related actions**: Place secondary buttons near primary
3. **Maintain hierarchy**: Primary > Secondary > Ghost > Link
4. **Consistent sizing**: Use same size for buttons in a group
5. **Clear labels**: Use action verbs (Save, Cancel, Continue)
6. **Choose corner style**: 
   - `rounded-md` for standard, professional look
   - `rounded-full` for softer, modern pill-style look
   - Be consistent within the same context
7. **Icon buttons**: Always label icon-only buttons with `aria-label`
8. **SVG icons**: Mark decorative icons with `aria-hidden="true"`

## Corner Style Decision Guide

**Use `rounded-md` (standard) when:**
- Professional/corporate context
- Dense UI with many buttons
- Forms and data entry
- Traditional web applications

**Use `rounded-full` (pill style) when:**
- Consumer-facing applications
- Marketing/landing pages
- Modern, friendly interfaces
- Fewer buttons with more whitespace

**Consistency**: Once you choose a style for a page/app, stick with it throughout.