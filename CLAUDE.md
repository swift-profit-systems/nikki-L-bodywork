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

## Design System (Light Mode — Round 5)
- Typography: Playfair Display (headings), Inter (body)
- Backgrounds:
  - Primary: `bg-white` (#FFFFFF)
  - Alternate sections: `bg-[#FAF8F5]` (warm cream)
  - Accent bands (featured quote, guide capture, tools intro): `bg-[#5B8FA8]` (studio blue)
  - Footer only: `bg-[#0d1428]` (navy, stays dark)
- Text:
  - Primary: `text-[#1A1A1A]` on light backgrounds
  - Secondary: `text-[#4A4A4A]` on light backgrounds
  - On blue accent sections: `text-white` and `text-white/90`
  - Section labels (PACKAGES, etc.): gold `#C8952E`, uppercase, tracking-widest
- Gold accents: `#C8952E` (primary), `#c8a84b` (secondary borders/decoration), `#B8850E` (hover dark)
- Cards (light mode): `bg-white border border-[#E8E0D4] rounded-lg shadow-sm` or `shadow-md`. Hover: `hover:shadow-lg hover:border-[#c8a84b]/30 transition-all duration-200`
- Buttons (.btn-primary): gold `#C8952E` bg, white text, `border-2 border-[#C8952E]`, rounded-lg, shadow-md. Hover: bg `#B8850E`, shadow-lg, scale-[1.02]
- Section dividers on light: `bg-gradient-to-r from-transparent via-[#E8E0D4] to-transparent h-[1px]`. On blue: `via-white/20`

## Key Components
- Guide forms: Two instances (homepage on blue band, /book page on blue band). Store email to localStorage. Open PDF in new tab.
- Acuity iframe: Lazy-loaded on /book. Do not modify the embed URL or parameters.
- Logo: nikki-logo.webp. Explicit width/height on both nav (62x40) and footer (99x64) instances.
- Hero photo (homepage): `/studio-interior.webp` (394 KB), split layout right column.
- Portrait (about page): `/nikki-portrait.webp` (87 KB), split layout right column on hero.
- FAQ accordion on /book: text-xl questions, text-lg answers, single-open behavior.

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
