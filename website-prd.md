# Fien Studio — Website PRD
**Shopify Theme: Dawn (customized)**
**Store:** brandonfienlimited.myshopify.com → fienstudio.com
**Owner:** Brandon Fien — outdoor & wildlife fine art photographer

---

## 1. Brand Overview

Brandon Fien sells limited-edition fine art prints and photography services. The brand occupies a dark-luxury niche: museum-quality prints for collectors and interior designers, not mass-market décor. Every design decision should reinforce scarcity, craft, and the emotional weight of wild places.

### Brand voice
- Minimal, evocative, never promotional
- Sentence case everywhere (not Title Case)
- Short declarative phrases for headings; longer, lyrical copy in body/italic serif
- No exclamation marks, no "shop now!", no hyperbolic adjectives ("stunning", "amazing")
- OK: "Each print is produced in an edition of 50." Not OK: "Get your stunning print today!"

---

## 2. Design System

### Color tokens
| Token | Value | Usage |
|---|---|---|
| `--black` | `#080808` | Page background |
| `--deep` | `#0e0e0e` | Alternate section background |
| `--dark` | `#161616` | Card backgrounds |
| `--mid` | `#1e1e1e` | Input backgrounds, hover states |
| `--border` | `rgba(255,255,255,0.07)` | All dividers and card borders |
| `--gold` | `#c9a84c` | Primary accent: CTAs, labels, prices, active states |
| `--gold-light` | `#e8c97a` | Gold hover state |
| `--white` | `#f0ece4` | Body text (warm off-white, not pure white) |
| `--muted` | `rgba(240,236,228,0.5)` | Secondary text, placeholders |

### Typography
| Role | Font | Weight | Size | Letter-spacing |
|---|---|---|---|---|
| Display / headings | Bebas Neue | 400 | `clamp(5rem, 12vw, 11rem)` hero; `clamp(2.5rem, 5vw, 4rem)` section | `0.04–0.1em` |
| Serif body / quotes | Cormorant Garamond | 300 / 400 italic | `1.05–1.4rem` | normal |
| UI / labels / nav | Montserrat | 300 / 400 / 500 | `0.55–0.8rem` | `0.15–0.4em` |
| Prices | Bebas Neue | 400 | `1.5rem` | `0.05em` |
| Eyebrows / tags | Montserrat | 400 | `0.55–0.65rem` | `0.2–0.4em`, uppercase |

**Font loading:** Google Fonts preconnect. Load `Bebas+Neue`, `Cormorant+Garamond:ital,wght@0,300;0,400;1,300;1,400`, `Montserrat:wght@300;400;500`.

### Spacing scale
Sections: `120px` top/bottom padding desktop; `80px` mobile.
Horizontal page padding: `60px` desktop; `24px` mobile.

### Interactive states
- All interactive elements transition `0.3s ease`
- Hover on gold elements: shift to `--gold-light`, `translateY(-2px)`
- Border reveals on cards: gold underline animates `scaleX` from 0→1 on `:hover`
- Custom cursor: 6px gold dot + 36px gold ring (desktop only; disable on touch devices)

### Animations
| Name | Behavior |
|---|---|
| `fadeUp` | `opacity 0 → 1`, `translateY(30px → 0)`, staggered 0.3s delays on hero |
| `reveal` | Intersection Observer; `opacity 0 → 1`, `translateY(40px → 0)`, 0.8s ease |
| `scrollPulse` | Scroll indicator line opacity 0.4 → 1 → 0.4, 2s loop |

---

## 3. Product Catalog

### Print formats
| Format | Description |
|---|---|
| Metallic | Lustre metallic paper; rich depth; most popular |
| Canvas | Gallery-wrapped canvas; frameless option |
| Aluminum | Metal dibond; modern, borderless; high contrast |

### Size & price matrix (approximate)
| Size | Metallic | Canvas | Aluminum |
|---|---|---|---|
| 8×10 | $95 | $115 | $125 |
| 11×14 | $145 | $175 | $195 |
| 16×20 | $245 | $295 | $325 |
| 20×30 | $395 | $475 | $525 |
| 24×36 | $595 | $695 | $795 |
| 30×45 | $1,150 | $1,295 | $1,450 |

All prints are limited editions of 50. Each ships with a certificate of authenticity. Prices shown include the print; framing quoted separately on request.

