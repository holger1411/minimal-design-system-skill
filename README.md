# Minimal Design System - Claude Skill

A minimalist black-and-white design system with generous whitespace for HTML artifacts, dashboards, and websites. Built with Tailwind CSS and Inter UI font.

🌐 **[View Demo Website](https://minimal-design-system-skill.vercel.app)**

## What is a Claude Skill?

A Claude Skill is a folder containing instructions, scripts, and resources that Claude loads dynamically when needed. Skills teach Claude how to complete specific tasks in a repeatable way, improving consistency and performance.

The Minimal Design System Skill gives Claude precise instructions on how to create professional, minimalist websites and components with consistent styling, generous whitespace, and clear hierarchy.

**Claude automatically invokes Skills based on your task—no manual selection needed.** When you describe a task that matches a Skill's description, Claude recognizes it and loads the Skill automatically.

## Features

- ✨ **Generous Whitespace** - Large gaps between sections for breathing room
- 📐 **Clear Hierarchy** - Typography-driven visual hierarchy
- 🎨 **Minimal Colors** - Black, white, and subtle grays only
- 📖 **Readable** - Max 65-75 characters per line for text content
- 🌓 **Dark Mode** - Perfect light/dark mode symmetry
- ⚡ **Tailwind CSS** - Fast, consistent development

## File Structure

The complete skill includes:

```
minimal-design-system/
├── SKILL.md                           # Main skill file with instructions
├── assets/
│   ├── base-template.html            # Complete working template
│   └── showcase.html                 # Full showcase with all components
└── references/
    ├── design-tokens.md              # Color system, typography, spacing
    ├── button-components.md          # Button variations and usage
    └── components.md                 # Complete component library
```

## Quick Start

### Using in Claude.ai (Web & Desktop App)

#### Option 1: Download from GitHub (Recommended - includes all files)

1. **Clone or Download this Repository**
   ```bash
   git clone https://github.com/holger1411/minimal-design-system-skill.git
   ```
   Or download as ZIP from GitHub

2. **Create the Skill ZIP**
   ```bash
   cd minimal-design-system-skill
   zip -r minimal-design-system.zip minimal-design-system/
   ```

3. **Upload to Claude**
   - Go to `Settings → Capabilities → Skills`
   - Click "Upload skill"
   - Select the `minimal-design-system.zip` file

#### Option 2: Quick Start (SKILL.md only)

If you just want to try the basic skill without all templates:

1. Download [SKILL.md](SKILL.md)
2. Create a folder named `minimal-design-system` and place SKILL.md inside
3. ZIP the folder
4. Upload to Claude via `Settings → Capabilities → Skills`

**Note:** The full skill with templates and references provides Claude with more examples and detailed documentation.

### Using in Claude Code (Terminal)

1. **Clone the Repository**
   ```bash
   git clone https://github.com/holger1411/minimal-design-system-skill.git
   ```

2. **Copy to Claude Skills Directory**
   ```bash
   cp -r minimal-design-system-skill/minimal-design-system ~/.claude/skills/
   ```

3. **Restart Claude Code**
   - The Skill will be automatically available in all sessions

### Using in Other LLMs

**ChatGPT:**
1. Go to Settings → Personalization → Custom Instructions
2. Paste the [SKILL.md](SKILL.md) content into the bottom text field
3. Enable "Enable for new chats"

**Google Gemini:**
1. Open a new chat
2. Paste the [SKILL.md](SKILL.md) content as your first message
3. Ask Gemini to follow these instructions

**Other LLMs:**
- Paste the SKILL.md content as a system prompt or at the beginning of your conversation

## Design Principles

### Core Philosophy

1. **Generous Whitespace**: Large gaps between sections for breathing room
2. **Clear Hierarchy**: Typography-driven visual hierarchy (size, weight)
3. **Minimal Color**: Black, white, and subtle grays only
4. **Readable**: Max 65-75 characters per line for text content
5. **Reversible**: Perfect light/dark mode symmetry

### Layout Guidelines

- **Max width**: 1280px (max-w-5xl or max-w-6xl)
- **Content width**: 672px (max-w-2xl) for reading text
- **Padding**: 24px on mobile, 32px on desktop
- **Section gaps**: 64px (space-y-16) between major sections
- **Element gaps**: 24px (space-y-6) within sections

### Typography Scale

```
Headings:
- h1: text-4xl sm:text-5xl (36px/48px)
- h2: text-2xl sm:text-3xl (24px/30px)
- h3: text-xl sm:text-2xl (20px/24px)

Body:
- Default: text-base (16px)
- Large: text-lg (18px)
- Small: text-sm (14px)
- Muted: text-muted (gray-600/gray-400)
```

## Components

The design system includes a comprehensive component library:

### Buttons
- Primary, Secondary, Ghost, Link variants
- Three sizes (small, default, large)
- Disabled and loading states
- Icon integration

### Forms
- Input fields (text, email, password, textarea)
- Checkboxes and radio buttons
- Complete login form example

### Cards
- Basic cards with hover states
- Stats cards for metrics
- Image cards with content

### Tables
- Responsive table layouts
- Hover states and striped rows
- Status badges integration

### Lists & Badges
- Checklists with icons
- Feature lists
- Status badges (success, info, warning, error)
- Tags for categories

### Charts
- Horizontal bar charts
- Progress indicators
- Data visualization patterns

## Implementation Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --color-bg: #ffffff;
      --color-fg: #000000;
      --color-muted: #737373;
      --color-border: #e5e7eb;
      --color-hover: #f5f5f5;
    }
    
    @media (prefers-color-scheme: dark) {
      :root {
        --color-bg: #000000;
        --color-fg: #ffffff;
        --color-muted: #a3a3a3;
        --color-border: #262626;
        --color-hover: #171717;
      }
    }
    
    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
      background-color: var(--color-bg);
      color: var(--color-fg);
    }
  </style>
</head>
<body class="antialiased">
  <div class="max-w-5xl mx-auto px-6 py-12">
    <header class="mb-16">
      <h1 class="text-4xl font-bold mb-4">Welcome</h1>
      <p class="text-lg text-[var(--color-muted)]">A minimalist design approach</p>
    </header>
    
    <main class="space-y-16">
      <section>
        <h2 class="text-2xl font-semibold mb-4">Section Title</h2>
        <p class="text-[var(--color-muted)]">Your content here...</p>
      </section>
    </main>
  </div>
</body>
</html>
```

## Usage Examples

### Creating a Landing Page
```
"Use minimal design system and create a landing page for my SaaS product"
```

### Building a Dashboard
```
"Use minimal design system and build a dashboard with user statistics"
```

### Designing Components
```
"Use minimal design system and create a login form"
```

## How Skills Work

Claude automatically discovers and uses Skills based on your request:

1. **Progressive Disclosure**: Claude scans skill metadata (name and description) first
2. **Automatic Invocation**: When your task matches a skill's description, Claude loads it
3. **No Manual Selection**: You don't need to explicitly activate skills
4. **Composable**: Multiple skills can work together automatically

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Supports both light and dark mode automatically

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT License - feel free to use this skill in your projects.

## Author

Created by Holger Könemann

## Links

- [Demo Website](https://minimal-design-system-skill.vercel.app)
- [Claude AI](https://claude.ai)
- [Claude Skills Documentation](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview)

## Resources

- [What are Skills?](https://support.claude.com/en/articles/12512176-what-are-skills)
- [Using Skills in Claude](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [How to create custom Skills](https://support.claude.com/en/articles/12512198-how-to-create-custom-skills)
- [Skills GitHub Repository](https://github.com/anthropics/skills)