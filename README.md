# Agnosphere Landing Page

AI & Data Consulting for ambitious SMB and mid-market companies.

## 🚀 Tech Stack

- **Framework:** [Astro](https://astro.build)
- **Styling:** [Tailwind CSS](https://tailwindcss.com)
- **Animations:** [Framer Motion](https://www.framer.com/motion/) (React)
- **Analytics:** [Plausible](https://plausible.io)
- **Scheduling:** [Cal.com](https://cal.com)
- **Forms:** [Formspree](https://formspree.io)
- **Hosting:** [Vercel](https://vercel.com)

## 📦 Project Structure

```
/
├── public/              # Static assets
│   ├── favicon.svg
│   ├── og-image.png
│   ├── robots.txt
│   └── images/
├── src/
│   ├── components/      # Reusable components
│   │   ├── Header.astro
│   │   ├── Footer.astro
│   │   ├── ServiceCard.astro
│   │   ├── Testimonial.astro
│   │   ├── MagneticButton.tsx
│   │   └── AnimatedSection.tsx
│   ├── layouts/         # Page layouts
│   │   └── BaseLayout.astro
│   ├── pages/           # File-based routing
│   │   ├── index.astro
│   │   ├── about.astro
│   │   ├── contact.astro
│   │   ├── services/
│   │   ├── case-studies/
│   │   └── insights/
│   └── styles/
│       └── global.css
└── package.json
```

## 🛠️ Development

### Prerequisites

- Node.js 18+ and npm

### Setup

```bash
npm install
```

### Run Development Server

```bash
npm run dev
```

Open [http://localhost:4321](http://localhost:4321) in your browser.

### Build for Production

```bash
npm run build
```

### Preview Production Build

```bash
npm run preview
```

## 🎨 Customization

### Update Brand Colors

Edit `src/styles/global.css`:

```css
:root {
  --color-primary: 59 130 246;    /* blue-500 */
  --color-secondary: 99 102 241;  /* indigo-500 */
  --color-accent: 249 115 22;     /* orange-500 */
}
```

### Add Logo

Replace the placeholder in:
- `src/components/Header.astro`
- `src/components/Footer.astro`
- Add actual logo files to `public/`

### Update Contact Information

1. **Email:** Replace `hello@agnosphere.com` throughout
2. **Cal.com:** Update the Cal.com link in contact page and CTAs
3. **Social Links:** Update LinkedIn, Twitter links in Footer
4. **Formspree:** Get a form ID from [Formspree](https://formspree.io) and update in `src/pages/contact.astro`

### Update Legal Pages

Fill in actual company details in:
- `src/pages/imprint.astro`
- `src/pages/privacy.astro`

### Add Founder Information

Update `src/pages/about.astro` with:
- Founder names and bios
- Photos (add to `public/images/`)
- LinkedIn/Twitter profiles

## 📊 Analytics & Tracking

### Plausible Setup

1. Create account at [plausible.io](https://plausible.io)
2. Add your domain
3. Update domain in `src/layouts/BaseLayout.astro`:
   ```html
   <script defer data-domain="your-domain.com" src="https://plausible.io/js/script.js"></script>
   ```

### Custom Events

Tracked events:
- `cta_header_click` - Header CTA button
- `cta_mobile_click` - Mobile menu CTA
- `form_submission` - Contact form submit
- `form_success` - Thank you page view

## 🚀 Deployment

### Vercel (Recommended)

1. Push code to GitHub
2. Import project in [Vercel](https://vercel.com)
3. Vercel will auto-detect Astro and deploy
4. Add custom domain in Vercel settings

### Environment Variables

No environment variables needed for basic setup. If you add server-side features, create `.env` file (see `.env.example`).

## ✅ Launch Checklist

Before going live:

- [ ] Update all placeholder content
- [ ] Add logo and brand images
- [ ] Update founder photos and bios
- [ ] Fill in Imprint and Privacy Policy
- [ ] Get Formspree form ID and update contact form
- [ ] Set up Cal.com account and update booking links
- [ ] Configure Plausible analytics
- [ ] Test all forms and CTAs
- [ ] Add actual client logos (if available)
- [ ] Update testimonials with real quotes
- [ ] Test on mobile devices
- [ ] Run Lighthouse audit (target: 95+ on all metrics)
- [ ] Set up custom domain
- [ ] Test 404 page
- [ ] Submit sitemap to Google Search Console

## 🎯 SEO

The site is built with SEO best practices:

- ✅ Semantic HTML
- ✅ Meta tags (title, description, OG, Twitter)
- ✅ JSON-LD structured data
- ✅ Sitemap.xml (auto-generated)
- ✅ Robots.txt
- ✅ Fast loading times
- ✅ Mobile responsive
- ✅ Accessible (WCAG AA)

## 📝 Adding Blog Posts

Create new files in `src/pages/insights/`:

```astro
---
// src/pages/insights/my-first-post.astro
import BaseLayout from '../../layouts/BaseLayout.astro';
---

<BaseLayout title="Post Title" description="Post description">
  <!-- Your content -->
</BaseLayout>
```

## 🤝 Contributing

This is a private project. For any questions, contact the team.

## 📄 License

Proprietary - All rights reserved

---

Built with ❤️ by the Agnosphere team
