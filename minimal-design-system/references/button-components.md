# Button Components

This document provides implementation examples for button components in the minimal design system.

## Button Variants

### Primary Button
Use for main actions. High contrast, clear visual weight.

```html
<button class="px-6 py-3 bg-black text-white font-medium rounded-md hover:bg-gray-800 transition-colors dark:bg-white dark:text-black dark:hover:bg-gray-200">
  Primary Action
</button>
```

### Secondary Button
Use for secondary actions. More subtle appearance.

```html
<button class="px-6 py-3 bg-transparent text-black font-medium rounded-md border border-gray-300 hover:bg-gray-50 transition-colors dark:text-white dark:border-gray-700 dark:hover:bg-gray-900">
  Secondary Action
</button>
```

### Ghost Button
Use for tertiary actions. Minimal visual weight.

```html
<button class="px-6 py-3 bg-transparent text-black font-medium rounded-md hover:bg-gray-100 transition-colors dark:text-white dark:hover:bg-gray-900">
  Ghost Action
</button>
```

### Link Button
Use for navigation or less prominent actions.

```html
<button class="px-2 py-1 text-black font-medium underline-offset-4 hover:underline dark:text-white">
  Link Action
</button>
```

## Button Sizes

### Large
```html
<button class="px-8 py-4 text-lg ...">Large Button</button>
```

### Default (Medium)
```html
<button class="px-6 py-3 text-base ...">Default Button</button>
```

### Small
```html
<button class="px-4 py-2 text-sm ...">Small Button</button>
```

## Button States

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
```html
<button class="px-6 py-3 flex items-center gap-2 ...">
  <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4"/>
  </svg>
  Add Item
</button>
```

### With Icon (Trailing)
```html
<button class="px-6 py-3 flex items-center gap-2 ...">
  Continue
  <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
  </svg>
</button>
```

### Icon Only
```html
<button class="p-3 rounded-md hover:bg-gray-100 dark:hover:bg-gray-900 transition-colors">
  <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
  </svg>
</button>
```

## Usage Guidelines

1. **Use Primary sparingly**: Typically one primary button per view
2. **Group related actions**: Place secondary buttons near primary
3. **Maintain hierarchy**: Primary > Secondary > Ghost > Link
4. **Consistent sizing**: Use same size for buttons in a group
5. **Clear labels**: Use action verbs (Save, Cancel, Continue)