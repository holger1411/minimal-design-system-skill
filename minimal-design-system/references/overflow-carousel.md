# Overflow Scroll Carousel

A horizontal scroll slider aligned to the content container on the left, but extending beyond the viewport on the right. Also known as "Edge-to-Edge Carousel", "Bleed Slider", or "Asymmetric Container Carousel".

## Use Cases

- Testimonial sliders
- Product carousels
- Portfolio galleries
- Feature showcases
- Logo sliders

## The Mechanism

### The Problem

A normal horizontally scrolling container is either:
- Enclosed in the content container (loses the "bleed" effect)
- Fully viewport-wide (loses alignment to content)

### The Solution

A CSS variable `--scroll-padding` dynamically calculates the distance from viewport edge to content container:

```css
--scroll-padding: max(
  1.5rem,                              /* Minimum: 24px */
  calc((100vw - var(--container)) / 2) /* Dynamic to container */
);
```

This variable is used **twice**:
1. As `padding-left` on the scroll container
2. As `scroll-margin-left` on individual cards

### Why Both Are Needed

| Property | Purpose |
|----------|---------|
| `padding-left` on container | Positions visible start point at content container |
| `scroll-margin-left` on cards | When snapping, card is positioned at container edge, not viewport edge |
| Spacer element at end | Enables full scrolling to last card |

## Required CSS

Add these styles to the `<style>` block:

```css
:root {
  /* Container widths (Tailwind equivalents) */
  --container-5xl: 64rem;   /* 1024px - max-w-5xl */
  --container-7xl: 80rem;   /* 1280px - max-w-7xl */
}

/* Scroll container */
.scroll-container {
  /* Mobile: Minimum 1.5rem, Desktop: dynamic */
  --scroll-padding: max(1.5rem, calc((100vw - var(--container-5xl)) / 2));
  
  /* 
   * IMPORTANT: Add container padding (1.5rem = px-6) to START side only.
   * This aligns the first card with the content container's inner edge.
   * Uses logical properties for RTL support.
   */
  padding-inline-start: calc(var(--scroll-padding) + 1.5rem);
  padding-inline-end: var(--scroll-padding);
}

/* Responsive: Larger container on desktop */
@media (min-width: 1024px) {
  .scroll-container {
    --scroll-padding: max(2rem, calc((100vw - var(--container-7xl)) / 2));
  }
}

/* Cards: Scroll margin for correct snap behavior */
.scroll-card {
  scroll-margin-inline-start: calc(var(--scroll-padding) + 1.5rem);
}

/* Hide scrollbar */
.hide-scrollbar {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
.hide-scrollbar::-webkit-scrollbar {
  display: none;
}
```

### Why `padding-inline-start` instead of `padding-left`?

Using logical properties (`padding-inline-start`, `padding-inline-end`, `scroll-margin-inline-start`) ensures the carousel works correctly in both LTR and RTL layouts. In LTR, `inline-start` equals `left`. In RTL, it equals `right`.

## HTML Structure

```html
<!-- Section with overflow-hidden on parent -->
<section class="overflow-hidden py-16">
  
  <!-- 
    IMPORTANT: Header uses scroll-container class for alignment!
    This ensures the heading aligns with the first card's left edge.
  -->
  <header class="scroll-container">
    <p class="text-sm uppercase text-muted">Testimonials</p>
    <h2 class="text-3xl font-bold">Heading</h2>
  </header>
  
  <!-- Scroll container -->
  <div id="carousel-1" class="scroll-container mt-12 flex gap-6 overflow-x-auto hide-scrollbar snap-x snap-mandatory overscroll-x-contain scroll-smooth">
    
    <!-- Cards -->
    <article class="scroll-card shrink-0 w-72 sm:w-96 snap-start">
      <!-- Card content -->
    </article>
    
    <article class="scroll-card shrink-0 w-72 sm:w-96 snap-start">
      <!-- Card content -->
    </article>
    
    <!-- More cards... -->
    
    <!-- Spacer at end (important!) -->
    <div class="shrink-0 w-[var(--scroll-padding)]" aria-hidden="true"></div>
    
  </div>
  
  <!-- Dots Navigation (also uses scroll-container for alignment) -->
  <nav class="scroll-container mt-8 flex justify-end" aria-label="Carousel navigation">
    <div id="dots-1" class="flex gap-2">
      <button class="w-2.5 h-2.5 rounded-full bg-[var(--color-fg)]" aria-label="Go to slide 1" aria-current="true"></button>
      <button class="w-2.5 h-2.5 rounded-full bg-[var(--color-border)]" aria-label="Go to slide 2"></button>
      <!-- More dots... -->
    </div>
  </nav>
  
</section>
```

### Key Rule: Use `scroll-container` for All Content

