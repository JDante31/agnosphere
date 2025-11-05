# TODO: Content & Assets Needed

This file lists all the content and assets you need to provide to finalize the website.

## 🖼️ Images & Assets

### Logo
- [ ] Company logo (SVG preferred)
  - Location: `public/logo.svg` or `public/logo.png`
  - Usage: Header, Footer, metadata
  - Dimensions: Flexible, but should look good at ~40px height

### Favicon
- [ ] Favicon (currently placeholder)
  - Location: `public/favicon.svg`
  - Format: SVG or PNG
  - Dimensions: 32x32px or 64x64px

### Open Graph Image
- [ ] Social sharing image (currently placeholder text file)
  - Location: `public/og-image.png`
  - Dimensions: 1200x630px
  - Content: Logo + tagline or branded graphic
  - Used when sharing links on social media

### Founder Photos
- [ ] Founder 1 photo
  - Location: `public/images/founder1.jpg`
  - Format: JPG or PNG
  - Dimensions: Square, minimum 800x800px
  - Usage: About page

- [ ] Founder 2 photo
  - Location: `public/images/founder2.jpg`
  - Format: JPG or PNG
  - Dimensions: Square, minimum 800x800px
  - Usage: About page

### Optional: Client Logos
- [ ] Client logo 1-6 (if available)
  - Location: `public/images/clients/`
  - Format: PNG with transparency
  - Dimensions: Width ~200px
  - Usage: Homepage trust section

## 👥 Founder Information

### Founder 1
```
Name: _______________________
Role/Title: _______________________
Bio (2-3 sentences): 
_________________________________________________
_________________________________________________
_________________________________________________

LinkedIn: https://linkedin.com/in/_______________________
Twitter/X: https://twitter.com/_______________________
```

### Founder 2
```
Name: _______________________
Role/Title: _______________________
Bio (2-3 sentences): 
_________________________________________________
_________________________________________________
_________________________________________________

LinkedIn: https://linkedin.com/in/_______________________
Twitter/X: https://twitter.com/_______________________
```

## 🏢 Company Information

### Legal Details (for Imprint & Privacy pages)
```
Legal Company Name: _______________________
Street Address: _______________________
City, Postal Code: _______________________
Country: _______________________
Registration Number: _______________________
Register Type: _______________________
VAT ID (if applicable): _______________________
Responsible Person: _______________________
```

### Contact Information
```
Primary Email: _______________________ (replace hello@agnosphere.com)
Support Email (if different): _______________________
Phone (optional): _______________________
```

## 🔗 External Service Setup

### Cal.com
- [ ] Create Cal.com account
- [ ] Set up "30 Min Consultation" event type
- [ ] Your Cal.com username: _______________________
- [ ] Full booking link: https://cal.com/_______________________

### Formspree
- [ ] Create Formspree account at https://formspree.io
- [ ] Create a new form
- [ ] Your Form ID: _______________________
- [ ] Configure redirect to `/thanks` on success

### Plausible Analytics
- [ ] Create Plausible account at https://plausible.io
- [ ] Add your domain
- [ ] Your domain: _______________________

### Social Media
```
LinkedIn Company Page: https://linkedin.com/company/_______________________
Twitter/X Account: https://twitter.com/_______________________
GitHub (optional): https://github.com/_______________________
```

## 🎨 Branding (Optional)

If you want to customize the default blue theme:

```
Primary Color (hex): _______________________ (currently: #3B82F6 blue-500)
Secondary Color (hex): _______________________ (currently: #6366F1 indigo-500)
Accent Color (hex): _______________________ (currently: #F97316 orange-500)
```

To update, edit `src/styles/global.css`.

## 📝 Content Updates

### Testimonials (Currently Placeholder)

If you have real testimonials, provide:

```
Testimonial 1:
Quote: "_________________________________________________"
Name: _______________________
Role: _______________________
Company: _______________________
Photo (optional): path/to/photo.jpg

Testimonial 2:
Quote: "_________________________________________________"
Name: _______________________
Role: _______________________
Company: _______________________
Photo (optional): path/to/photo.jpg

Testimonial 3:
Quote: "_________________________________________________"
Name: _______________________
Role: _______________________
Company: _______________________
Photo (optional): path/to/photo.jpg
```

### Taglines & Copy Review

Review and refine these key messages in:
- Homepage hero: "Turn Your Data Into Competitive Advantage"
- Homepage subheading
- Service descriptions
- About page messaging

## 📅 Timeline

1. **Immediate** (before deployment):
   - [ ] Company email address
   - [ ] Logo
   - [ ] Favicon
   - [ ] Legal information for Imprint
   - [ ] Cal.com setup

2. **Before Public Launch**:
   - [ ] Founder photos and bios
   - [ ] OG image
   - [ ] Formspree setup
   - [ ] Plausible setup
   - [ ] Privacy policy review

3. **Nice to Have**:
   - [ ] Real testimonials
   - [ ] Client logos
   - [ ] Custom colors
   - [ ] First blog post

## 📋 Quick Update Commands

After providing assets:

1. Add images to `public/` directory
2. Update files marked with placeholders:
   - Search for `[Placeholder` or `PLACEHOLDER` in the codebase
   - Update Cal.com links: search for `cal.com/agnosphere`
   - Update email: search for `hello@agnosphere.com`

3. Commit and deploy:
```bash
git add .
git commit -m "Update with real content and assets"
git push
```

Vercel will automatically redeploy.

---

**Pro Tip:** Start with the "Immediate" items and launch with placeholders for the rest. You can update incrementally after launch.

