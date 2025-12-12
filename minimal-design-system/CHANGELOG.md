# Changelog

All notable changes to the Minimal Design System Skill will be documented in this file.

## [v1.4] - 2024-12-12

### Added
- **Responsive Navigation**: Complete documentation and examples for mobile-first navigation with animated hamburger menu
- **Tailwind CSS Section**: Reference to official documentation (https://tailwindcss.com/docs/) with guidance to research when needed
- **Mobile Menu Animation**: CSS transitions for smooth open/close animations (max-height, opacity, padding, margin)
- **Navigation Component**: New section in components.md with key classes and accessibility requirements
- **Live Navigation Examples**: Added responsive header to both showcase.html and base-template.html

### Changed
- Updated version to v1.4
- Enhanced header structure in template files with sticky positioning and proper z-index

## [v1.3] - 2024-12-11

### Added
- **Page Structure Guidelines**: New section documenting when and how to use hero sections
- **Hero Section Patterns**: Three styling options (boxed, full-width, minimal) with code examples
- **When NOT to add hero**: Guidance for dashboards, apps, documentation, and forms

### Changed
- Updated version to v1.3

## [v1.2] - 2024-12-10

### Added
- **Complete 5-Color Semantic System**: Success (green), Info (blue), Warning (yellow), Error (red), Neutral (gray)
- **Primary/Secondary Colors**: Explicit color definitions for easier brand customization
- **Enhanced Alert Components**: Full alert system with icons and proper contrast
- **Badge Components**: Status badges for all semantic colors

### Changed
- Updated version to v1.2
- Improved color documentation in design-tokens.md
- Synchronized components between showcase.html and design-system.html

## [v1.1] - 2024-12-09

### Added
- **Accessibility Checklist**: Comprehensive WCAG AA compliance guidelines
- **Focus States**: 2px outline with offset for all interactive elements
- **ARIA Attributes**: Documentation for icon-only buttons and decorative elements
- **Touch Targets**: Minimum 44x44px sizing for all interactive elements
- **Rounded Button Variants**: Pill-style buttons (rounded-full) alongside standard (rounded-md)

### Changed
- Updated `--color-muted` to #525252 (gray-600) for better WCAG contrast
- Enhanced button sizing to meet accessibility standards
- Improved base-template.html with better semantic structure

### Fixed
- Color contrast ratios for muted text (now 4.5:1 compliant)

## [v1.0] - 2024-12-08

### Added
- Initial release of Minimal Design System Skill
- **Core Design Philosophy**: Generous whitespace, clear hierarchy, minimal color, readable typography
- **Design Tokens**: Colors, typography, spacing, borders, shadows
- **Button Components**: Primary, Secondary, Ghost, Link variants in three sizes
- **Form Components**: Inputs, textareas, checkboxes, radio buttons
- **Card Components**: Basic cards, stats cards, image cards
- **Table Components**: Responsive tables with hover states
- **List Components**: Checklists, feature lists, ordered/unordered lists
- **Chart Components**: Simple bar charts and progress indicators
- **Base Template**: Text-focused template with articles, blockquotes, images
- **Showcase Template**: Complete component library reference
- **Light/Dark Mode**: Automatic theme switching via CSS custom properties
- **Inter Font**: Professional typography with proper loading optimization
