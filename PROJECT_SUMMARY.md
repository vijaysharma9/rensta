# RENSTA Property Services — Project Summary

## Overview

**Project Name:** Rensta Coming Soon Landing Page  
**Client/Brand:** Rensta Property Services  
**Project Type:** WordPress custom page template (Coming Soon / pre-launch)  
**Tech Stack:** WordPress, PHP, HTML5, CSS3, Vanilla JavaScript (no frameworks, no jQuery)

---

## Project Structure

```
wp-content/themes/rensta/
├── style.css              # Theme metadata
├── index.php              # Default template
├── header.php             # Minimal header
├── footer.php             # Minimal footer
├── functions.php          # Theme setup, admin bar hide
├── page-coming-soon.php   # Main Coming Soon template (self-contained)
└── assets/
    ├── logo-white.png     # RENSTA logo (white)
    └── trust-badges.png   # NAPIT, Gas Safe Register, TrustMark
```

---

## Key Deliverables

| Component | Description |
|-----------|-------------|
| **Coming Soon Template** | Full-page custom WordPress template with 4 sections |
| **Rensta Theme** | Minimal custom theme for this landing page |
| **Responsive Design** | Mobile-first, breakpoints at 1024px, 768px, 480px |
| **Email Capture** | 2 forms (Hero + Footer) with client-side success message |

---

## Page Sections

1. **Hero** — Full viewport height, Coming Soon messaging, email form, phone CTA  
2. **About Us** — Two-column layout: electrician image + company description  
3. **Services** — 10-item grid of property compliance & maintenance services  
4. **Footer** — Two-column: logo + email form | certifications + phone

---

## Technical Notes

- **No plugins required**
- **No backend** for email forms (success message only; no database storage)
- **Font Awesome 6** (CDN) for icons
- **Google Fonts** — Poppins (400, 500, 600, 700, 800)
- **Admin bar** hidden on front-end when logged in

---

## Usage

1. Activate **Rensta** theme in Appearance → Themes  
2. Create a new Page in WordPress  
3. Set template to **Coming Soon** (Page Attributes)  
4. Optionally set as homepage in Settings → Reading  

---

## Contact

**Phone:** 020 7046 0410

---

# RENSTA — Mail Summary

## Email Capture Overview

The Coming Soon page includes **two identical email capture forms** for “Get Notified” signups.

### Form Locations

| Location | Section | Purpose |
|----------|---------|---------|
| Hero | Above the fold | Primary signup point |
| Footer | Bottom of page | Secondary signup point |

---

## Current Implementation

### Behavior

- **Front-end only** — No server-side processing
- **Client-side validation** — HTML5 `required` on email field
- **Success feedback** — Message: *"Thanks! We'll notify you when we're ready."*
- **Form reset** — Input cleared after submit

### Technical Details

| Property | Value |
|----------|-------|
| Method | `POST` |
| Action | `#` (no backend URL) |
| Fields | `email` (type="email", required) |
| Submit button | "Get Notified" |
| JavaScript | Vanilla JS, `preventDefault()` on submit |

### Form Markup (Hero)

```html
<form class="hero-form" action="#" method="post" aria-label="Email signup">
  <div class="hero-email-wrap">
    <input type="email" name="email" placeholder="Enter your email" required>
    <button type="submit" class="hero-get-notified-btn">Get Notified</button>
  </div>
</form>
<p class="form-success" role="status">Thanks! We'll notify you when we're ready.</p>
```

---

## What’s Not Implemented

| Feature | Status |
|---------|--------|
| Database storage | ❌ Not implemented |
| Email sending | ❌ Not implemented |
| Newsletter integration (Mailchimp, etc.) | ❌ Not implemented |
| Double opt-in | ❌ Not implemented |
| Server-side validation | ❌ Not implemented |
| CSRF protection | ❌ Not implemented |

---

## Suggested Next Steps (Backend)

To turn these forms into real email capture:

1. **Plugin option** — Contact Form 7, WPForms, or Newsletter
2. **Third-party API** — Mailchimp, Sendinblue, ConvertKit
3. **Custom PHP** — `wp_mail()` or custom handler in theme
4. **REST API** — Custom endpoint + AJAX form submission

