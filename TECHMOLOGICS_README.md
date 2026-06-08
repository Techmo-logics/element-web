# Techmologics Element Web Customization

## Overview
This branch contains all branding customizations to transform Element Web into **Techmologics Collaborate** - a secure collaboration platform for the company.

## What's Included

### 📁 Configuration Files
- `techmologics-config.json` - Centralized branding and company configuration
- `res/themes/techmologics-branding.json` - Theme color definitions

### 🎨 Styling Files
- `res/css/themes/_techmologics.pcss` - Main theme stylesheet with Techmologics colors
- `res/css/themes/_techmologics_auth.pcss` - Login and welcome page styling

### 📚 Documentation
- `TECHMOLOGICS_BRANDING_GUIDE.md` - Complete customization guide
- `scripts/setup-techmologics.sh` - Automated setup script

### 🎯 Branding Details

**Company**: TECHMOLOGICS INNOVATIONS PRIVATE LIMITED  
**App Name**: Techmologics Collaborate  
**Website**: https://techmologics.com  
**Tagline**: Collaborate | Innovate | Scale

#### Color Palette
| Element | Color | Hex Code |
|---------|-------|----------|
| Primary | Red/Orange | #FF6B6B |
| Primary Dark | Dark Red | #E63946 |
| Accent | Green | #27AE60 |
| Background | Black | #0F0F0F |
| Text | White | #FFFFFF |

## Getting Started

### Prerequisites
- Node.js >= 22.18
- pnpm >= 11.2.2
- Git

### Setup Instructions

1. **Clone and Navigate**
```bash
git clone https://github.com/Techmo-logics/element-web.git
cd element-web
git checkout customization/techmologics-branding
```

2. **Run Setup Script**
```bash
chmod +x scripts/setup-techmologics.sh
./scripts/setup-techmologics.sh
```

3. **Add Logo Assets**
Place these files in `apps/web/res/img/`:
- `techmologics-logo.svg` (recommended size: 256x256px)
- `techmologics-favicon.ico` (16x16px, 32x32px, 48x48px)
- `techmologics-logo-full.svg` (full logo with text)

4. **Build the Application**
```bash
pnpm install
pnpm -C apps/web build
```

5. **Start Development Server**
```bash
pnpm -C apps/web start
```

6. **Build Desktop App (Optional)**
```bash
pnpm -C apps/desktop build
```

## File Structure

```
element-web/
├── apps/
│   ├── web/
│   │   ├── res/
│   │   │   ├── img/
│   │   │   │   ├── techmologics-logo.svg
│   │   │   │   ├── techmologics-favicon.ico
│   │   │   │   └── techmologics-logo-full.svg
│   │   │   ├── css/
│   │   │   │   └── themes/
│   │   │   │       ├── _techmologics.pcss
│   │   │   │       └── _techmologics_auth.pcss
│   │   │   └── themes/
│   │   │       └── techmologics-branding.json
│   │   ├── techmologics-config.json
│   │   └── index.html
│   └── desktop/
│       └── package.json
├── scripts/
│   └── setup-techmologics.sh
├── TECHMOLOGICS_BRANDING_GUIDE.md
└── README.md
```

## Customization Options

### Update Company Information
Edit `techmologics-config.json`:
```json
{
  "company": {
    "name": "TECHMOLOGICS",
    "website": "https://techmologics.com",
    "supportEmail": "support@techmologics.com"
  }
}
```

### Change Color Scheme
Edit color values in `res/themes/techmologics-branding.json` and `_techmologics.pcss`

### Customize Welcome Message
Update the welcome text in `_techmologics_auth.pcss` and HTML templates

## Deployment

### Web Deployment
1. Build the application
2. Deploy `dist/` folder to your hosting server
3. Configure environment variables for your Matrix homeserver

### Docker Deployment
```bash
# Build Docker image
docker build -f Dockerfile -t techmologics-chat .

# Run container
docker run -p 80:80 techmologics-chat
```

### Configuration for Production

Create an `.env.production` file:
```
VITE_APP_NAME=Techmologics Collaborate
VITE_HOME_SERVER_URL=https://your-matrix-server.com
VITE_IDENTITY_SERVER_URL=https://vector.im
```

## Maintenance & Updates

### Keeping Upstream Updates
To merge new Element Web updates:
```bash
git fetch upstream
git rebase upstream/develop
# Resolve any conflicts in customization files
pnpm -C apps/web build
```

### Rolling Back Changes
```bash
git checkout develop
git branch -D customization/techmologics-branding
```

## Browser Support
- Chrome/Chromium (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Testing

### Unit Tests
```bash
pnpm -C apps/web test
```

### Playwright E2E Tests
```bash
pnpm -C apps/web test:playwright
```

### Build Verification
```bash
pnpm -C apps/web build
pnpm -C apps/web start
```

## Troubleshooting

### Build Fails
- Clear cache: `rm -rf node_modules pnpm-lock.yaml && pnpm install`
- Check Node version: `node --version` (should be >= 22.18)

### Logo Not Showing
- Verify files exist in `apps/web/res/img/`
- Check file names match exactly
- Ensure SVG files are properly formatted

### Colors Not Applied
- Clear browser cache
- Rebuild application: `pnpm -C apps/web build`
- Check CSS file is imported in main styles

### Matrix Connection Issues
- Verify homeserver URL in `.env` or config
- Check network connectivity
- Review browser console for errors

## Support

For issues or questions:
- 📧 Email: support@techmologics.com
- 🌐 Website: https://techmologics.com
- 📖 Documentation: See `TECHMOLOGICS_BRANDING_GUIDE.md`

## License

This customization is based on Element Web, which is licensed under AGPL v3.0. See LICENSE files in repository for details.

---

**Branch**: customization/techmologics-branding  
**Last Updated**: June 8, 2026  
**Status**: Ready for Production

