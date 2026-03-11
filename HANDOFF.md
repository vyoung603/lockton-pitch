# Lockton Pitch Deck -- Handoff Document

## Live URL
https://vyoung603.github.io/denver-health-pitch/

## Repo
https://github.com/vyoung603/denver-health-pitch

---

## What This Is
A single-file horizontal-scroll HTML pitch deck presenting SonderMind's "Total Brain Solutions" as a comprehensive EAP replacement, customized for **Lockton** (April 2026).

## File Structure
```
index.html                     -- The entire deck (single file, self-contained)
lockton-logo-white.svg         -- Lockton logo (white SVG, rendered dark via CSS filter on light BGs)
hero-slide20.png               -- Hero image (woman on phone)
who-we-are-photo.jpg           -- Who We Are team photo
product-screens/               -- Product phone screenshots (cleaned up from Google Slides)
  ai-coach-slide2_*.png        -- AI Coach screens (slide 2 of product deck)
  brain-training-slide3_*.png  -- Brain training screens (slide 3 of product deck)
  assess-train-reassess_*.png  -- Brain assessment wheel screens
  reduce-negative_2.png        -- Self-care toolkit overview (6 tool categories)
  population-slide5_1.png      -- Population insights dashboard screenshot
  reflections_*.png             -- Reflections journaling screens
  mindfulness_*.png             -- Mindfulness exercise screens
  goal-setting_*.png            -- Goal setting screens
  ai-connect_0.png             -- AI Connect diagram
app-screens/                   -- Older placeholder images (not used in current deck)
```

## Slide Order (14 slides)
| # | Title | BG | Notes |
|---|-------|----|-------|
| 1 | Hero | cream | SM+TBS logo | Lockton logo, April 2026 |
| 2 | Who We Are | cream | Vision / photo / Mission |
| 3 | Meet Our Team | white | 6-person grid (VY, CS, RS, JM, EG, WK) |
| 4 | The Insight | navy | 3-col: Access Gap / Cost Crisis / SM Solution |
| 5 | The Solution | cream | 3-pillar overview: Self-Care & AI Coach / AI Connect / Engagement |
| 6 | AI Coach | white | Bullets + 2 phone screens |
| 7 | Brain Training | cream | Bullets + 2 phone screens |
| 8 | Self-Care Toolkit | white | Reflections/Mindfulness/Goals + wide product image |
| 9 | Engagement | cream | Engagement playbook + tiered engagement model |
| 10 | Population Insights | white | Insights+Trends / Actionable Programs + dashboard screenshot |
| 11 | AI Connect | cream | Provider matching bullets + 4 coverage stat boxes + payor logos |
| 12 | Quality Care | cream | 5 stat cards + 4 capability cards |
| 13 | Outcomes & ROI | navy | Brain Health / Risk Reduction / Financial Impact |
| 14 | Thank You | navy | Dual logos, closing question |

## Design System

### CSS Variables (`:root`)
```css
--lake: #004455;        /* Primary brand, navy text */
--lake-deep: #123e4f;
--lake-light: #dbf0f2;
--cream: #F5F0E8;       /* Warm background */
--gold: #e8bb25;        /* Accent, emphasis */
--gold-light: #f6e4a8;
--turquoise: #46b2b8;   /* Checkmarks, accent elements */
--text: #161616;        /* Body text */
--text-secondary: #595959;
--border: #ccdadd;
```

### Fonts
- **Headings**: Playfair Display (Google Fonts) -- serif, 500 weight
- **Body/UI**: proxima-nova (Adobe Typekit, ID `bnw6lfh`)
- **`<em>` inside headings**: Italic Playfair Display, colored `var(--lake)` on light BGs or `var(--gold)` on dark BGs