---

# RENSTA — Design Summary

## Brand

**Name:** RENSTA Property Services  
**Tagline:** PROPERTY SERVICES  
**Industry:** Property compliance and maintenance (UK)

---

## Color Palette

| Name | Hex | Usage |
|------|-----|-------|
| Primary Navy | `#001255` | Hero/Service/Footer backgrounds, headings, CTA |
| Accent Blue | `#2563EB` | Labels, footer buttons, accents |
| Hero Blue | `#0056DD` | Hero buttons (Get Notified, Phone) |
| Dark Navy | `#000d3d` | Footer bottom bar |
| White | `#ffffff` | Text on dark, trust badge background |
| Gray | `#374151` | Body text |
| Light Gray | `#9CA3AF` | Placeholder text |

---

## Typography

**Font:** Poppins (Google Fonts)  
**Weights:** 400, 500, 600, 700, 800

| Element | Size | Weight |
|---------|------|--------|
| Hero logo "RENSTA" | 28px | 700 |
| Hero tagline | 10px | 400 |
| "COMING SOON" | 82.97px | 600 |
| Section headings | 30–36px | 700–800 |
| Body text | 15px | 400 |
| Labels | 12.96–14px | 400–700 |

---

## Layout

### Global

- **Max width:** 1200px  
- **Margin:** 0 auto  
- **Padding:** 0 40px (20px on mobile)

### Section Structure

| Section | Background | Padding |
|---------|------------|---------|
| Hero | #001255 + image overlay | 60px 20px |
| About | #ffffff | 80px 0 |
| Services | #001255 | 80px 0 |
| Footer | #001255 | 60px 0 |
| Footer bar | #000d3d | 14px 0 |

---

## Components

### Hero

- Full-height (100vh), centered flex
- Background image + overlay `rgba(0, 18, 85, 0.80)`
- Logo, “We're almost ready.”, “COMING SOON”
- Trust badges: white bar, 6px radius
- Email form: joined input + button
- Phone CTA: pill button (#0056DD)

### About

- Two-column grid (1fr 1fr), gap 60px
- Image: 420px height, object-fit cover
- Label: “About Us” with checkmark, blue (#2563EB)
- Button: “Contact Us for More Infos” (270×49px)

### Services

- 5-column grid (2 rows × 5)
- Icons: 64×64px circles, `rgba(255,255,255,0.1)`
- Font Awesome icons (fire, plug, bolt, etc.)
- Labels max-width 120px

### Footer

- Two columns: logo + email | certifications + phone
- Logo: RENSTA + star, PROPERTY SERVICES
- Certifications: NAPIT, Gas Safe, TrustMark
- Bottom bar: copyright © 2025

---

## Trust Badges

- NAPIT  
- Gas Safe Register  
- TrustMark (Government Endorsed Quality)

---

## Responsive Breakpoints

| Breakpoint | Changes |
|------------|---------|
| 1024px | Services: 3 columns |
| 768px | About: 1 column; Services: 2 columns; footer stacked; container 20px |
| 480px | Hero/form scaled; headings ~20% smaller |

---

## Icons (Font Awesome 6)

| Service | Icon |
|---------|------|
| Gas and Boiler Safety | fa-fire |
| Electrical Safety (EICR and PAT) | fa-plug |
| Energy Performance Certificates | fa-bolt |
| Fire Risk Assessments | fa-shield-halved |
| Fire Alarms and Emergency Lighting | fa-bell |
| Property Repairs and Call Outs | fa-screwdriver-wrench |
| Fuse Box Upgrades | fa-square-plus |
| Fire Door Checks | fa-door-closed |
| Inventory Check In and Check Out | fa-clipboard-list |
| Plumbing | fa-faucet |

---

## External Assets

- **Hero background:** Unsplash (electrician/worker)
- **About image:** Unsplash (electrician on fuse box)
- **Logo:** Theme asset (`logo-white.png`)
- **Trust badges:** Theme asset (`trust-badges.png`)
