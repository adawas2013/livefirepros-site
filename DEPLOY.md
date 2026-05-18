# LiveFirePros — Deployment Guide

## Option 1: Netlify (FREE — Recommended)

### Step-by-step:

1. Go to **netlify.com** and sign up (free — use Google or GitHub)
2. On the dashboard, look for **"Deploy manually"** or drag-and-drop
3. **Drag the entire `site/` folder** (the one with index.html and thank-you.html) onto the Netlify deploy area
4. Done. You'll get a URL like `livefirepros.netlify.app` instantly.

### Connect your domain:
1. In Netlify → **Domain settings** → **Add custom domain**
2. Enter: `livefirepros.com`
3. Netlify will tell you to update your nameservers or add a CNAME record
4. Go to your domain registrar (Namecheap/Porkbun) → DNS settings
5. Add a **CNAME record**: `@` → points to your Netlify URL
6. Or change nameservers to Netlify's (they'll provide them)
7. Enable **HTTPS** (Netlify does this free with Let's Encrypt)

### Form handling (FREE on Netlify):
- The form already has `data-netlify="true"` — Netlify auto-detects it
- Form submissions show up in: Netlify dashboard → Forms
- Set up **email notifications**: Netlify → Forms → Form notifications → Add email
- You'll get an email every time someone submits a quote request

### Want email forwarding too?
- Set up **quotes@livefirepros.com** using ImprovMX (free) or your registrar's email forwarding

---

## Option 2: GitHub Pages (FREE)

1. Create a GitHub account (if you don't have one)
2. Create a new repository called `livefirepros`
3. Upload index.html and thank-you.html to the repo
4. Go to Settings → Pages → Source: main branch
5. Custom domain: livefirepros.com
6. **Note:** GitHub Pages doesn't handle forms — you'd need to swap the form to use Formspree.io (free tier: 50 submissions/month)

---

## Option 3: Cloudflare Pages (FREE)

Similar to Netlify. Drag and drop the site folder. Free SSL. Free custom domain. 
Form handling: use Cloudflare Workers or external form service.

---

## After Deployment Checklist

- [ ] Verify site loads at livefirepros.com
- [ ] Submit a test form — confirm you receive the notification
- [ ] Set up Google Search Console (search.google.com/search-console) — verify domain, submit sitemap
- [ ] Set up Google Analytics (analytics.google.com) — add tracking code to the HTML
- [ ] Create Google Business Profile for LiveFirePros
- [ ] Test on mobile — make sure everything looks good

---

## Files to Deploy

```
site/
├── index.html        (main landing page with lead capture form)
└── thank-you.html    (confirmation page after form submit)
```

That's it. Two files. Deploy and you're live.
