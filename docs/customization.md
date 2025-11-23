# CivicOS Customization Guide

Make CivicOS truly yours with these customization options.

## 🎨 Branding

### Logo and City Name

Edit `index.html` line 68:

```html
<!-- Current -->
<a href="#" class="logo">🏛️ CivicOS</a>

<!-- Change to -->
<a href="#" class="logo">
    <img src="logo.png" alt="Your City" style="height: 40px;">
    Your City Name
</a>
```

### Color Scheme

Edit CSS variables (lines 11-17):

```css
:root {
    --primary: #2563eb;      /* Main brand color */
    --primary-dark: #1e40af; /* Darker shade for hover */
    --secondary: #10b981;    /* Accent color */
    --text: #1f2937;         /* Primary text */
    --text-light: #6b7280;   /* Secondary text */
    --bg: #ffffff;           /* Background */
    --bg-alt: #f9fafb;       /* Alternate background */
    --border: #e5e7eb;       /* Borders */
}
```

**Example - Newark Orange & Blue:**
```css
:root {
    --primary: #FF6600;      /* Newark orange */
    --primary-dark: #CC5200;
    --secondary: #003366;    /* Newark blue */
}
```

### Typography

Change fonts (add to `<head>`):

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">

<style>
    body {
        font-family: 'Inter', sans-serif;
    }
</style>
```

## 📋 Content

### Hero Section

Edit lines 78-82:

```html
<h1>Connect Your Community</h1>
<p>Find housing, jobs, healthcare, and community services</p>
```

Change to match your city:

```html
<h1>Welcome to Newark Services</h1>
<p>Your one-stop portal for city services, events, and community resources</p>
```

### Services

Add/edit service cards (lines 197-232):

```html
<div class="service-card">
    <h4>🏠 Housing Assistance</h4>
    <p>Emergency shelter, rental assistance, affordable housing programs</p>
</div>
```

**Add click actions:**
```html
<div class="service-card" onclick="window.location.href='housing.html'">
    <h4>🏠 Housing Assistance</h4>
    <p>Click to browse housing services</p>
</div>
```

### Events

Edit event cards (lines 246-260):

```html
<div class="event-card">
    <div class="event-date">📅 Monday, Nov 25, 2025 | 6:00 PM</div>
    <h4>Community Town Hall</h4>
    <p>Join us for discussion. Location: City Hall</p>
</div>
```

### Footer

Edit footer content (lines 310-325):

```html
<div class="footer-section">
    <h4>Contact</h4>
    <ul>
        <li>Email: your@email.com</li>
        <li>Phone: (555) 123-4567</li>
        <li>City Hall Address</li>
    </ul>
</div>
```

## ⚙️ Features

### Add Search

Add search bar to services section:

```html
<input type="text" id="searchServices" placeholder="Search services..." 
       style="width: 100%; padding: 1rem; margin-bottom: 2rem; border: 1px solid var(--border); border-radius: 0.5rem;">

<script>
document.getElementById('searchServices').addEventListener('input', function(e) {
    const search = e.target.value.toLowerCase();
    document.querySelectorAll('.service-card').forEach(card => {
        const text = card.textContent.toLowerCase();
        card.style.display = text.includes(search) ? 'block' : 'none';
    });
});
</script>
```

### Add Language Selector

```html
<!-- Add to nav -->
<select id="language" style="padding: 0.5rem; border-radius: 0.25rem;">
    <option value="en">English</option>
    <option value="es">Español</option>
</select>

<script>
// Basic language switching
const translations = {
    en: { hero: "Connect Your Community" },
    es: { hero: "Conecta Tu Comunidad" }
};

document.getElementById('language').addEventListener('change', function(e) {
    const lang = e.target.value;
    document.querySelector('.hero h1').textContent = translations[lang].hero;
});
</script>
```

### Add RSS Feed for Events

```html
<script>
fetch('https://your-city.com/events.json')
    .then(r => r.json())
    .then(events => {
        const container = document.querySelector('.events .container');
        events.forEach(event => {
            container.innerHTML += `
                <div class="event-card">
                    <div class="event-date">📅 ${event.date}</div>
                    <h4>${event.title}</h4>
                    <p>${event.description}</p>
                </div>
            `;
        });
    });
