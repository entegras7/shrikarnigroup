# Shri Karni Group — Website

A multi-page, SEO-optimised static website for Shri Karni Group of Companies.

---

## File Structure

```
shri-karni/
├── index.html                  → Group homepage
├── electrotech/
│   └── index.html              → Shri Karni Electrotech page
├── infrastructure/
│   └── index.html              → Shri Karni Infrastructure page
├── about/
│   └── index.html              → About: Director's message, Vision, Mission, Policies
├── contact/
│   └── index.html              → Contact form (shared across all entities)
├── shared.css                  → All shared styles (one file for all pages)
├── shared.js                   → All shared JavaScript (nav, scroll, FAQ, filters, form)
├── sitemap.xml                 → SEO sitemap — submit to Google Search Console
└── robots.txt                  → Crawl instructions for search engines
```

---

## Customisation Checklist

### 1. Company Identity
- [ ] Replace `[Director Name]` with the actual director's name (all pages)
- [ ] Replace `[Year]` in the hero kicker on homepage with founding year
- [ ] Replace `info@shrikarnigroup.com` with real email addresses
- [ ] Replace `+91 XXXXX XXXXX` with real phone numbers
- [ ] Replace `[Street Address], [City, State — PIN]` with real registered office address
- [ ] Replace `shrikarnigroup.com` with the actual domain name (in all `<link rel="canonical">`, `og:url`, and structured data blocks)

### 2. Homepage Stats (index.html)
- [ ] `XX+ Years of Experience`
- [ ] `XX+ Projects Completed`
- [ ] `XX+ Satisfied Clients`

### 3. Director's Message (about/index.html)
- [ ] Replace placeholder paragraphs with the actual message from the company profile
- [ ] Replace the `[Insert a key quote…]` blockquote with a real quote
- [ ] Upload director photograph → replace the `✦` placeholder div with:
  ```html
  <img src="../assets/director.jpg" alt="[Director Name], Managing Director" class="director-photo" />
  ```

### 4. Vision & Mission (about/index.html)
- [ ] Replace vision statement and bullet points with actual text from company profile
- [ ] Replace mission statement and bullet points with actual text from company profile

### 5. Policies (about/index.html)
- [ ] Replace Quality Policy placeholder text with real policy
- [ ] Replace Environmental Policy placeholder text with real policy
- [ ] Replace Health & Safety Policy placeholder text with real policy
- [ ] Replace HR Policy placeholder text with real policy
- [ ] Add actual policy sign date in each `[Policy Date]` field

### 6. Electrotech Page (electrotech/index.html)
- [ ] Update stats: `XX+ Electrical Projects`, `XX+ Clients`, `XX kV`, `XX+ Airports`
- [ ] Replace 6 project cards with real project names, values, years, and clients
- [ ] Replace project placeholder images with real site photographs
- [ ] Update certifications — remove any not held, add any missing
- [ ] Replace 12 `Client Name X` entries in clients grid with real client names
- [ ] Update FAQ answers with specific licence class and voltage levels

### 7. Infrastructure Page (infrastructure/index.html)
- [ ] Update stats: projects, tenders, airports, project value
- [ ] Replace 6 project cards with real airport names, values, years
- [ ] Replace project placeholder images with real site photographs
- [ ] Update certifications as applicable
- [ ] Replace 12 `Client Name X` entries with real client names
- [ ] Update FAQ geographic coverage answer

### 8. Homepage Clients Strip (index.html)
- [ ] Replace 10 `Client Name X` items in the `.clients-track` div with real combined client names
- [ ] These should be a combined highlight — the full lists are on each entity page

### 9. Contact Page (contact/index.html)
- [ ] Replace entity-specific email addresses (`electrotech@...`, `infrastructure@...`)
- [ ] Add Google Maps embed — replace the `.map-placeholder` div with:
  ```html
  <iframe
    src="https://www.google.com/maps/embed?pb=YOUR_EMBED_CODE"
    width="100%" height="260" style="border:0;border-radius:8px;"
    allowfullscreen="" loading="lazy"
    title="Shri Karni Group office location">
  </iframe>
  ```
- [ ] Connect the form to a backend. Options:
  - **Formspree** (free, no backend needed): Replace `<form id="contact-form"...>` action with `https://formspree.io/f/YOUR_ID`
  - **EmailJS**: Add EmailJS SDK and call `emailjs.sendForm()` in shared.js
  - **Your own server**: POST the form data to your API endpoint

### 10. Sitemap & SEO
- [ ] Update all `<loc>` URLs in `sitemap.xml` to the actual domain
- [ ] Update `Sitemap:` line in `robots.txt` to the actual domain
- [ ] Submit `sitemap.xml` to Google Search Console after going live
- [ ] Update `<lastmod>` dates in sitemap whenever major content changes are made

### 11. Assets to Add
- [ ] `/assets/og-cover.jpg` — 1200×630px Open Graph image for social sharing
- [ ] `/assets/logo.png` — Logo for structured data (referenced in JSON-LD)
- [ ] `/assets/favicon.ico` — Add `<link rel="icon" href="/favicon.ico">` to all pages
- [ ] Director photograph at `/assets/director.jpg`
- [ ] Real project photographs (replace all Unsplash URLs)

---

## Hosting Instructions

This is a **pure static site** — no server, no database needed.

### Option A — Netlify (Recommended, Free)
1. Go to [netlify.com](https://netlify.com) and sign up
2. Drag and drop the entire `shri-karni/` folder onto the Netlify dashboard
3. Your site is live instantly
4. Add your custom domain in Site Settings → Domain Management

### Option B — Vercel (Free)
1. Push the folder to a GitHub repository
2. Connect the repo to [vercel.com](https://vercel.com)
3. Deploy in one click

### Option C — Traditional Web Hosting (cPanel, etc.)
1. Zip the entire `shri-karni/` folder
2. Upload via FTP or cPanel File Manager to your `public_html/` directory
3. Point your domain's DNS to the hosting server

---

## SEO Summary — What's Already Built In

| Feature | Detail |
|---|---|
| `<title>` tags | Unique, keyword-rich on every page |
| Meta descriptions | Unique on every page |
| Canonical URLs | Set on every page — update to real domain |
| Open Graph tags | For social sharing previews |
| JSON-LD structured data | Organization, AboutPage, ContactPage, FAQPage schemas |
| Breadcrumb navigation | On all sub-pages |
| Semantic HTML5 | `<main>`, `<article>`, `<section>`, `<nav>`, `<footer>`, ARIA roles |
| Image `alt` text | Descriptive on every image |
| `loading="lazy"` | On all below-fold images |
| `width` & `height` on images | Prevents Cumulative Layout Shift (CLS) |
| Skip-to-main link | Accessibility — also a Google ranking signal |
| `robots.txt` | Allows full crawl |
| `sitemap.xml` | Submit to Google Search Console |
| Mobile responsive | Works on all screen sizes |
| `prefers-reduced-motion` | Respects user accessibility settings |

---

## Notes

- The contact form currently shows a success message client-side only. Wire it to Formspree or EmailJS to actually receive submissions.
- All `XX` placeholders are intentional — fill them in before going live. Avoid publishing a site with visible placeholder text as it harms credibility and SEO.
- When you have real project photos, replace the Unsplash URLs with locally hosted images (e.g. `/assets/projects/runway-patna.jpg`) for better performance and no external dependency.