### Photography services
- **Commercial** — Brand campaigns, editorial, advertising
- **Expedition** — Multi-day wilderness assignments
- **Fine art commissions** — Custom location/subject shoots for collectors

---

## 4. Page-by-Page Specs

### 4.1 Home (`/`)

**Hero section**
- Full-viewport height (`100vh`, min 700px)
- Background: looping video (muted, autoplay, `opacity: 0.45`, `brightness(0.6) saturate(0.8)`) with overlay gradients bleeding into `--black` at bottom. Fallback: dark green gradient placeholder when no video.
- Overlay gradients: `linear-gradient(to bottom, rgba(5,5,5,0.6) 0%, rgba(5,5,5,0.3) 45%, rgba(5,5,5,0.82) 85%, #080808 100%)` + left-side vignette.
- Content positioned bottom-left (`padding: 0 60px 80px`)
- Eyebrow: `OUTDOOR & WILDLIFE PHOTOGRAPHY` in gold, 0.6rem, 0.4em tracking
- H1: `BRANDON FIEN` / `STUDIO` — second word in gold, stacked
- Subtitle: Cormorant italic, muted color, max-width 500px
- CTAs: primary gold button ("View prints") + outline button ("Photography services")
- Scroll indicator: bottom-right, gold animated line + "SCROLL" label

**Portfolio / gallery section** (background: `--deep`)
- Section number decorative (Bebas, 4rem, gold at 15% opacity)
- Filter buttons: All / Wildlife / Landscape / Aerial / Black & White
- Grid: 4 columns desktop, 2 columns mobile
- Cards: `aspect-ratio: 3/4`, overflow hidden
- On hover: image scales 1.04, overlay fades in from bottom (gradient + title + format/price tags)
- Featured item (first) spans 2 rows (larger visual weight)

**Featured prints section** (background: `--black`)
- Intro paragraph: Cormorant italic, muted, max-width 600px
- Grid: 3 columns desktop, 1 column mobile
- Print card anatomy:
  - Image (`aspect-ratio: 4/3`)
  - Body: title (Cormorant serif), edition label (gold, uppercase), format tags (outline pills), pricing accordion
  - Footer row: price (Bebas, gold) + "Select options" button
- Pricing accordion: expand/collapse per format (Metallic / Canvas / Aluminum) showing size→price table

**Video / behind-the-scenes section** (background: `--deep`)
- 2-column grid of video thumbnails (16/9 aspect ratio)
- Each card: thumbnail + play button (gold ring) + type badge + title
- On hover: play button fills gold, scales 1.1

**Services / hire section** (background: `--black`)
- Intro paragraph Cormorant italic
- 3-column service cards with hover gold underline reveal
- Service icon: Bebas large text at 20% gold opacity (decorative)
- Process steps: 4-column horizontal timeline grid

**About section** (background: `--deep`)
- 2-column grid: photographer portrait left, text right
- Portrait: `aspect-ratio: 3/4`, decorative gold-border frame offset bottom-right
- Stats row: 3 columns (Years Active / Editions Sold / Countries)
- Text: Cormorant serif body, Bebas heading

**Contact section** (background: `--black`)
- 2-column: contact details left, form right
- Form fields: dark backgrounds, gold border on focus
- Field labels: Montserrat 0.55rem uppercase, muted color
- CTA: full-width gold submit button

**Footer**
- Single row: logo left, copyright center, social links right
- Background: `--deep`, top border `--border`
- Social links: Instagram, YouTube (text links)

---

### 4.2 Collection page (`/collections/prints`)
- Full-width header with collection title and description
- Filter/sort bar: format filter (All / Metallic / Canvas / Aluminum) + sort (Price: low–high, Newest)
- Product grid: 3 columns desktop, 2 columns tablet, 1 column mobile
- Product card: image, title, edition info, starting price, format tags
- Load more button (not infinite scroll — maintain URL state for sharing)

### 4.3 Product page (`/products/[handle]`)
- Large image gallery left (swipeable), product details right
- Gallery: main image + thumbnail strip; supports zoom on click
- Details panel:
  - Title (Cormorant, large)
  - Edition count + certificate badge
  - Format selector: three radio-style cards (Metallic / Canvas / Aluminum) each with short description
  - Size selector: dropdown or button group, updates price dynamically
  - Price: Bebas gold, large
  - Quantity: limited (1 per size/edition enforced via inventory)
  - Add to cart: full-width gold button
  - Accordion: Print details / Shipping & framing / Certificate of authenticity
