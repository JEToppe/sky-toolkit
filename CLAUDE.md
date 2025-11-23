# CLAUDE.md - AI Assistant Guide for Sky Toolkit

## Project Overview

**Sky Toolkit** is a personal, curated website by Johannes Toppe that serves as a comprehensive guide to sky watching resources. The site focuses on aurora tracking, sunrise/sunset viewing, stargazing, and specific Toronto-area sky watching locations.

**Live Site**: Hosted via GitHub Pages at the repository root
**Purpose**: Single-page resource hub for aurora chasers, sunrise/sunset enthusiasts, and stargazers
**Target Audience**: Toronto-area sky watchers, with emphasis on aurora viewing during the 2024-2025 solar maximum

## Repository Structure

```
/
├── index.html          # Main website (all content in one file)
├── README.md           # Minimal project description
└── CLAUDE.md          # This file (AI assistant guide)
```

### Key Files

#### `index.html` (17,767 bytes)
- **Single-page application** - All HTML, CSS, and content in one file
- **No external dependencies** - Pure HTML/CSS, no JavaScript frameworks
- **Fully self-contained** - No separate CSS or JS files
- **Responsive design** - Mobile-friendly with media queries
- **Sections**:
  1. Header with animated gradient title
  2. Solar Maximum 2024-2025 live banner
  3. Aurora Tracking resources
  4. Sunset & Sunrise Tools
  5. Dark Sky & Stargazing tools
  6. Toronto Sky Spots (sunrise and aurora locations)
  7. Learn & Connect resources
  8. Footer

#### `README.md`
- Minimal file with project tagline only
- Not used for documentation

## Content Structure & Categories

### 1. Aurora Tracking
- **Essential**: My Aurora Forecast & Alerts app (Android/iOS)
- Space Weather Live website
- Ontario Aurora Chasers Facebook group (200,000+ members)

### 2. Sunset & Sunrise Tools
- **Essential**: SunsetHue
- PhotoPills (planning tool)
- Windy.com (cloud cover forecasts)

### 3. Dark Sky & Stargazing
- **Essential**: Light Pollution Map
- Stellarium (web/desktop/mobile)
- Clear Outside (astronomy forecasts)

### 4. Toronto Sky Spots
- **Sunrise locations**: Tommy Thompson Park, Trillium Park East, Dundas/Spadina
- **Aurora/Dark sky**: Torrance Barrens (Dark Sky Preserve), general dark spots via light pollution map

### 5. Learning Resources
- SpaceWeather.com
- TimeandDate Astronomy
- Secret Flying (for aurora chasing travel deals)

## Design & Styling Conventions

### Color Scheme
- **Background**: Gradient from deep blue (`#0a0e27`) through indigo (`#1a237e`) to pink (`#e91e63`)
- **Text**: White (`#ffffff`) with light blue accents (`#b8c5ff`)
- **Cards**: Semi-transparent white overlays with backdrop blur
- **Links**: Light blue (`#64b5f6`) hover to lighter blue (`#90caf9`)
- **Badges**:
  - ESSENTIAL: Orange background (`rgba(255, 152, 0, 0.3)`)
  - COMMUNITY: Purple background (`rgba(103, 58, 183, 0.3)`)
  - NEW: Red background (`rgba(244, 67, 54, 0.3)`)

### Visual Effects
- Animated twinkling stars background (CSS-only animation)
- Fade-in animations for sections
- Hover effects on resource cards (slight translation and background change)
- Pulsing live banner for solar maximum

### Typography
- **Font**: System font stack (`-apple-system, BlinkMacSystemFont, 'Segoe UI'...`)
- **H1**: 2.5em with gradient text effect
- **H2**: 1.5em
- **Body**: 1.6 line height for readability

### Layout
- **Container**: Max-width 600px, centered
- **Grid**: Auto-fit grid for location cards (min 200px)
- **Mobile-first**: Responsive design with breakpoint at 600px

## Development Workflows

### Making Content Changes

1. **Adding a new resource**:
   - Duplicate an existing `.resource-card` div in the appropriate section
   - Update `.resource-title`, `.resource-description`, and `.resource-link`
   - Add badge if needed: `<span class="badge essential">ESSENTIAL</span>`

2. **Adding a new section**:
   - Copy entire `.section` div structure
   - Update section icon (emoji) and title
   - Add resource cards or custom content

3. **Updating Toronto locations**:
   - Modify `.spot-card` divs within the grid structure
   - Keep `.spot-name` and `.spot-detail` classes

4. **Changing live banner** (e.g., when solar maximum ends):
   - Update `.live-banner` content or remove entire div

### Styling Changes

- **All styles are inline** in the `<style>` tag (lines 7-260)
- Maintain existing CSS variable patterns for consistency
- Test animations by checking keyframe definitions
- Preserve backdrop-filter and rgba transparency for glass-morphism effect

### Git Workflow

**Branch Strategy**:
- Main branch: Production (GitHub Pages source)
- Feature branches: `claude/*` prefix for AI-assisted changes

**Commit Guidelines**:
- Be descriptive: "Add Stellarium web version link" not "Update index.html"
- Reference line numbers for small changes: "Fix typo in Aurora section (line 283)"
- Group related changes: "Update all Toronto sunrise locations"

**Push Process**:
```bash
git add index.html
git commit -m "Descriptive message"
git push -u origin <branch-name>
```

**Important**: Branch names starting with 'claude/' require matching session IDs to push successfully.

## Code Conventions & Best Practices

