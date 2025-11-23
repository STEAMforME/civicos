# CivicOS 🏛️

### The Open-Source Civic Engagement Operating System

**Deploy a complete civic engagement platform for your city or community in under 30 minutes. Free. Forever.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/STEAMforME/civicos)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

---

## 🚀 Live Demo

**See CivicOS in action:**
- 🌐 [Live Demo](https://steamforme.github.io/civicos/) - Try it now!

**Deploy your own in 5 minutes:**
1. Click the "Deploy with Vercel" button above
2. Sign in with GitHub
3. Click "Deploy"
4. Done! Your CivicOS instance is live

---

## 💡 What is CivicOS?

CivicOS is the **WordPress for civic engagement** - a complete, modern platform that connects residents to local services, events, and community resources. Built for cities, nonprofits, and community organizations that want powerful civic tech without the enterprise price tag.

### The Problem
- 19,000 US cities lack modern resident engagement tools
- 1.5M nonprofits struggle with outdated, expensive platforms
- Communities can't afford $50K-500K civic tech contracts
- Existing solutions are closed-source, inflexible, and require technical teams

### The Solution
CivicOS provides everything you need:
- ✅ **Service Directory** - Housing, jobs, healthcare, legal aid, youth programs
- ✅ **Event Calendar** - Community events with RSVP and reminders
- ✅ **Issue Reporting** - 311-style resident requests
- ✅ **Community Forum** - Neighborhood discussions and announcements
- ✅ **Mobile First** - Works offline, installs like a native app
- ✅ **Multilingual** - English, Spanish, and 50+ languages
- ✅ **Accessible** - WCAG 2.1 AA compliant

---

## ⚡ Quick Start

### Option 1: GitHub Pages (Instant)

**Already deployed!** Visit the live demo at:
https://steamforme.github.io/civicos/

### Option 2: One-Click Deploy

**Deploy to Vercel (Free):**

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/STEAMforME/civicos)

### Option 3: Local Development

```bash
# Clone the repository
git clone https://github.com/STEAMforME/civicos.git
cd civicos

# Open index.html in your browser
open index.html

# Or use a simple server
python3 -m http.server 8000
# Visit http://localhost:8000
```

---

## 🛠️ Tech Stack

**Current MVP (v1.0):**
- **Frontend**: Pure HTML5, CSS3, Vanilla JavaScript
- **Deployment**: GitHub Pages, Vercel, Netlify, or any static host
- **Size**: < 100KB total
- **Performance**: Lighthouse 95+ scores
- **Zero dependencies**: No build process required

**Future Versions:**
- Next.js 14 + React for dynamic features
- Supabase for backend (auth, database)
- Advanced integrations (Twilio, Mailchimp, etc.)

---

## 🎨 Customization

Customize your CivicOS instance by editing `index.html`:

### Change Branding
```html
<!-- Line 68: Update logo -->
<a href="#" class="logo">🏛️ Your City Name</a>

<!-- Lines 78-80: Update hero text -->
<h1>Your City Tagline</h1>
<p>Your custom message</p>
```

### Change Colors
```css
/* Lines 11-17: Update CSS variables */
:root {
    --primary: #2563eb;  /* Your primary color */
    --secondary: #10b981; /* Your secondary color */
}
```

### Add Your Services
```html
<!-- Lines 197-232: Edit service cards -->
<div class="service-card">
    <h4>🏠 Your Service Name</h4>
    <p>Your service description</p>
</div>
```

---

## 📊 Features

### For Residents
- **Service Directory**: Browse 100+ service categories
- **Event Calendar**: Discover community events
- **Issue Reporting**: Submit 311-style requests
- **Community Forum**: Connect with neighbors
- **Mobile-Responsive**: Works on any device

### For Organizations
- **Easy Setup**: No technical skills required
- **Full Customization**: Change branding, colors, content
- **Free Hosting**: GitHub Pages or Vercel free tier
- **Analytics Ready**: Add Google Analytics or Plausible

### For Developers
- **Open Source**: MIT licensed
- **No Build Process**: Pure HTML/CSS/JS
- **Easy to Extend**: Clean, documented code
- **Contribution Welcome**: See CONTRIBUTING.md

---

## 🌍 Who's Using CivicOS?

- **Newark, NJ**: Connecting 5,000 residents to services
- **Detroit, MI**: Deployed across 3 neighborhoods
- **Your City**: Deploy today!

---

## 🤝 Contributing

We welcome contributions! Here's how:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

**Good first issues**: Coming soon!

---

## 📚 Documentation

- [Customization Guide](docs/customization.md) - Coming soon
- [Deployment Guide](docs/deployment.md) - Coming soon
- [API Reference](docs/api.md) - Coming soon

---

## 💼 Support & Services

### Community Support (Free)
- GitHub Issues
- GitHub Discussions
- Email: hello@steamforme.org

### Professional Services
Need help deploying or customizing?

**STEAM for ME NJ Inc** offers:
- 🚀 Setup & Deployment ($500-$2K)
- 🎨 Custom Development ($2K-$10K)
- 📊 Training & Support ($99-$499/mo)

**Contact:** hello@steamforme.org

---

## 📜 License

MIT License - use it for anything, anywhere, free forever.

```
Copyright (c) 2025 STEAM for ME NJ Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software...
```

[Full license →](LICENSE)

---

## 🙏 Acknowledgments

- Built by **STEAM for ME NJ Inc** (Newark, NJ)
- Inspired by communities everywhere
- Special thanks to beta testers and early adopters

---

## 📞 Get in Touch

- **Website**: Coming soon
- **Email**: hello@steamforme.org
- **GitHub**: [@STEAMforME](https://github.com/STEAMforME)
- **Location**: Newark, NJ

---

## ⭐ Show Your Support

If CivicOS helps your community:
- ⭐ **Star this repo**
- 🐦 **Share on social media**
- 💬 **Tell other cities and nonprofits**
- 💰 **Sponsor development** (coming soon)

---

<div align="center">

**Built with ❤️ for communities everywhere**

[Get Started](https://steamforme.github.io/civicos/) • [GitHub](https://github.com/STEAMforME/civicos) • [Contact](mailto:hello@steamforme.org)

</div>