- Below fold: "You may also like" — 4 related products
- No reviews section (brand decision — see §7)

### 4.4 Cart (`/cart`)
- Minimal dark table layout
- Each line item: thumbnail, title, format, size, edition note, price, remove
- Order summary panel: subtotal, shipping note, checkout button
- No upsell popups

### 4.5 About (`/pages/about`)
- Full-page version of the about section from home
- Extended biography in Cormorant serif
- Press/feature logos (grayscale, gold on hover)
- Equipment/process section

### 4.6 Services (`/pages/services`)
- Full-page version of hire section
- Detailed service cards + process timeline
- Contact CTA at bottom linking to `/pages/contact`

### 4.7 Contact (`/pages/contact`)
- Full-page version of contact section
- Form fields: name, email, inquiry type (dropdown), message
- No phone number displayed publicly

---

## 5. Navigation

### Desktop nav
- Fixed, transparent → `rgba(8,8,8,0.97)` + bottom border on scroll
- Logo: `FIEN` `STUDIO` (second word in gold)
- Links: Portfolio / Prints / Services / About / Contact
- Nav link style: 0.65rem Montserrat, 0.2em tracking, uppercase, muted → white on hover, gold underline animates in
- No cart icon in nav (checkout handled via product page flow into Shopify cart)

### Mobile nav
- Hamburger menu icon (top right)
- Full-screen overlay, dark background
- Links stacked vertically, large Bebas Neue

---

## 6. Typography Rules

1. **Never use Bebas Neue below 1.2rem** — it becomes illegible at small sizes; use Montserrat for UI text.
2. **Cormorant Garamond body text** is always weight 300, line-height 1.8–1.9.
3. **Italic Cormorant** is for quotes, taglines, section intros — not body paragraphs.
4. **All-caps Montserrat** is for labels, tags, nav, buttons, form labels only.
5. **Prices** always use Bebas Neue in `--gold`.
6. **Sentence case** for all user-facing strings including button labels and section titles.
7. **Letter-spacing on Montserrat** varies by size: larger tracking (0.3–0.4em) at small sizes (0.55–0.65rem); reduce to 0.15em at 0.8rem+.

---

## 7. What NOT to Include

- No pop-ups (newsletter, discount, exit-intent) — ruins the luxury atmosphere
- No countdown timers or "X people viewing this" urgency tactics
- No star ratings or review widgets on product pages
- No chat widget or support bubble
- No social proof banners ("As seen in...")
- No sale badges or strikethrough pricing — prints are priced at value, not discounted
- No Shopify "Powered by Shopify" footer link (remove via theme)
- No cookie consent banner above the fold (use a minimal bottom bar if legally required)
- No related products carousel with autoplay
- No breadcrumb navigation — site is shallow enough to not need it

---

## 8. Mobile Specifications

| Element | Desktop | Mobile |
|---|---|---|
| Section padding | `120px 60px` | `80px 24px` |
| Nav padding | `24px 60px` | `20px 24px` |
| Portfolio grid | 4 columns | 2 columns |
| Prints grid | 3 columns | 1 column |
| Services grid | 3 columns | 1 column |
| Video grid | 2 columns | 1 column |
| Process steps | 4 columns | 2 columns |
| About layout | 2 columns | 1 column (portrait above text) |
| Contact layout | 2 columns | 1 column |
| Footer | horizontal row | stacked, centered |
| Custom cursor | enabled | disabled |
| Hero title | `clamp(5rem, 12vw, 11rem)` | scales down via clamp |

Touch targets: minimum 44×44px for all interactive elements. Gold outline buttons must have sufficient contrast on dark backgrounds.

---

## 9. Performance & Technical Notes

- **Critical CSS** inlined via `critical.css` asset — covers above-fold styles only
- **Fonts** loaded via Google Fonts with `display=swap`; subset to used weights
- **Hero video** — lazy-loaded on scroll for mobile; autoplay muted on desktop only
- **Images** — all via Shopify CDN `image_url` filter with explicit `width` parameters; use `loading="lazy"` for below-fold
- **No third-party tracking scripts** beyond Shopify Analytics and a single Meta Pixel (if used) — keep clean
- **Liquid translations** — all user-facing strings in `locales/en.default.json`; no hardcoded English copy in templates
