# CivicOS Deployment Guide

CivicOS can be deployed in multiple ways. Choose the option that best fits your needs.

## 🚀 Quick Deployment Options

### 1. GitHub Pages (Recommended for Beginners)

**Cost:** Free  
**Time:** 2 minutes  
**Best for:** Quick demos, personal projects

**Steps:**
1. Fork this repository
2. Go to Settings > Pages
3. Select "main" branch as source
4. Click Save
5. Your site will be live at `https://yourusername.github.io/civicos/`

### 2. Vercel (Recommended for Production)

**Cost:** Free tier (plenty for most cities)  
**Time:** 5 minutes  
**Best for:** Production deployments, custom domains

**Steps:**
1. Click [![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/STEAMforME/civicos)
2. Sign in with GitHub
3. Click "Deploy"
4. Done! You get:
   - Custom domain support
   - Automatic SSL
   - Global CDN
   - Analytics

**Add Custom Domain:**
1. Go to Vercel project settings
2. Click "Domains"
3. Add your domain (e.g., `civicos.yourcity.gov`)
4. Update DNS records as instructed

### 3. Netlify

**Cost:** Free tier  
**Time:** 5 minutes  
**Best for:** Teams, form handling

**Steps:**
1. Sign up at [netlify.com](https://netlify.com)
2. Click "New site from Git"
3. Select your forked civicos repository
4. Click "Deploy"

**Features:**
- Form submissions (built-in)
- Custom redirects
- Split testing
- Team collaboration

### 4. Your Own Server

**Cost:** Varies ($5-20/month)  
**Time:** 15-30 minutes  
**Best for:** Full control, government servers

**Requirements:**
- Web server (Apache, Nginx, etc.)
- Domain name
- SSL certificate (free with Let's Encrypt)

**Steps:**
```bash
# Upload files via FTP/SFTP
# Or clone from GitHub
ssh user@yourserver.com
cd /var/www/html
git clone https://github.com/STEAMforME/civicos.git

# Configure your web server
# Point to the civicos directory
```

## ⚙️ Configuration

### Customize Branding

Edit `index.html`:

```html
<!-- Change logo (line ~68) -->
<a href="#" class="logo">🏛️ Your City Name</a>

<!-- Change hero text (lines ~78-80) -->
<h1>Your City Tagline</h1>
<p>Your custom message</p>
```

### Change Colors

Edit CSS variables in `index.html`:

```css
/* Lines 11-17 */
:root {
    --primary: #2563eb;    /* Your primary color */
    --secondary: #10b981;  /* Your secondary color */
    --text: #1f2937;       /* Text color */
}
```

### Add Your Services

Edit service cards (lines ~197-232):

```html
<div class="service-card">
    <h4>🏠 Your Service</h4>
    <p>Service description</p>
</div>
```

### Add Events

Edit event cards (lines ~246-260):

```html
<div class="event-card">
    <div class="event-date">📅 Date | Time</div>
    <h4>Event Title</h4>
    <p>Event description and location</p>
</div>
```

## 📧 Form Integration

The beta form currently logs to console. To receive real submissions:

### Option 1: Formspree (Easiest)

1. Sign up at [formspree.io](https://formspree.io)
2. Create a new form
3. Copy your form endpoint
4. Update JavaScript (line ~333):

```javascript
fetch('https://formspree.io/f/YOUR_FORM_ID', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify(formData)
});
```

### Option 2: Netlify Forms

If deployed on Netlify, add to form tag:

```html
<form netlify name="beta" data-netlify="true">
```

### Option 3: Custom Backend

Connect to your own API endpoint:

```javascript
fetch('https://your-api.com/submissions', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify(formData)
});
```

## 📊 Analytics

### Google Analytics

Add before `</head>`:

```html
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

### Plausible (Privacy-Friendly)

Add before `</head>`:

```html
<script defer data-domain="yourdomain.com" src="https://plausible.io/js/script.js"></script>
```

## 🔒 SSL Certificate

### Vercel/Netlify
Automatic! SSL included free.

### Self-Hosted
Use Let's Encrypt:

```bash
sudo apt install certbot python3-certbot-nginx
sudo certbot --nginx -d yourdomain.com
```

## 🛡️ Security

### Content Security Policy

Add to your web server config or `<head>`:

```html
<meta http-equiv="Content-Security-Policy" content="default-src 'self'; script-src 'self' 'unsafe-inline';">
```

### HTTPS Only

Redirect HTTP to HTTPS in your web server config.

## ✅ Testing

Before going live, test:

- [ ] All links work
- [ ] Forms submit correctly
- [ ] Responsive on mobile
- [ ] Fast loading (< 3 seconds)
- [ ] Accessible (use Lighthouse)
- [ ] Works in all major browsers

## 🎓 Next Steps

1. **Customize content** - Add your city's services and events
2. **Set up form handling** - Connect to Formspree or backend
3. **Add analytics** - Track usage with Google Analytics or Plausible
4. **Share with community** - Tell residents and organizations
5. **Gather feedback** - Improve based on user input

## ❓ Troubleshooting

**Site not loading?**
- Check GitHub Pages is enabled
- Verify DNS records (if custom domain)
- Clear browser cache

**Form not submitting?**
- Check browser console for errors
- Verify form action URL
- Test with simple alert first

**Slow loading?**
- Optimize images (compress, resize)
- Use CDN for assets
- Enable caching

## 📞 Support

Need help?
- Email: hello@steamforme.org
- GitHub Issues: [github.com/STEAMforME/civicos](https://github.com/STEAMforME/civicos)
- Professional setup: $500-$2K (contact us)

---

**Happy deploying! 🚀**