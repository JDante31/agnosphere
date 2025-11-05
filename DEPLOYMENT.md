# Deployment & Launch Guide for Agnosphere

This guide will walk you through deploying your Agnosphere landing page to Vercel and completing the final setup steps.

## Pre-Deployment Checklist

### 1. Content to Add

Before deploying, prepare the following content:

#### Required Images
- [ ] Company logo (SVG preferred, or high-res PNG)
- [ ] Favicon (place in `public/favicon.svg`)
- [ ] Open Graph image (`public/og-image.png` - 1200x630px)
- [ ] Founder photos (2 photos, square, high resolution)

#### Company Information
- [ ] Company legal name and address
- [ ] VAT ID (if applicable)
- [ ] Registration details
- [ ] Email address (currently placeholder: hello@agnosphere.com)

#### Founder Details
- [ ] Founder 1: Name, role, bio, LinkedIn, Twitter
- [ ] Founder 2: Name, role, bio, LinkedIn, Twitter

#### External Services
- [ ] Cal.com username (update all `cal.com/agnosphere` links)
- [ ] Formspree form ID (sign up at formspree.io)
- [ ] Plausible account (sign up at plausible.io)
- [ ] LinkedIn company page URL
- [ ] Twitter/X account URL

#### Optional
- [ ] Client logos (if available)
- [ ] Real testimonials (currently placeholder)
- [ ] Custom brand colors (update in `src/styles/global.css`)

## Step-by-Step Deployment

### 1. Initialize Git Repository

```bash
cd /Users/jakobschlegel/Documents/coding/agnosphere
git init
git add .
git commit -m "Initial commit: Agnosphere landing page"
```

### 2. Push to GitHub

```bash
# Create a new repository on GitHub (private recommended)
# Then run:
git remote add origin https://github.com/YOUR_USERNAME/agnosphere.git
git branch -M main
git push -u origin main
```

### 3. Deploy to Vercel

#### Option A: Vercel CLI (Fastest)

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel

# Follow prompts:
# - Set up and deploy? Y
# - Which scope? Select your account
# - Link to existing project? N
# - What's your project's name? agnosphere
# - In which directory is your code located? ./
# - Auto-detected Astro! Continue? Y
# - Want to modify settings? N

# Deploy to production
vercel --prod
```

#### Option B: Vercel Dashboard

1. Go to [vercel.com](https://vercel.com)
2. Click "Add New" → "Project"
3. Import your GitHub repository
4. Vercel will auto-detect Astro
5. Click "Deploy"

### 4. Post-Deployment Configuration

#### A. Custom Domain

1. In Vercel dashboard, go to your project
2. Settings → Domains
3. Add your custom domain (e.g., agnosphere.com)
4. Follow DNS configuration instructions
5. Wait for DNS propagation (can take up to 48 hours)

#### B. Update Site URL

After deploying, update the site URL in:

```typescript
// src/layouts/BaseLayout.astro
const site = 'https://agnosphere.com'; // Your actual domain
```

Commit and push this change.

#### C. Configure Plausible Analytics

1. Sign up at [plausible.io](https://plausible.io)
2. Add your domain
3. The script is already included in BaseLayout.astro
4. Update the domain in the script:

```html
<script defer data-domain="agnosphere.com" src="https://plausible.io/js/script.js"></script>
```

#### D. Set Up Formspree

1. Sign up at [formspree.io](https://formspree.io)
2. Create a new form
3. Copy your form ID
4. Update in `src/pages/contact.astro`:

```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

5. Configure form to redirect to `/thanks` on success

#### E. Configure Cal.com

