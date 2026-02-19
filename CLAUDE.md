# CLAUDE.md — Durand Future Health Website

## Overview

This is the **Durand Future Health (DFH)** marketing website, live at **https://www.durand.life**. It's a single-page HTML site with tab-based navigation, targeting three audiences: Benefits Brokers, Employers, and Individuals (Consumers).

## What DFH Does

Durand Future Health is a healthcare innovation company offering **EHAP** (Employee Health and Assistance Plan) — an advanced replacement for traditional EAPs (Employee Assistance Programs). Key offerings:

- **Predictive health testing**: Multi-omics, epigenetics, proteomics via home-based blood test (peel-and-stick, no nurse visit)
- **AI-powered health intelligence**: Risk assessment across 40+ organ systems, 5–10 year forward-looking detection
- **Personalized health coaching**: AI + human (6 coaching sessions with a dedicated health professional)
- **Care navigation**: Weight loss, menopause, pain management, hormonal health
- **Distribution model**: PEPM (Per Employee Per Month) through brokers and insurers at $3–5 PEPM

## Tech Stack

- **Single HTML file**: `index.html` (everything — HTML, CSS, JS — in one file)
- **Fonts**: Fraunces (serif, headings) + Inter (sans-serif, body) via Google Fonts
- **Hosting**: Vercel, auto-deploys from this GitHub repo (`DFHprb/durand-website`)
- **Domain**: durand.life (DNS via Netfirms, pointed to Vercel)
- **No build step**: Just push to `main` and Vercel deploys

## How to Deploy

```bash
# 1. Make your changes to index.html
# 2. Commit and push
git add index.html
git commit -m "Description of changes"
git push

# Vercel auto-deploys within ~30 seconds
```

**IMPORTANT**: Asset paths in `index.html` must use ROOT-LEVEL paths (e.g., `src="logo.svg"`), NOT `src="assets/logo.svg"`. The repo serves from root.

## Site Architecture

### Tab-Based Navigation

The site uses a JavaScript `showPanel()` function to switch between four panels:

| Panel ID | Tab Label | Audience |
|----------|-----------|----------|
| `brokers` | For Brokers | Benefits brokers, consultants |
| `employers` | For Employers | HR, benefits decision-makers |
| `longevity` | Get Tested / $499 | Individual consumers |
| `about` | About | General info |

Each panel has its own:
- **Hero variant** (`#hero-brokers`, `#hero-employers`, `#hero-longevity`, `#hero-about`)
- **Content panel** (`#panel-brokers`, `#panel-employers`, `#panel-longevity`, `#panel-about`)

### Key Sections (Broker Panel — the main one)

1. **Hero**: "Health Care Is Stuck on Break-Fix. We Move It to Prevention."
2. **Trust bar**: 4 stats (3–5% utilization, 40+ organ systems, 5–10yr detection, $0 incremental cost)
3. **Broker value section**: Why brokers should offer EHAP
4. **"Why EHAP, not EAP?" callout**: Teal-bordered explainer block
5. **Comparison table**: Traditional EAP vs EHAP with engagement model + economic impact rows
6. **GLP-1 section**: The GLP-1 crisis and EHAP's prevention approach, includes PEPM math callout ($167 vs $5)
7. **Employee showcase**: Home Depot lady photo + 11-item feature checklist
8. **How It Works**: 4-step process
9. **Contact/Enquiry form**: Sends to support@durand.life

### Key Sections (Employer Panel)

1. **Hero**: "A Better EAP — And So Much More. For No More Money."
2. **Value propositions**: ROI-focused content for HR
3. **Shared sections**: Comparison table, How It Works, Contact form

### Key Sections (Consumer/Get Tested Panel)

1. **Hero**: Personal health testing pitch
2. **Trust bar**: Consumer-specific (Secure AI-Powered Health Intelligence, 40 Languages Supported, Care Navigation)
3. **$499 pricing**: Individual test package
4. **Video section**: YouTube embeds (English + Hindi)

## Brand Guidelines

### Colors (CSS Custom Properties)

```css
--blue-deep: #1B2D6B;   /* Primary dark blue — hero backgrounds, headings */
--blue: #2E5EA8;         /* Secondary blue */
--teal: #2BA5A5;         /* Accent — borders, highlights, callout blocks */
--green: #44B878;        /* CTA buttons (gradient start) */
--lime: #8CC63F;         /* CTA buttons (gradient end), accent text */
--dark: #1a1f36;         /* Body text dark */
--warm: #F8F6F3;         /* Warm background sections */
```

