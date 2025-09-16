# Dev Tools Scripts

A collection of development tools and scripts for debugging mobile applications, hosted on Cloudflare Pages.

## 🎯 Purpose

This repository hosts debugging utilities that can be easily included in mobile web applications for development and testing purposes.

## 📁 Repository Structure

```
dev-tools-scripts/
├── public/                          # Cloudflare Pages public directory
│   └── debug/
│       └── mobile-console-interceptor.min.js  # Mobile debug console interceptor
├── mobile-console-interceptor.min.js          # Source file (backup)
├── Task Brief for Agent.md                    # Implementation guide
└── README.md                                  # This file
```

## 🚀 Live URLs

### Production URLs:
- **Cloudflare Pages**: https://dev-tools-scripts.pages.dev/debug/mobile-console-interceptor.min.js
- **Custom Domain**: https://dev-tools.zurielyahav.com/debug/mobile-console-interceptor.min.js

Both URLs serve the same content with:
- ✅ HTTP 200 OK status
- ✅ `application/javascript` content-type
- ✅ Auto-deployment from git pushes

## 🛠️ Tools Included

### Mobile Console Interceptor
**File**: `mobile-console-interceptor.min.js`

A JavaScript utility that intercepts console messages on mobile devices and forwards them to a debug server for remote debugging.

**Features**:
- Captures `console.log`, `console.warn`, `console.error`, `console.info`
- Intercepts JavaScript errors and unhandled promise rejections
- Tracks touch events for mobile interaction debugging
- Supports WebSocket and HTTP fallback for log transmission
- Device and viewport information collection

**Usage**:
```html
<!-- Add to your mobile web app for debugging -->
<script src="https://dev-tools.zurielyahav.com/debug/mobile-console-interceptor.min.js"></script>
```

**Activation**:
- URL parameter: `?debug=on`
- localStorage: `hebrewTrainerDebug=on`

## 🏗️ Infrastructure

### Hosting
- **Platform**: Cloudflare Pages
- **Repository**: https://github.com/zyahav/dev-tools-scripts
- **Auto-deployment**: Enabled from `main` branch
- **Build settings**: 
  - Build command: None
  - Output directory: `public`

### Domain Configuration
- **Primary**: `dev-tools-scripts.pages.dev`
- **Custom**: `dev-tools.zurielyahav.com`
- **SSL**: Automatic via Cloudflare

## 🔧 Development

### Local Development
```bash
# Clone repository
git clone https://github.com/zyahav/dev-tools-scripts.git
cd dev-tools-scripts

# Serve locally (optional)
python -m http.server 8000 --directory public
# Access: http://localhost:8000/debug/mobile-console-interceptor.min.js
```

### Adding New Tools
1. Add files to `public/` directory
2. Commit and push to `main` branch
3. Cloudflare Pages will auto-deploy

### Git Workflow
```bash
# After making changes
git add .
git commit -m "Descriptive commit message"
git push origin main
```

## 📋 Implementation Guide

See `Task Brief for Agent.md` for detailed setup instructions including:
- Repository creation with `gh` CLI
- Cloudflare Pages configuration
- Custom domain setup
- End-to-end verification
- Troubleshooting guide

## ✅ Verification

Test both URLs are working:
```bash
# Check status and headers
curl -I https://dev-tools-scripts.pages.dev/debug/mobile-console-interceptor.min.js
curl -I https://dev-tools.zurielyahav.com/debug/mobile-console-interceptor.min.js

# Verify content
curl -s https://dev-tools.zurielyahav.com/debug/mobile-console-interceptor.min.js | grep -o "console" | head -1
```

## 📝 Notes

- **Auto-deployment**: Changes pushed to `main` branch automatically deploy to both URLs
- **CDN**: Files are served via Cloudflare's global CDN for fast loading
- **Reliability**: Cloudflare Pages provides 99.9% uptime SLA
- **Security**: HTTPS enforced, modern security headers included

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Add your development tools to the `public/` directory
4. Test the URLs work correctly
5. Submit a pull request

---

**Last Updated**: September 2025  
**Status**: ✅ Live and operational