</script>
```

## 📱 Mobile Customization

### Add Mobile Menu

```html
<!-- Add to nav -->
<button id="mobileMenuBtn" style="display: none;">☰</button>

<style>
@media (max-width: 768px) {
    #mobileMenuBtn {
        display: block !important;
        background: none;
        border: none;
        font-size: 2rem;
        cursor: pointer;
    }
    
    .nav-links {
        display: none;
        position: absolute;
        top: 100%;
        left: 0;
        right: 0;
        background: white;
        flex-direction: column;
        padding: 1rem;
        box-shadow: var(--shadow);
    }
    
    .nav-links.active {
        display: flex !important;
    }
}
</style>

<script>
document.getElementById('mobileMenuBtn').addEventListener('click', function() {
    document.querySelector('.nav-links').classList.toggle('active');
});
</script>
```

## 🔌 Integrations

### Google Maps for Locations

```html
<iframe 
    width="100%" 
    height="400" 
    frameborder="0" 
    style="border:0; border-radius: 0.5rem; margin: 2rem 0;"
    src="https://www.google.com/maps/embed?pb=YOUR_EMBED_CODE"
    allowfullscreen>
</iframe>
```

### Social Media Links

Add to footer:

```html
<div class="footer-section">
    <h4>Follow Us</h4>
    <div style="display: flex; gap: 1rem; font-size: 1.5rem;">
        <a href="https://facebook.com/yourpage">📘</a>
        <a href="https://twitter.com/yourpage">🐦</a>
        <a href="https://instagram.com/yourpage">📷</a>
    </div>
</div>
```

### Newsletter Signup

```html
<div style="background: var(--primary); color: white; padding: 2rem; text-align: center; margin: 2rem 0; border-radius: 0.75rem;">
    <h3>Stay Updated</h3>
    <p>Get weekly updates on services and events</p>
    <form style="display: flex; gap: 0.5rem; max-width: 400px; margin: 1rem auto;">
        <input type="email" placeholder="Your email" style="flex: 1; padding: 0.75rem; border: none; border-radius: 0.25rem;">
        <button type="submit" class="btn btn-secondary">Subscribe</button>
    </form>
</div>
```

## 🌐 Advanced

### Progressive Web App (PWA)

Create `manifest.json`:

```json
{
  "name": "CivicOS - Your City",
  "short_name": "CivicOS",
  "start_url": "/",
  "display": "standalone",
  "background_color": "#ffffff",
  "theme_color": "#2563eb",
  "icons": [
    {
      "src": "icon-192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "icon-512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ]
}
```

Link in `<head>`:

```html
<link rel="manifest" href="manifest.json">
<meta name="theme-color" content="#2563eb">
```

### Service Worker (Offline Support)

Create `sw.js`:

```javascript
self.addEventListener('install', (e) => {
    e.waitUntil(
        caches.open('civicos-v1').then((cache) => {
            return cache.addAll([
                '/',
                '/index.html',
                '/manifest.json'
            ]);
        })
    );
});

self.addEventListener('fetch', (e) => {
    e.respondWith(
        caches.match(e.request).then((response) => {
            return response || fetch(e.request);
        })
    );
});
```

Register in `<script>`:

```javascript
if ('serviceWorker' in navigator) {
    navigator.serviceWorker.register('/sw.js');
}
```

## 👨‍💻 Developer Tips

### Use Version Control

```bash
git add .
git commit -m "Customize for Newark deployment"
git push
```

### Test Locally

```bash
python3 -m http.server 8000
# Visit http://localhost:8000
```

### Validate HTML

Use [validator.w3.org](https://validator.w3.org/)

### Check Accessibility

Use Lighthouse in Chrome DevTools

## ❓ Questions?

- Email: hello@steamforme.org
- GitHub Issues: Report bugs or request features
- Professional customization: $2K-$10K

---

**Make it yours! 🎨**