### HTML Structure
- **Keep it simple**: No unnecessary divs or wrappers
- **Semantic elements**: Use `<header>`, `<footer>`, `<section>` appropriately
- **Accessibility**: Include `alt` text if images are added, ensure links have descriptive text
- **External links**: Always use `target="_blank"` for external resources

### CSS Practices
- **No !important**: Avoid using !important declarations
- **Consistent spacing**: Use 15-30px margins between cards, 40-60px between sections
- **Animation timing**: Keep animations between 1-3s for smoothness
- **Mobile-first**: Add mobile styles in media queries, not vice versa

### Content Guidelines
- **Tone**: Personal, enthusiastic, but informative
- **Descriptions**: 2-3 sentences max per resource
- **Links**: Use descriptive link text ("Visit Website →", "Learn More →")
- **Badges**: Use sparingly - only for truly essential tools or new additions
- **Emojis**: One per section header, none in body text

### Performance
- **No external requests**: Keep everything self-contained
- **Optimize animations**: Use CSS transforms instead of position changes
- **Image considerations**: If adding images, compress and use modern formats (WebP)

## Common Tasks

### Task: Update aurora forecast app links
**Location**: Lines 281-288 in index.html
**Process**: Update `href` attributes for Android/iOS links

### Task: Add new sky watching tool
**Template**:
```html
<div class="resource-card">
    <div class="resource-title">Tool Name <span class="badge essential">ESSENTIAL</span></div>
    <div class="resource-description">
        Brief description of the tool and its main features.
    </div>
    <a href="https://example.com" class="resource-link" target="_blank">Visit Website →</a>
</div>
```

### Task: Update member count for community groups
**Location**: Line 301 (Ontario Aurora Chasers)
**Note**: Keep numbers accurate - it's a credibility marker

### Task: Change seasonal banner
**Location**: Lines 269-272 (live banner)
**Consider**: Remove entirely if no current event, or update for meteor showers, eclipses, etc.

### Task: Add new Toronto location
**Template**:
```html
<div class="spot-card">
    <div class="spot-name">Location Name</div>
    <div class="spot-detail">Brief description and viewing conditions</div>
</div>
```

## Testing Checklist

Before committing changes:
- [ ] Open index.html in browser (locally or via GitHub Pages)
- [ ] Test all new/modified links (should open in new tabs)
- [ ] Check mobile view (resize browser to <600px)
- [ ] Verify animations work smoothly
- [ ] Ensure no horizontal scroll on mobile
- [ ] Check text contrast/readability
- [ ] Validate HTML if major changes (https://validator.w3.org/)

## Things to AVOID

### Content
- ❌ Don't add resources without personal recommendation or clear value
- ❌ Don't remove existing resources without understanding their importance
- ❌ Don't change the personal tone to corporate/formal
- ❌ Don't add affiliate links or monetization
- ❌ Don't add tracking scripts or analytics without explicit request

### Technical
- ❌ Don't split into multiple files (keep single-page architecture)
- ❌ Don't add JavaScript unless absolutely necessary
- ❌ Don't add external dependencies (no CDN links, no frameworks)
- ❌ Don't use tables for layout
- ❌ Don't add build processes or compilation steps
- ❌ Don't change font families (stick to system fonts)

### Style
- ❌ Don't drastically change color scheme (maintain aurora/sky theme)
- ❌ Don't remove animations (they're core to the experience)
- ❌ Don't add too many badges (dilutes "essential" meaning)
- ❌ Don't make text too small (<0.8em body text)
- ❌ Don't add auto-playing media

## Deployment

**Platform**: GitHub Pages
**Source**: Root of main branch
**URL Pattern**: `https://<username>.github.io/<repo-name>/`
**Process**: Automatic deployment on push to main branch
**Delay**: ~2-5 minutes after merge

### Pre-deployment Checklist
- [ ] All links tested and working
- [ ] Mobile responsiveness verified
- [ ] No console errors in browser
- [ ] Animations perform well
- [ ] Content is accurate and up-to-date

## Future Enhancement Ideas

If the user requests improvements, consider:
- Dark mode toggle (currently always dark)
- Location-based resource filtering
- Embed real-time KP index widget
- Photo gallery section
- Equipment recommendations section
- Calendar integration for celestial events
- Printable field guide version

## Context for AI Assistants

### Project Maturity
- **Stage**: Mature, published website
- **Maintenance**: Content updates more likely than structural changes
- **Stability**: Preserve existing functionality unless explicitly changing

### User Intent Recognition
- **"Add resource"** → Use resource-card template
- **"Fix link"** → Find and update href attribute
- **"Update colors"** → Modify style section, maintain theme
- **"Make it responsive"** → Already responsive, likely means improve mobile
- **"Add JavaScript"** → Question necessity first
- **"Optimize"** → Performance is already good, clarify what to optimize

### Communication Style
- Be concise and direct
- Reference specific line numbers when making changes
- Explain impact of changes (e.g., "This will affect mobile view")
- Ask for clarification on subjective changes (colors, content removal)
- Provide preview descriptions of visual changes

## Quick Reference

**Total lines in index.html**: 454
**Style section**: Lines 7-260
**Content sections**: Lines 263-451
**Resource cards**: Use class `.resource-card`
**Location cards**: Use class `.spot-card`
**Badges**: `.badge`, `.badge.essential`, `.badge.new`

---

**Last Updated**: 2025-11-23
**Repository**: sky-toolkit
**Maintainer**: Johannes Toppe
**AI Assistant**: Follow this guide for consistent, high-quality contributions to the project.