Any content above or below the carousel that should align with the cards must also use the `scroll-container` class. This includes:
- Section headers
- Subheadings and descriptions
- Navigation dots
- Footer content

This ensures consistent alignment across the entire carousel section.

## Tailwind Classes Overview

### Scroll Container

| Class | Purpose |
|-------|---------|
| `overflow-x-auto` | Enables horizontal scrolling |
| `flex gap-6` | Flexbox layout with gaps |
| `snap-x snap-mandatory` | Enable scroll snap |
| `overscroll-x-contain` | Prevents "bounce" at end |
| `scroll-smooth` | Smooth scroll behavior |

### Cards

| Class | Purpose |
|-------|---------|
| `shrink-0` | Prevents card compression |
| `w-72 sm:w-96` | Fixed width (responsive) |
| `snap-start` | Snap point at card start |

## Variants

### Light Cards

```html
<article class="scroll-card shrink-0 w-72 sm:w-96 snap-start">
  <div class="bg-[var(--color-subtle-bg)] rounded-2xl p-8 h-full flex flex-col">
    <blockquote class="flex-1 mb-6">
      <p class="text-lg leading-relaxed">"Testimonial text here..."</p>
    </blockquote>
    <footer class="flex items-center gap-4 pt-6 border-t border-[var(--color-border)]">
      <div class="w-12 h-12 rounded-full bg-[var(--color-border)]"></div>
      <div>
        <p class="font-semibold">Name</p>
        <p class="text-sm text-[var(--color-muted)]">Position, Company</p>
      </div>
    </footer>
  </div>
</article>
```

### Dark Cards with Image Overlay

```html
<article class="scroll-card shrink-0 w-72 sm:w-96 snap-start">
  <div class="relative aspect-[9/16] sm:aspect-[3/4] rounded-2xl overflow-hidden flex flex-col justify-end">
    <!-- Image -->
    <img src="..." alt="" class="absolute inset-0 w-full h-full object-cover">
    <!-- Gradient overlay -->
    <div class="absolute inset-0 bg-gradient-to-t from-black from-[44%] sm:from-25%"></div>
    <!-- Content -->
    <figure class="relative p-8">
      <blockquote>
        <p class="text-xl leading-7 text-white">"Testimonial text here..."</p>
      </blockquote>
      <figcaption class="mt-6 pt-6 border-t border-white/20">
        <p class="text-sm font-medium text-white">Name</p>
        <p class="text-sm font-medium text-neutral-400">Position, Company</p>
      </figcaption>
    </figure>
  </div>
</article>
```

## Accessibility

- Cards should be semantically correct (`<article>`, `<figure>`, `<blockquote>`)
- Spacer element needs `aria-hidden="true"`
- For interactive dots: `aria-label` for each button
- Native scroll behavior is accessible (touch, mouse, keyboard)

## Browser Support

- `scroll-snap-type`: All modern browsers
- `overscroll-behavior`: All modern browsers
- CSS `max()` function: All modern browsers
- CSS Custom Properties: All modern browsers

No JavaScript required for basic functionality!

## Optional Enhancements (with JavaScript)

If desired, the following features can be added with minimal JavaScript:

- Active dot indicator based on scroll position
- Clickable navigation dots
- Auto-play functionality
- Keyboard navigation (arrow keys)

### Dot Navigation Script

```javascript
function initCarousel(carouselId, dotsId) {
  const carousel = document.getElementById(carouselId);
  const dotsContainer = document.getElementById(dotsId);
  if (!carousel || !dotsContainer) return;
  
  const dots = dotsContainer.querySelectorAll('button');
  const cards = carousel.querySelectorAll('.scroll-card');
  
  // Click handler for dots
  dots.forEach((dot, index) => {
    dot.addEventListener('click', () => {
      const card = cards[index];
      if (card) {
        card.scrollIntoView({ behavior: 'smooth', inline: 'start', block: 'nearest' });
      }
    });
  });
  
  // Scroll handler to update active dot
  carousel.addEventListener('scroll', () => {
    const scrollLeft = carousel.scrollLeft;
    const cardWidth = cards[0]?.offsetWidth || 0;
    const gap = 24; // gap-6 = 24px
    const activeIndex = Math.round(scrollLeft / (cardWidth + gap));
    
    dots.forEach((dot, index) => {
      if (index === activeIndex) {
        dot.classList.remove('bg-[var(--color-border)]');
        dot.classList.add('bg-[var(--color-fg)]');
        dot.setAttribute('aria-current', 'true');
      } else {
        dot.classList.remove('bg-[var(--color-fg)]');
        dot.classList.add('bg-[var(--color-border)]');
        dot.removeAttribute('aria-current');
      }
    });
  });
}

// Initialize
initCarousel('carousel-1', 'dots-1');
```

The basic carousel (scrolling, snapping) works fully without JavaScript. The script above adds clickable dots and active state updates.
