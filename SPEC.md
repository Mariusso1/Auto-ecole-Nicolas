# SPEC.md - Auto-École Nicolas

## 1. Project Overview

**Project Name:** Auto-École Nicolas  
**Type:** Static Website (Front-end only)  
**Framework:** Astro 4.x  
**Hosting:** Netlify (free tier)  
**Target Users:** People seeking driving school services in Castres area  
**Language:** French

---

## 2. Technical Stack

| Technology | Purpose |
|------------|---------|
| Astro 4.x | Static site generator with Islands architecture |
| CSS (scoped) | Styling (no external frameworks per rules) |
| JavaScript | Minimal interactivity |
| Google Reviews API | Display Google reviews |

---

## 3. Site Structure

### 3.1 Pages

```
/
├── src/
│   ├── pages/
│   │   ├── index.astro        # Home page
│   │   ├── horaires.astro     # Opening hours
│   │   ├── contact.astro      # Contact page
│   │   └── code.astro         # Code course page
│   ├── components/
│   │   ├── Header.astro       # Navigation header
│   │   ├── Footer.astro       # Footer with info
│   │   ├── GoogleReviews.astro # Reviews cards
│   │   └── Card.astro         # Reusable card component
│   ├── layouts/
│   │   └── Layout.astro       # Base HTML layout
│   └── styles/
│       └── global.css         # Global styles & CSS variables
├── public/
│   └── images/                # Static images (to be added)
├── astro.config.mjs
├── package.json
└── .gitignore
```

### 3.2 Navigation

- **Header:** Logo + Navigation links (Accueil, Horaires, Code, Contact)
- **Footer:** Contact info + Quick links + Social (optional)

---

## 4. UI/UX Specification

### 4.1 Color Palette

| Color | Hex | Usage |
|-------|-----|-------|
| Primary Blue | `#1a5f9e` | Headers, buttons, accents |
| Dark Navy | `#0d2b4a` | Footer, text emphasis |
| White | `#ffffff` | Backgrounds, cards |
| Light Gray | `#f5f7fa` | Section backgrounds |
| Text Dark | `#333333` | Body text |
| Text Light | `#666666` | Secondary text |
| Accent Gold | `#d4a84b` | Highlights, stars (reviews) |

### 4.2 Typography

- **Headings:** "Montserrat", sans-serif (Google Fonts)
- **Body:** "Open Sans", sans-serif (Google Fonts)
- **Sizes:**
  - H1: 2.5rem (40px)
  - H2: 2rem (32px)
  - H3: 1.5rem (24px)
  - Body: 1rem (16px)
  - Small: 0.875rem (14px)

### 4.3 Layout

- **Max Width:** 1200px container
- **Responsive Breakpoints:**
  - Mobile: < 768px
  - Tablet: 768px - 1024px
  - Desktop: > 1024px

### 4.4 Components

#### Header
- Fixed position
- White background with shadow
- Mobile: Hamburger menu

#### Footer
- Dark navy background (`#0d2b4a`)
- White text
- Contact info + navigation links

#### Google Reviews Card
- White card with shadow
- 5-star rating (gold stars)
- Review text
- Author name
- Date

#### Buttons
- Primary: Blue background, white text
- Hover: Slightly darker blue
- Border radius: 4px

---

## 5. Page Specifications

### 5.1 Home Page (`index.astro`)

**Sections:**
1. **Hero Section**
   - Large title: "Votre auto-école à Castres"
   - Subtitle: Professional message
   - Call-to-action button
   - Background image (to be provided)

2. **Introduction**
   - Brief presentation of the driving school
   - Key benefits (3-4 points)

3. **Google Reviews Section**
   - Title: "Avis de nos élèves"
   - Grid of review cards (3 columns desktop, 1 mobile)
   - Each card shows: Stars, text, author, date

4. **Services Preview**
   - Quick overview of main services

### 5.2 Horaires Page (`horaires.astro`)

**Content:**
- Opening hours table
- Days of week with hours
- Note about holidays

### 5.3 Contact Page (`contact.astro`)

**Content:**
- Phone number (clickable on mobile)
- Email address (clickable)
- Physical address
- Embedded map (optional, via iframe)
- Simple contact form (optional)

### 5.4 Code Page (`code.astro`)

**Content:**
- Placeholder for course information
- Sections to be populated later by user

---

## 6. Google Reviews Integration

### Option 1: Google Places API (Recommended)
- Requires Google Cloud API key
- Fetches reviews dynamically
- Must be configured by user

### Option 2: Static/Embedded
- Reviews hardcoded initially
- Can be updated manually
- No API required initially

**Initial Approach:** Use static placeholder data until API is configured

---

## 7. Performance Requirements

- **Lighthouse Score Target:** 90+ (all categories)
- **Images:** WebP format with lazy loading
- **CSS:** Minimal, scoped per component
- **JavaScript:** Minimal (Astro Islands only where needed)

---

## 8. Accessibility (a11y)

- Semantic HTML (header, main, nav, footer, article)
- Alt text for all images
- ARIA labels where needed
- Keyboard navigation
- Color contrast ratio 4.5:1 minimum
- Focus indicators

---

## 9. Deployment (Netlify)

- **Build Command:** `npm run build`
- **Publish Directory:** `dist`
- **Environment Variables:** None required (static site)
- **Custom Domain:** autoecolenicolascastres.com (to configure)

---

## 10. Files to Create

### Priority 1 - Core Structure
```
1. package.json
2. astro.config.mjs
3. tsconfig.json
4. .gitignore
5. src/layouts/Layout.astro
6. src/styles/global.css
```

### Priority 2 - Components
```
7. src/components/Header.astro
8. src/components/Footer.astro
9. src/components/GoogleReviews.astro
```

### Priority 3 - Pages
```
10. src/pages/index.astro
11. src/pages/horaires.astro
12. src/pages/contact.astro
13. src/pages/code.astro
```

---

## 11. Next Steps

1. User validates SPEC.md
2. Initialize Astro project (with user validation for commands)
3. Create components and pages
4. Add placeholder content
5. Configure Google Reviews
6. Deploy to Netlify

---

*Document Version: 1.0*  
*Created: 2026-03-19*  
*Mode: Architect*