1. Sign up at [cal.com](https://cal.com)
2. Set up your event type (e.g., "30 Min Consultation")
3. Get your booking link
4. Update all instances of `cal.com/agnosphere` throughout the site with your actual link

You can find instances by running:
```bash
grep -r "cal.com/agnosphere" src/
```

## Content Updates Guide

### Update Logo

1. Add logo files to `public/`:
   - `logo.svg` or `logo.png`
   - Update size/format as needed

2. Update in `src/components/Header.astro`:

```astro
<a href="/" class="flex items-center space-x-2 group">
  <img src="/logo.svg" alt="Agnosphere" class="h-10 w-auto" />
</a>
```

3. Update in `src/components/Footer.astro` similarly

### Update Founder Information

Edit `src/pages/about.astro`:

1. Replace placeholder photos:
```astro
<img src="/images/founder1.jpg" alt="Founder Name" class="w-48 h-48 rounded-full object-cover" />
```

2. Update names, roles, bios
3. Update social links

### Update Legal Pages

Edit these files with your actual information:
- `src/pages/imprint.astro`
- `src/pages/privacy.astro`

Replace all `[Placeholders]` with real data.

### Add Client Logos (Optional)

If you have client logos:

1. Add images to `public/images/clients/`
2. Update the logos array in `src/pages/index.astro`:

```javascript
const logos = [
  { src: '/images/clients/client1.png', alt: 'Client 1' },
  { src: '/images/clients/client2.png', alt: 'Client 2' },
  // ...
];
```

## Testing Before Launch

### 1. Local Testing

```bash
npm run build
npm run preview
```

Open http://localhost:4321 and test:
- [ ] All pages load correctly
- [ ] Navigation works
- [ ] Forms submit (check Formspree)
- [ ] Cal.com embed loads
- [ ] Mobile responsive
- [ ] All links work

### 2. Lighthouse Audit

1. Open Chrome DevTools (F12)
2. Go to Lighthouse tab
3. Run audit for:
   - Performance
   - Accessibility
   - Best Practices
   - SEO

Target scores: **95+ on all metrics**

### 3. Cross-Browser Testing

Test on:
- [ ] Chrome
- [ ] Safari
- [ ] Firefox
- [ ] Mobile (iOS Safari, Chrome Android)

### 4. SEO Checklist

After deploying to production domain:

- [ ] Submit sitemap to Google Search Console
  - URL: https://yourdomain.com/sitemap-index.xml
- [ ] Verify og:image renders correctly
  - Test at: https://www.opengraph.xyz/
- [ ] Check structured data
  - Test at: https://search.google.com/test/rich-results
- [ ] Verify robots.txt is accessible
  - URL: https://yourdomain.com/robots.txt

## Maintenance

### Adding Blog Posts

Create new files in `src/pages/insights/`:

```astro
---
// src/pages/insights/my-post.astro
import BaseLayout from '../../layouts/BaseLayout.astro';

const jsonLd = {
  '@context': 'https://schema.org',
  '@type': 'Article',
  headline: 'Your Title',
  author: {
    '@type': 'Person',
    name: 'Author Name',
  },
  datePublished: '2025-01-01',
  description: 'Article description',
};
---

<BaseLayout
  title="Your Title - Agnosphere"
  description="Article description"
  jsonLd={jsonLd}
>
  <article class="prose lg:prose-xl mx-auto">
    <!-- Your content -->
  </article>
</BaseLayout>
```

### Updating Testimonials

Edit `src/pages/index.astro`, update the `testimonials` array.

### Analytics Review

Check Plausible dashboard weekly:
- Page views
- Top pages
- Traffic sources
- Custom events (CTA clicks, form submissions)

## Troubleshooting

### Build Fails

```bash
# Clear cache and rebuild
rm -rf node_modules dist .astro
npm install
npm run build
```

### Images Not Loading

- Check file paths (case-sensitive)
- Ensure images are in `public/` directory
- Verify file extensions

### Form Not Submitting

- Check Formspree form ID
- Verify form action URL
- Test in production (some features don't work in dev)

### Cal.com Not Loading

- Check account is active
- Verify event type is published
- Test booking link directly

## Support

For questions about the codebase:
- Check README.md
- Review component documentation
- Contact development team

---

**Next Steps After Launch:**

1. Monitor analytics for first week
2. Gather user feedback
3. Iterate on copy based on performance
4. Add case studies as they become available
5. Start content marketing (blog posts)
6. Set up email notifications for form submissions
7. A/B test CTAs and messaging

Good luck with the launch! 🚀