### Key CSS Classes
- `.slide` -- Full viewport, scroll-snap container
- `.slide-inner` -- Max-width 1200px content wrapper
- `.bg-cream`, `.bg-white`, `.bg-navy`, `.bg-lake`, `.bg-lake-light` -- Background variants
- `.phone-screen` -- Product phone screenshots (200px wide, 24px border-radius, subtle shadow)
- `.anim`, `.d1`-`.d4` -- Entrance animations triggered by `.slide.active`
- `.section-label` -- Uppercase small label above headings
- `.subtitle` -- Secondary text, max-width 600px
- `.pillars` / `.pillar` -- 3-column solution layout
- `.pillar-items` -- Bulleted list inside pillars

### Navigation
- Arrow keys (left/right), spacebar, Home/End
- Click progress dots at bottom
- Prev/Next buttons in floating nav bar
- Logo appears in top-left after slide 1

## Key Content Conventions
- **"Total Brain Solutions"** is the product/bundle name
- **"brain training"** (never "cognitive training")
- **"clinician-in-the-loop"** for AI oversight language
- **Stats must be defensible**: Sources cited on Insight slide (McKinsey, KFF, Milliman)
- **$3K+** (not $3,109) for 2-year savings per member
- **Lockton branding**: SM logo stacked with "Total Brain Solutions" text | divider | Lockton logo

## Source Presentations (Google Slides)
These were the content sources for images and text:
- `1AomGutFDK-NqpZ1n6xTcgeemZOgGq2V3dma4o0KkpoQ` -- Product images deck (cleaned phone mockups)
- `1cBeAanT10XpZ0bTqMLEXpHMKI87yksu6byVZgdSO0tc` -- Lockton pitch deck (engagement, population, insights content)
- `1QbM0VbGl_0DKgbO1WI1jb8ZjeP8OenFmk2x2TARcCbs` -- Denver campaign photography (hero image)
- `1tdGonFZx5Bx5ATGIRhPlDznJz8zhJz608qNfxCmtJDs` -- Who We Are photo source

## Brand Reference
- Full SonderMind brand book: `/Users/vyoung/Desktop/Clawdex/scratch/sondermind-brand/SONDERMIND_BRAND_BOOK.md`
- SM logo (dark on light): `../sondermind-brand/logo-header.svg`
- SM favicon: `../sondermind-brand/favicon-32.png`

## How to Edit
This is a single HTML file. All CSS is in a `<style>` block in `<head>`. All JS is in a `<script>` block at the end. No build step.

To add/remove slides:
1. Add/remove a `<div class="slide bg-X">` block in the `<div class="deck">` container
2. The JS auto-counts slides and generates navigation dots
3. Alternate backgrounds for visual rhythm: cream, white, navy

To swap product images:
1. Drop new PNGs into `product-screens/`
2. Update `src` attributes in the relevant slide
3. Use `class="phone-screen"` for consistent phone-sized treatment

To rebrand for a different client:
1. Replace "Lockton" text and logo on slides 1 and 14
2. Update "April 2026" date on slide 1
3. Swap `lockton-logo-white.svg` with the new client logo

## Agent Prompt for Continued Editing
If handing this to another AI agent, use this prompt:

```
You are editing a horizontal-scroll HTML pitch deck at index.html. It's a single-file deck with CSS scroll-snap, 14 slides, presenting SonderMind's "Total Brain Solutions" to Lockton.

Key rules:
- Use the /frontend-design skill for all visual changes
- Keep the SonderMind brand: Playfair Display headings, proxima-nova body, lake/cream/gold palette
- Product images go in product-screens/ and use class="phone-screen" for phone mockups
- Alternate slide backgrounds (cream/white/navy) for visual rhythm
- <em> tags inside headings render in gold on dark BGs, lake on light BGs
- "brain training" not "cognitive training", "clinician-in-the-loop" for AI oversight
- All stats must be defensible -- don't fabricate numbers
- The deck is TECH SOLUTION FORWARD: digital product first, care provider story second
- JS at the bottom auto-handles navigation, slide counting, and animations

Read HANDOFF.md for full context including slide order, CSS variables, file structure, and source presentations.
```