### Gradients

- **Brand gradient**: `linear-gradient(135deg, #1B2D6B 0%, #2BA5A5 50%, #8CC63F 100%)`
- **Hero gradient**: `linear-gradient(135deg, #0a1628 0%, #1B2D6B 30%, #1a5050 70%, #2d5a1a 100%)`
- **CTA buttons**: `linear-gradient(135deg, #44B878, #8CC63F)`

### Typography

- **Headings**: `'Fraunces', Georgia, serif` — font-weight 700–900
- **Body**: `'Inter', -apple-system, sans-serif` — font-weight 300–700
- **Section labels**: 13px uppercase, letter-spacing 2px, teal or lime color

### EHAP Branding — CRITICAL

The product name is **EHAP** (Employee Health and Assistance Plan). Special branding rules:

1. **Always uppercase**: `EHAP` (never "eHAP" or "ehap")
2. **Green H on light/dark backgrounds**:
   ```html
   E<span style="color:#8CC63F;">H</span>AP
   ```
3. **White H on green/teal backgrounds** (to avoid green-on-green):
   ```html
   E<span style="color:#fff; font-weight:800;">H</span>AP
   ```
4. **Apply to ALL instances** of EHAP across the entire site

### Logo

- File: `durand-logo-white.svg` (used in hero/nav on dark backgrounds)
- Additional: `durand-logo.svg` (dark version if needed)

## Content Rules

1. **EHAP stands for**: "Employee Health and Assistance Plan" (always define on first use per section)
2. **PEPM**: Always define as "Per Employee Per Month" on first use
3. **Utilization stat**: "3–5%" (not "3%") — sourced from IFEBP/Gallup
4. **Coaching, not counselling**: "6 coaching sessions with a dedicated health professional" (never "counselling sessions")
5. **No "Coming Soon"**: All features are presented as available
6. **No "AI-Native"**: Use "AI-Powered Health Intelligence" (AI-Native is investor language)
7. **Competitor language**: Soft — "in many cases largely covered by existing insurance" (not aggressive comparisons)
8. **This is a virtual product**: No references to clinics, practitioners, or in-person visits unless discussing care navigation partners

## Images

| File | Description |
|------|-------------|
| `durand-logo-white.svg` | White logo for dark backgrounds |
| `home-depot-lady.jpg` | Retail employee with phone (employee showcase section) |
| `hero-testing.jpg` | Hero image for consumer/testing panel |

## Videos

- **English explainer**: `https://www.youtube.com/embed/X1HbGdDq5-k`
- **Hindi explainer**: `https://www.youtube.com/embed/mG1Lc0J5F6g`

## Contact

- **Email**: support@durand.life (all enquiry forms point here)
- **Company**: Durand Future Health

## Common Tasks

### Adding/Editing Content
1. Open `index.html`
2. Find the relevant panel (search for `id="panel-brokers"` etc.)
3. Make changes
4. Commit and push

### Changing Hero Text
- Search for `id="hero-brokers"` (or employers/longevity/about)
- Each hero variant is inside a `<div class="hero-variant">` block

### Updating Stats/Numbers
- Trust bar stats are in `<div class="trust-bar">` within each panel
- Comparison table is in `<table>` elements within the panel content

### Adding New Sections
- Follow existing pattern: wrap in `<div class="fade-in">` for scroll animation
- Use `section-label` class for uppercase teal/lime labels
- Use existing CSS classes — the site has a comprehensive design system built in

## Team

- **Paven Bratch** — Founder, manages content and strategy
- **Sarah Heyer** (sarah@durandhealth.com) — Site management

## Important Notes

- **Single file**: Everything is in `index.html`. There is no separate CSS or JS file.
- **No framework**: Pure HTML/CSS/JS. No React, no build tools, no npm.
- **Responsive**: Site has media queries for mobile (968px, 640px breakpoints)
- **Scroll animations**: Uses IntersectionObserver with `.fade-in` class
- **DNA helix**: SVG animation in hero with floating labels that cycle through health metrics
- **Form submissions**: Currently uses `mailto:` links (no backend form handler yet)
