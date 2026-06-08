# Techmologics Element Web Customization Guide

This document outlines all the customization changes made to rebrand Element Web as **Techmologics Collaborate**.

## Overview
- **Company**: TECHMOLOGICS INNOVATIONS PRIVATE LIMITED
- **App Name**: Techmologics Collaborate
- **Tagline**: Collaborate | Innovate | Scale
- **Website**: https://techmologics.com

## Branding Details

### Color Scheme
- **Primary Color**: #FF6B6B (Red/Orange)
- **Primary Dark**: #E63946 (Darker Red)
- **Accent Color**: #27AE60 (Green)
- **Background**: #0F0F0F (Dark/Black)
- **Text**: #FFFFFF (White)

### Logo Assets Required
Place the following files in `apps/web/res/img/`:
1. `techmologics-logo.svg` - Main logo (used in sidebar/header)
2. `techmologics-favicon.ico` - Browser tab favicon
3. `techmologics-logo-full.svg` - Full logo with text (login page)

## Files Modified

### 1. Configuration Files
- `apps/web/res/themes/techmologics-branding.json` - Centralized branding config

### 2. HTML & Metadata
- `apps/web/index.html` - Update page title, meta tags
- `apps/web/public/index.html` - Update meta descriptions

### 3. Styling
- `apps/web/res/css/themes/_techmologics.pcss` - Custom theme stylesheet
- Update primary/accent colors in main CSS

### 4. Application Metadata
- `apps/web/package.json` - Update app name and description
- `apps/desktop/package.json` - Update desktop app branding

### 5. UI Strings (Localization)
- `apps/web/src/i18n/strings/en_EN.json` - Update UI strings and company references

### 6. Login/Welcome Pages
- Update splash screen with Techmologics branding
- Customize welcome message

## Implementation Steps

### Step 1: Add Logo Assets
1. Download/prepare Techmologics logos in SVG format
2. Place in `apps/web/res/img/` directory
3. Ensure logo files are optimized

### Step 2: Update HTML Files
Update the page titles and meta tags in your HTML files:

```html
<title>Techmologics Collaborate - Secure Communication</title>
<meta name="description" content="Techmologics Collaborate: An IT Services Innovation Partner - Powering Business with Technology">
<meta name="theme-color" content="#FF6B6B">
```

### Step 3: Configure Theme Colors
The theme colors are defined in `techmologics-branding.json`. This file is referenced by the build system to generate themed CSS.

### Step 4: Update Package Information
- Update `productName` in `apps/desktop/package.json`
- Update `name` and `description` in `apps/web/package.json`

### Step 5: Build & Test
```bash
# Install dependencies
pnpm install

# Build the web app
pnpm -C apps/web build

# Test the desktop app
pnpm -C apps/desktop start
```

## Deployment

### Web Deployment
The customized web app will be available at your deployment URL with:
- Techmologics branding throughout
- Custom colors and logos
- Company-specific messaging

### Environment Configuration
Update your `.env` configuration if needed:
```
VITE_APP_NAME=Techmologics Collaborate
VITE_COMPANY_NAME=TECHMOLOGICS
```

## Additional Customizations (Optional)

### 1. Custom Welcome Message
Edit welcome screens to include Techmologics messaging

### 2. Room Creation Templates
Pre-populate default rooms:
- #announcements
- #general
- #engineering
- #marketing

### 3. Email Templates
Customize email invitations with Techmologics branding

### 4. Documentation
Update references from "Element" to "Techmologics Collaborate"

## Support & Maintenance

### Future Updates
When updating Element Web from upstream:
1. Check for conflicts in branding files
2. Test theme rendering
3. Verify logo display
4. Test across browsers/devices

### Rollback
To revert to Element branding:
```bash
git checkout develop
git branch -D customization/techmologics-branding
```

## Checklist for Complete Customization

- [ ] Logo files placed in `apps/web/res/img/`
- [ ] HTML meta tags updated
- [ ] Theme colors applied
- [ ] Package.json files updated
- [ ] UI strings localized (if needed)
- [ ] CSS theme file created/updated
- [ ] Build tested successfully
- [ ] Deployment verified
- [ ] Cross-browser testing completed
- [ ] Mobile responsiveness verified

## Contact

For questions about this customization, contact:
- **Email**: support@techmologics.com
- **Website**: https://techmologics.com

---

**Last Updated**: June 8, 2026
**Branch**: customization/techmologics-branding
