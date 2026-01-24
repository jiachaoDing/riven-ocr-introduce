# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **landing page repository** for the Riven OCR Assistant browser extension - a Chrome extension designed for Warframe players to automate the process of listing "Riven Mods" (紫卡) on warframe.market.

**Key Context:**
- This is NOT the extension source code - it's the marketing/landing page
- The actual extension is built with TypeScript + Vite using Chrome Extension Manifest V3
- The extension uses OCR to recognize Riven Mod attributes from screenshots and auto-fills warframe.market auction forms
- Backend OCR service runs at IP: 49.234.200.196:80

## Repository Structure

```
riven-ocr-introduce/
├── index.html          # Main landing page (Chinese)
├── privacy.html        # Privacy policy page (English)
├── readme.md           # Project background (Chinese)
├── riven-pic/          # Riven Mod card images for showcase
│   ├── rivenCard1.png
│   ├── rivenCard2.png
│   └── rivenCard3.png
└── nul                 # Untracked file (likely accidental)
```

## Technology Stack

- **Pure HTML/CSS/JavaScript** - No build process required
- **Tailwind CSS** - Loaded via CDN (https://cdn.tailwindcss.com)
- **Font Awesome 6.4.0** - For icons
- **Google Fonts** - Inter & JetBrains Mono

## Development Workflow

### Viewing the Site Locally

Simply open `index.html` in a browser. No build step or local server required.

### Deployment

This appears to be deployed as a static site. Changes are committed directly to the main branch.

### Making Changes

1. **Styling**: All custom styles are inline in `<style>` tags within each HTML file
2. **Content**: Edit HTML directly - the site uses Chinese for the main page, English for privacy policy
3. **Images**: Riven card images are in `riven-pic/` directory

## Important Links

- **Chrome Web Store**: https://chromewebstore.google.com/detail/jcjmejcbdiieeamgblajbkndppkbgmkn
- **Privacy Policy**: Accessible at `/privacy.html`
- **Target Website**: warframe.market (where the extension operates)

## Design System

### Color Scheme
- Background: `#030712` (dark)
- Text: `#f3f4f6` (light gray)
- Gradient: Blue (#3b82f6) → Purple (#8b5cf6) → Pink (#d946ef)

### Key CSS Classes
- `.tech-gradient` - Blue-purple-pink gradient
- `.glass-card` - Glassmorphism effect with backdrop blur
- `.glow-text` - Text with blue glow shadow
- `.riven-card-float` / `.riven-card-float-delayed` - Floating animations for showcase cards

## Content Guidelines

### Language
- **index.html**: Chinese (Simplified) - target audience is Chinese Warframe players
- **privacy.html**: English - standard privacy policy format
- **readme.md**: Chinese - project documentation

### Key Messaging
1. **Pain Point**: Manual data entry for Riven Mods is tedious and error-prone
2. **Solution**: OCR + auto-fill = instant listing
3. **Features**: Smart OCR, one-click auto-fill, market price lookup
4. **Workflow**: Screenshot → Auto-recognize → One-click upload

## Privacy & Security Notes

When editing privacy.html, maintain these key points:
- Images sent to OCR backend are NOT permanently stored
- No personal information collected
- No tracking or browsing history collection
- Data transmission uses HTTPS encryption
- Extension permissions limited to: storage, warframe.market, OCR API

## Common Tasks

### Update Extension Download Link
The Chrome Web Store link appears in multiple places:
- Navigation bar (line 96 in index.html)
- Hero section CTA (line 122 in index.html)

### Update Riven Card Images
Replace images in `riven-pic/` directory and update references in index.html (lines 134, 139, 144, 215)

### Modify Privacy Policy
Edit `privacy.html` - remember to update "Last Updated" date (line 30)

## Git Workflow

- **Main branch**: `main` (also the default branch for PRs)
- **Commit style**: Chinese commit messages (e.g., "增加链接", "更新页面")
- Recent commits show iterative updates to page content and images
