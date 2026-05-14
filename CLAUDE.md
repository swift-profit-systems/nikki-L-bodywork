# CLAUDE.md — Nikki Leonardi Bodywork

## Project Overview
Website for Nikki Leonardi Bodywork, an Ashiatsu barefoot massage specialist in Traverse City, MI. Built and maintained by Swift Profit Systems (Elliot Swift).

## Tech Stack
- **Framework:** Astro (static site)
- **Styling:** Tailwind CSS
- **Hosting:** Railway (auto-deploy from GitHub)
- **Scheduling:** Squarespace Acuity Scheduling (embedded iframe, owner ID 38952971)
- **Email:** Active Campaign (not yet connected — forms currently store to localStorage)
- **Payments:** Square
- **Domain:** Custom domain not yet purchased — currently at nikki-l-bodywork-production.up.railway.app

## Repository Structure
/public/ — Static assets (images, PDF guide, favicon)
/public/guides/ — Free guide PDF (5-signs-your-body-is-compensating.pdf)
/src/ — Astro source files
/src/pages/ — Page components (index.astro, about.astro, tools.astro, book.astro)
/src/layouts/ — Layout components
/src/components/ — Reusable components

## Site Architecture
Four pages:
- / (Homepage) — Hero, stats, social proof, differentiators, pricing, reviews, guide capture, closing CTA
- /about — Origin story, training, approach, specializations grid, human part, studio
- /tools — Tools of the Trade (educational page about modalities)
- /book — Acuity scheduling embed, FAQ accordion, guide capture form

## Brand Rules (Non-Negotiable)
1. No fabricated content. Every testimonial must be a real Google review.
2. No em dashes in body copy. Use commas, periods, colons, or parentheses. Exception: attribution dashes before names in testimonials.
3. No spa language. Never use: relaxing massage, treat yourself, pamper, melt away, journey to wellness, holistic healing.
4. Expert-decides model. Nikki picks the modalities, not the client. Never frame services as a menu.
5. First person on About page. Third person on Homepage. Never mix within a page.
6. Premium positioning. No discounts to drive bookings. Urgency is scarcity/capacity-based only.
7. Pricing must match Acuity. Current rates: 120 min $250, 90 min $175, 75 min $150, 60 min $125.

## Design System
- Typography: Playfair Display (headings), Inter (body)
- Colors: Navy backgrounds (bg-[#0d1428], bg-[#162040]), gold accents (#C8952E, #c8a84b)
- Gold text opacity: minimum /80 for body text (WCAG AA). /50 only for decorative elements.
- Cards: bg-[#0d1428] or bg-[#162040]/50 with border-[#c8a84b]/10, shadow-lg, hover transitions duration-200 or duration-300
- Buttons: Gold bg (#C8952E), white text, shadow-md, hover:shadow-lg hover:scale-[1.02]
- Section dividers: bg-gradient-to-r from-transparent via-[#c8a84b]/15 to-transparent h-[1px]

## Key Components
- Exit-intent popup: Uses direct style.opacity manipulation (NOT Tailwind class toggling — Astro CSP blocks it). Fires on cursor exit desktop, 45s inactivity mobile. Once per session.
- Guide forms: Three instances (homepage, /book, exit popup). Store email to localStorage. Open PDF in new tab.
- Acuity iframe: Lazy-loaded. Do not modify the embed URL or parameters.
- Logo: nikki-logo.webp (optimized). Explicit width/height on both nav and footer instances.

## Deployment
- Push to main branch — Railway auto-deploys
- Build command: npm run build (Astro static build)

## Do Not Touch
- Acuity embed URL or parameters
- Any copy unless explicitly instructed
- Package.json dependencies without asking first
- The /public/guides/ PDF file

## Testing Checklist
1. npm run build succeeds with no errors
2. All four pages render correctly
3. No console errors
4. Mobile responsive (test at 375px width)
5. All internal links use relative paths
6. No em dashes in body copy
7. Every reviewer name appears at most once per page
8. Prices match Acuity rates
