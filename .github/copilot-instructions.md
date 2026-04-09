---
name: "Think with Abhinav Portfolio"
description: "Portfolio website context. Use when: answering questions about site structure, suggesting improvements, fixing styling/layout issues, adding features to the portfolio"
---

# Think with Abhinav — Portfolio Site Context

## Project Overview
A modern, responsive portfolio website showcasing Abhinav Pratap Singh's professional profile, experience, and skills. Built with vanilla HTML/CSS/JavaScript with no external dependencies.

**Location**: `c:\Users\Abhinav\Documents\Websites\Thinkwithabhinav`  
**Main File**: `index.html` (single-page architecture with embedded CSS/JS)

## Site Architecture

### Sections
1. **Navbar** (fixed, 66px height)
   - Logo with gradient text: "Think with Abhinav"
   - Navigation links: About, Experience, Skills, Contact
   - CTA button: "Reach me →"
   - Active link indicator on scroll

2. **Hero Section** (min-height: 100vh)
   - Badge: "Open to Opportunities · Class of 2025"
   - Title: Name with gradient styling on second line
   - Subtitle: "Media + Tech Learner · Building Real Things"
   - Description paragraph
   - Tags: Skills/interests (color-coded: orange, blue, purple, green)
   - Buttons: Primary CTA + Secondary
   - Photo: 300x340px with morphing background shape
   - Floating cards with animated stats

3. **Stats Bar**
   - 4 key metrics: 76K+ YouTube Views, 40+ Shorts, 2+ Years, 3+ Tech Domains
   - Dividers between stats

4. **About Section**
   - Main text on left (grid 1.1fr)
   - Info rows (Location, Education, etc.) with hover effects
   - Right stack: 3 cards with icons (Learner, Creator, Builder)

5. **Experience Section**
   - 2-column grid of experience cards
   - Color-coded icons (orange, blue, green, purple)
   - Period badges, role, organization, description, tags

6. **Skills Section**
   - 3-column grid of skill categories
   - Header with icon, category name, subcategory
   - Skill pills with color coding
   - Hover animations

7. **Contact Section**
   - Left: Intro text + contact links (Email, LinkedIn, GitHub, Twitter)
   - Right: Contact form (name, email, message)
   - Powered by Web3Forms API

8. **Footer**
   - Name, social links, copyright

## Design System

### Colors (CSS Variables)
```
--bg: #f6f7f9 (light background)
--white: #ffffff
--ink: #0d0f18 (dark text)
--ink2: #1e2235 (secondary dark)
--muted: #64748b (tertiary)
--border: #e2e8f0
--orange: #f97316 (primary accent)
--blue: #3b82f6 (secondary)
--green: #10b981 (tertiary)
--purple: #8b5cf6 (accent)
--grad: Linear gradient (orange → red → purple)
--grad2: Linear gradient (blue → purple)
```

### Typography
- **Display**: Syne (800 weight for headers, 600 for subheads)
- **Body**: Nunito (400-700 weights)
- Responsive sizing with `clamp()` for hero title and section titles

### Spacing & Sizing
- **Page padding**: 5vw (horizontal)
- **Section padding**: 6rem vertical, 5vw horizontal
- **Max-width**: 1100-1200px containers (centered, margin auto)
- **Gap patterns**: 1rem, 1.3rem, 1.5rem, 5rem depending on context

### Component Classes
- `.btn-primary`: Orange gradient button
- `.btn-secondary`: White button with border
- `.htag`, `.exp-tag`, `.skill-pill`: Color-variant tags
- `.exp-card`, `.skill-card`, `.about-card`: Hover animations (lift + shadow)
- `.reveal`: Scroll-triggered fade-in animation

## Interactive Features

### Animations
- **fadeUp**: Staggered entrance animations (0.1s → 0.68s delays)
- **floatY**: Floating stat cards with 4s cycle
- **morphShape**: Gradient background morphs every 8s
- **pulse**: Animated badge dot
- **reveal.in**: Scroll-triggered fade-in for sections

### JavaScript
- **Intersection Observer**: Triggers `.reveal` class on sections entering viewport
- **Form Submission**: Async POST to Web3Forms API on contact form submit
- **Active Link Highlighting**: Updates navbar links based on scroll position
- **Smooth Scroll**: CSS `scroll-behavior: smooth` on html

### Form Integration
- Contact form uses Web3Forms API
- No backend required; endpoints configured in form HTML
- Success/error states with 3s feedback window

## Responsive Design

### Breakpoint: max-width 900px
- Hero layout: Grid → single column, photo above text, center-aligned
- Hide floating cards
- About/Contact grids: 2 cols → 1 col
- Experience/Skills grids: 2 cols / 3 cols → 1 col
- Form grid: 2 cols → 1 col
- Hide navbar links (mobile optimization pending)

## Content Structure

### Hero Content Areas (omitted in current view)
- `hero-name` with `.line2` gradient (Lines 456-458)
- Hero tags (Lines 462-466)
- Buttons (Lines 468-470)
- Photo + floating cards (Lines 474-478)

### About Content (omitted)
- Descriptive paragraphs about Abhinav
- Info rows with icons
- About cards (Lines 499-531)

### Experience Content (omitted)
- 4+ job/project cards (Lines 543-611)
- Each with icon, period, role, org, description, tags

### Skills Content (omitted)
- 3+ skill categories (Lines 623-662)
- Each category has name, subcategory, 4+ pills

### Contact Content (omitted)
- Contact method cards
- Form fields: Name, Email, Message
- Form action to Web3Forms (Lines 670-718)

## Common Customizations

### To Update Content
1. Find omitted sections (marked with `/* Lines X-Y omitted */`)
2. Replace placeholder text in hero, about, experience, skills, contact sections
3. Update stats in `.stats-bar`

### To Modify Colors
- Edit CSS variables in `:root` block (lines ~13-30)
- All colors referenced via `var(--colorname)`

### To Adjust Spacing
- `.section` padding: 6rem 5vw
- Hero photo size: width 300px, height 340px
- Update gap values in grid layouts

### To Change Typography
- Font family already linked (Syne, Nunito)
- Adjust `clamp()` values in `.hero-name`, `.sec-title` for responsive sizing

## File Dependencies
- Google Fonts: Syne (400-800) + Nunito (300-700 italic)
- CloudFlare Email Decode script (for protected contact link)
- Web3Forms API: `https://api.web3forms.com/submit`

## Browser Compatibility
- CSS Grid, Flexbox, CSS Variables (modern browsers)
- IntersectionObserver API (IE 11 not supported)
- ES6 async/await in form handling

## Performance Notes
- Single HTML file (~800 lines) with embedded styles/scripts
- No build process required
- Optimize: Consider lazy-loading if adding images
- Consider: Preconnect for fonts already in use
