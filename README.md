# Minimal Design System - Claude Skill

A minimalist black & white design system for Claude AI. Clean, modern, and production-ready with generous whitespace and Inter UI typography.

## 🎨 Design Philosophy

- **Generous Whitespace**: Large gaps and breathing room for clarity
- **Typography First**: Clear hierarchy through size and weight
- **Minimal Color**: Black, white, and subtle grays with semantic colors for feedback
- **Dark Mode Ready**: Perfect symmetry between light and dark
- **Tailwind CSS**: Rapid development with utility classes
- **Inter UI Font**: Professional, readable typography

## 🧩 Components Included

### Buttons
- Primary, Secondary, Ghost, Link variants
- Small, Default, Large sizes
- Icon support (leading, trailing, icon-only)
- Disabled and loading states

### Forms
- Text inputs, email, password, textarea
- Checkboxes and radio buttons
- Complete login form template

### Cards
- Basic cards with hover states
- Stats cards for metrics and KPIs
- Image cards with content

### Tables
- Responsive table layouts
- Hover states and striped rows
- Status badge integration

### Lists
- Checklists with icons
- Feature lists with descriptions
- Simple ordered/unordered lists

### Badges & Alerts
- Status badges: Success, Info, Warning, Error, Neutral
- Category tags
- Alert components with icons

### Charts
- Horizontal bar charts
- Progress indicators
- Simple data visualization

### Navigation
- Clean navigation bars
- Mobile-responsive

## 🎨 Color System

### Base Colors
- Background & Foreground (perfect black/white)
- Muted text colors
- Subtle borders and backgrounds

### Semantic Colors
- **Success** (Green): Confirmations, positive states
- **Info** (Blue): Informational messages, tips
- **Warning** (Yellow): Cautions, important notices
- **Danger** (Red): Errors, destructive actions
- **Neutral** (Gray): Inactive states, neutral info

## 📥 Installation

### For Claude.ai (Web & Mobile)

1. **Download the Skill**
   - Download [`minimal-design-system.skill`](minimal-design-system.skill)

2. **Upload to Claude**
   - Go to [Claude.ai](https://claude.ai)
   - Navigate to **Skills** (in sidebar or settings)
   - Click **"Upload Skill"** or **"+"**
   - Select the downloaded `.skill` file

3. **Activate the Skill**
   - In your project, go to project settings
   - Enable "Minimal Design System" skill
   - Click "Save"

### For Claude Desktop App

1. **Download the Skill**
   - Download [`minimal-design-system.skill`](minimal-design-system.skill)

2. **Open Skills Manager**
   - Open Claude Desktop app
   - Go to **Settings** (⚙️ icon)
   - Navigate to **Skills** tab

3. **Add the Skill**
   - Click **"Add Skill"** or **"Import Skill"**
   - Select the downloaded `.skill` file
   - The skill will be installed automatically

4. **Enable in Project**
   - Create a new project or open existing one
   - Open project settings
   - Enable "Minimal Design System" from available skills
   - The skill is now ready to use!

## 🚀 Usage

### Triggering the Skill

The skill activates automatically when you use these phrases:

**German:**
```
"Nutze mein Designsystem"
```

**English:**
```
"use minimal design system"
"apply my design system"
```

Or when you request:
- Minimal, clean design
- Professional layouts
- Black & white interfaces

### Example Prompts

```
"Create a dashboard using my design system"
```

```
"Build a login page with minimal design system"
```

```
"Design a landing page. Use minimal design system."
```

```
"Make a contact form with my design system, include validation"
```

## 💡 Usage Tips

### Starting Fresh
- Claude will use the base template as foundation
- All components will follow design tokens
- Consistent spacing and typography applied automatically

### Applying to Existing Projects
- The skill won't overwrite existing custom styles
- It layers the design system underneath
- You can customize colors while keeping structure

### Best Practices
1. **Be specific**: "Create a stats dashboard with 3 cards"
2. **Reference components**: "Add a login form with the design system buttons"
3. **Iterate**: Ask for adjustments after initial creation
4. **Combine**: "Use tables and charts together"

## 📚 What's Included in the Skill

### Documentation
- **SKILL.md**: Main instructions and workflows
- **design-tokens.md**: All colors, typography, spacing
- **components.md**: Complete component library
- **button-components.md**: Detailed button documentation

### Assets
- **base-template.html**: Ready-to-use HTML starter
- **showcase.html**: Full component showcase (this website!)

## 🎯 Use Cases

- **Dashboards**: Admin panels, analytics views
- **Landing Pages**: Product pages, marketing sites
- **Web Apps**: SaaS interfaces, tools
- **Documentation**: Clean, readable docs
- **Portfolios**: Minimal personal sites
- **Forms**: Login, signup, contact forms

## 🔧 Customization

The skill provides a foundation. You can:
- Add your brand colors as accents
- Extend components with variants
- Adjust spacing for your needs
- Add custom components following the patterns

## 📖 Documentation

Visit the showcase website to see all components in action:
- [Live Demo](#) (add your deployed URL here)

## 🌐 Publishing Your Website

This website can be deployed to:

### Vercel (Recommended)
```bash
cd /path/to/minimal-design-system-skill
vercel deploy
```

### Netlify
1. Drag & drop folder to [netlify.com](https://netlify.com)
2. Or connect to Git repository

### GitHub Pages
```bash
git init
git add .
git commit -m "Initial commit"
git push -u origin main
# Enable GitHub Pages in repository settings
```

## 📁 File Structure

```
minimal-design-system-skill/
├── index.html                    # Showcase website
├── minimal-design-system.skill   # Claude skill file
└── README.md                     # This file
```

## 🆘 Troubleshooting

### Skill not activating?
- Make sure it's enabled in your project settings
- Try using the exact trigger phrases
- Check if skill shows as "Active" in skills list

### Colors not showing?
- Hard refresh browser: `Cmd + Shift + R` (Mac) or `Ctrl + Shift + R` (Windows)
- Clear browser cache
- Try in incognito/private mode

### Download button not working?
- Make sure `minimal-design-system.skill` is in same folder as `index.html`
- Check file permissions
- Try downloading from outputs folder directly

## 🤝 Contributing

Feel free to:
- Report issues
- Suggest improvements
- Share your projects built with this skill

## 📄 License

Open source and free to use.

## 🙏 Credits

Created with ❤️ for the Claude AI community.

Built using:
- [Tailwind CSS](https://tailwindcss.com)
- [Inter Font](https://rsms.me/inter/)
- [Claude AI](https://claude.ai)

---

**Demo**: [View Live Demo](#) (Update after deployment)  
**Download**: [minimal-design-system.skill](minimal-design-system.skill)  
**Support**: Open an issue or contact via email

## 📮 Feedback

Found a bug or have a feature request? We'd love to hear from you!

---

Made with minimal design and maximum care 🖤🤍
