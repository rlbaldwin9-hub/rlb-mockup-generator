# RLBDesigns — Product Listing Mockup Generator

**Version:** 1.4 &nbsp;|&nbsp; **Author:** Rachel Baldwin &nbsp;|&nbsp; **Brand:** [RLBDesigns.com](https://www.rlbdesigns.com)

> A browser-based tool for generating professional product listing images for Etsy, eBay, and your own website — no design software required. Fill in your product details, pick a layout, and download a print-ready JPG or SVG in seconds.

---

## Live Tool

**[Launch the Mockup Generator](https://rlbaldwin9-hub.github.io/rlb-mockup-generator)**

Embed URL for Google Sites:
```
https://rlbaldwin9-hub.github.io/rlb-mockup-generator
```

---

## What It Does

| Feature | Details |
|---------|---------|
| **3 Platform Presets** | Etsy (10 image slots), eBay (12 slots), Website (5 slots) |
| **6 Layout Templates** | Hero/Main, What's Included, How It Works, Bundle/Variants, Lifestyle, Detail Close-Up |
| **16 Color Schemes** | 8 Classic + 8 Pastel — switch with one click |
| **Badge System** | 5 category tabs — Universal, Digital Downloads, Physical Books, AI App/URL, Health/Wellness |
| **Image Shape Picker** | Square 1:1, Portrait 4:5, Portrait 2:3, Landscape 5:4 |
| **Editable Layout Fields** | Every layout has its own editable content panel in the sidebar |
| **SVG + JPG Download** | High-res 3× scale JPG export, SVG for further editing in Canva |
| **Canva Build Spec** | One-click copy of full hex colors, fonts, sizes, and slot list for Canva |
| **Readiness Checklist** | Live 7-item checklist tracks listing completeness |
| **Platform Spec Sheet** | Exact pixel sizes and pro tips for every image slot |

---

## Product Format Support

- Digital Download (PDF / JPG-PNG / .ZIP)
- Canva Template Access
- Physical Print Book
- Physical Print (Other)
- AI App URL — Free / Paid / Subscription / Bundle

---

## How to Use

1. **Select your platform** — Etsy, eBay, or Website
2. **Fill in product info** — title, subtitle, price (or FREE), format, and what's included
3. **Select feature badges** — browse by category tab, click to toggle on/off
4. **Choose a layout** — pick from 6 templates, edit the content fields that appear below
5. **Pick an image shape** — sets the placeholder proportion in Hero, Lifestyle, and Close-Up layouts
6. **Choose a color scheme** — Classic or Pastel swatches
7. **Click Generate** — preview appears instantly
8. **Download** — SVG (for Canva editing) or JPG (ready to upload directly)

---

## Color Schemes

### Classic
| Name | Header Color |
|------|-------------|
| Forest Green | `#2D6A4F` |
| Royal Purple | `#7A1FA0` |
| Warm Gold | `#A0720A` |
| Deep Navy | `#1A3A6B` |
| Festive Coral | `#C0392B` |
| Ocean Teal | `#0A7B7B` |
| Dark Brown | `#3D2B1F` |
| Neutral Slate | `#3A3A3A` |

### Pastels
| Name | Header Color |
|------|-------------|
| Baby Blue | `#6AAED6` |
| Mint | `#6DC8A0` |
| Rose | `#E89BB4` |
| Lilac | `#B49FCC` |
| Peach | `#E8A87C` |
| Sage | `#8AAE92` |
| Light Tan/Brown | `#C4A882` |
| Cream | `#C8B090` |

---

## Technical Details

### Stack
- **Pure HTML / CSS / JavaScript** — zero dependencies, no build step, no framework
- **Single file** — entire app lives in `index.html`
- **No server required** — runs as a static page

### Download Architecture
All downloads use **Base64 `data:` URIs** — no `Blob` URLs. This is required for compatibility with GitHub Pages Content Security Policy (CSP), which blocks `URL.createObjectURL()`.

```
SVG:  btoa(unescape(encodeURIComponent(svgString))) → data:image/svg+xml;base64,...
JPG:  SVG data URI → Image() → Canvas (3× scale) → toDataURL("image/jpeg", 0.95)
```

### JPG Output Quality
- Renders at **3× scale** (1740px+ on shortest side)
- White background fill before canvas draw
- 95% JPEG quality
- Suitable for direct Etsy upload (2000px minimum met)

### SVG Design
- Fixed `width="580"` and explicit `height` on every generated SVG
- Georgia serif font (system font — no loading required)
- All text truncated to prevent overflow
- No emoji in SVG text elements (cross-browser rendering unreliable)

---

## File Structure

```
rlb-mockup-generator/
└── index.html          ← Entire application (HTML + CSS + JS)
└── README.md           ← This file
```

That's it. One file runs the whole tool.

---

## Updating the Tool

1. Download the new `index.html` from Claude
2. In this repo, click `index.html` → three-dot menu → **Delete file** → Commit
3. Click **Add file → Upload files** → drop the new `index.html` → Commit
4. GitHub Pages redeploys automatically in ~60 seconds
5. Hard refresh (`Ctrl+Shift+R`) to clear cache

---

## Related Tools & Links

| Tool | URL |
|------|-----|
| Coloring Book Prompt Generator | [prompts.rlbdesigns.com](https://prompts.rlbdesigns.com) |
| AI Product Page Generator | [rlb-product-page-gen.pages.dev](https://rlb-product-page-gen.pages.dev) |
| Review Form | [rlbaldwin9-hub.github.io/rlb-review-form](https://rlbaldwin9-hub.github.io/rlb-review-form) |
| Cookbook App | [rlbaldwin9-hub.github.io/cookbook-app](https://rlbaldwin9-hub.github.io/cookbook-app) |
| Reading Journal | [rlbaldwin9-hub.github.io/rlb-reading-journal](https://rlbaldwin9-hub.github.io/rlb-reading-journal) |
| RLBDesigns Website | [rlbdesigns.com](https://www.rlbdesigns.com) |

---

## Roadmap

- [ ] Saved Presets — save & reload frequently-used product configurations
- [ ] Brand Watermark — optional RLBDesigns.com overlay with opacity control
- [ ] Social Media Cut-Downs — Instagram, Pinterest, Facebook sized exports
- [ ] Reviews Layout — 7th template for customer quotes and star ratings
- [ ] FAQ Layout — 8th template for top buyer questions

---

## Badge Categories

### Universal
Instant Download · Personalized · Free Revisions · Best Seller · New Arrival · Award Winner · Gift Ready · Limited Edition · Eco Friendly · Made with Love

### Digital Downloads
Print Ready · High-Res 300 DPI · PDF Included · JPG + PNG Included · ZIP Bundle · Canva Editable · Commercial License · No Subscription Needed · Edit in Canva · Lifetime Access

### Physical Books
Signed Copy Available · Paperback · Hardcover · Full Color Interior · Ages 0-4 · Ages 5-9 · Ages 9-13 · Adult Coloring · KDP Published · Amazon Available · Autographed Option

### AI App / URL
Free to Use · Free Tier Available · Paid Pro Access · Subscription Access · No App Download · Works in Browser · Mobile Friendly · Instant Access · Beginner Friendly · Step-by-Step Guide · Video Tutorial Included · Claude Powered · AI-Assisted · Prompt Included

### Health / Wellness
Alpha-Gal Safe · Mammal-Free · Dairy-Free · Gluten-Free Option · Clean Eating · Garden to Table · AGS Compliant · Allergy Friendly · Chemo-Supportive · Nutritionist Reviewed

---

## Brand

**RLBDesigns** is the creative brand of Rachel L. Baldwin — indie author, graphic designer, and publisher based in rural Missouri. Specializing in children's books, Alpha-Gal Syndrome compliant cookbooks, adult and children's coloring books, and AI-assisted publishing tools for new authors.

- **Etsy:** [RLBDesigns on Etsy](https://www.etsy.com/shop/RLBDesigns)
- **Amazon KDP:** Search "Rachel L. Baldwin"
- **Website:** [rlbdesigns.com](https://www.rlbdesigns.com)

---

*Built with Claude AI · Hosted on GitHub Pages · &copy; 2026 RLBDesigns*
