# Master Document Template

**Purpose:** Universal document construction guide for all BGP portfolio brands. Pairs with `Brand_Assets_Registry` to produce consistent, on-brand documents across BPS, BGP, AGS, Buffalo Ridge Marketing, and future portfolio companies.

**Architecture:**
- This file defines **HOW** to build any document (layout, typography, components, document types).
- The Brand Assets Registry defines **WHO** (colors, logos, website, company-specific variables).
- Together they produce any branded document — proposal, one-pager, memo, board update, email, flyer, etc.

**Version:** 1.0
**Last updated:** April 18, 2026

---

## 1. Build-Time Workflow (What Claude Does)

When Stephen requests any branded document:

1. Clone the brand-assets repo: `git clone https://github.com/stephendappelt-alt/brand-assets.git`
2. Read this file: `brand-assets/Master_Document_Template.md`
3. Read the Brand Assets Registry to pull brand variables for the target company
4. Scrape the company's live website for current phone/address/tagline/services
5. Select the appropriate **document type** from Section 6
6. Assemble the document using **components** from Section 5, styled with brand variables
7. Validate and render a preview
8. Ship

---

## 2. Universal Page Setup

**These settings apply to EVERY document unless explicitly overridden:**

| Setting | Value | Notes |
|---|---|---|
| Page size | 8.5" x 11" (US Letter) | DXA: 12240 x 15840 |
| Top margin | 0.5" (720 DXA) | Tight for headers/footers |
| Bottom margin | 0.5" (720 DXA) | |
| Left margin | 0.75" (1080 DXA) | |
| Right margin | 0.75" (1080 DXA) | |
| Content width | 7" (10080 DXA) | Left + right margin subtracted |
| Default font | Arial | Universally supported, clean |
| Line spacing | Single (1.0) | |

**Exception:** For text-heavy documents (proposals, reports, memos), use 1.0" top/bottom margins instead of 0.5".

---

## 3. Typography Scale

All fonts are Arial. All colors reference the brand variable from the Registry.

| Use | Size | Weight | Color | Notes |
|---|---|---|---|---|
| Body text | 11pt (22 DXA half-points) | Regular | BLACK | Default for all paragraphs |
| Small text | 9pt (18 DXA) | Regular | MID_GRAY | Captions, fine print, secondary info |
| Label text | 7pt (14 DXA) | Bold | BRAND_ACCENT | Above stats, contact blocks (CALL 24/7, EMAIL, VISIT) |
| Section header | 11pt (22 DXA) | Bold ALL CAPS | BRAND_PRIMARY | With red underline divider |
| Subsection header | 11pt (22 DXA) | Bold | BRAND_PRIMARY | No underline |
| H1 / Page title | 22pt (44 DXA) | Bold | BRAND_PRIMARY | Hero statements |
| H2 | 14pt (28 DXA) | Bold | BRAND_PRIMARY | Major sections |
| H3 | 12pt (24 DXA) | Bold | BRAND_PRIMARY | Sub-sections |
| Stat number | 22pt (44 DXA) | Bold | BRAND_ACCENT | In stats band |
| Stat label | 8pt (16 DXA) | Bold | BRAND_PRIMARY | Under stat number |
| Callout text | 12pt (24 DXA) | Bold | Contextual | Hero text in callout bands |
| Footer text | 9pt (18 DXA) | Regular italic | MID_GRAY | Page numbers, fine print |

### Brand Variable Mapping

When the template references `BRAND_PRIMARY`, substitute the correct hex code from the brand being used:

| Variable | BPS | BGP | AGS | Buffalo Ridge Marketing |
|---|---|---|---|---|
| `BRAND_PRIMARY` | `#232B42` | `#212940` | `#496A95` | `#1a3a1a` |
| `BRAND_ACCENT` | `#B42127` | `#B32227` | `#90DE37` | `#c8a84b` |
| `BRAND_HIGHLIGHT` | `#EED24A` | `#FFFFFF` | `#90DE37` | `#c8a84b` |

**Universal (not brand-specific):**
- `BLACK` = `#0A0A0A`
- `MID_GRAY` = `#666666`
- `LIGHT_GRAY` = `#F5F5F5`
- `BORDER_GRAY` = `#CCCCCC`

---

## 4. Spacing System

Consistent vertical rhythm. Units in DXA (1440 DXA = 1 inch). Always use these values — never freestyle.

| Context | Before | After |
|---|---|---|
| Between paragraphs | 0 | 100 |
| Between bullets | 0 | 60 |
| After section header | 180 | 100 |
| After H1 | 240 | 200 |
| After H2 | 200 | 160 |
| After H3 | 140 | 100 |
| Before component band | 200 | 200 |
| Inside component cells | 80-140 top/bottom | varies by component |
| Page footer spacing | 200 top | 0 bottom |

**Rule:** If a section feels cramped, increase the `after` value on the preceding element. Never add blank paragraphs as spacers — use proper spacing values.

---

## 5. Component Library

**These are the reusable building blocks.** Every document is assembled from these components. Each component auto-adapts to the brand via variable substitution.

### 5.1 Header Band

**Purpose:** Top of every document. Anchors brand identity.

**Structure:**
- 2-column borderless table, full content width (10080 DXA)
- Left column (3600 DXA): Logo
- Right column (6480 DXA): Right-aligned tagline + contact

**Specs:**
- Logo: Use `*-logo-wide.png` from brand folder, render at size from Registry (BPS = 220x57)
- Logo alignment: Left, vertically centered
- Right column top line: Brand positioning statement (22pt bold, BRAND_PRIMARY)
- Right column second line: "24/7 Emergency: [PHONE]" or "Call: [PHONE]" (18pt, phone in BRAND_ACCENT bold)
- Followed by: red accent divider (24pt thick, BRAND_ACCENT), 120 before / 240 after

**When to use:** Every document. Always. No exceptions.

---

### 5.2 Hero Tagline

**Purpose:** Centered, large brand statement immediately after header.

**Structure:**
- Centered paragraph, 44pt bold BRAND_PRIMARY — tagline_hero
- Centered paragraph, 22pt italic BRAND_ACCENT — tagline_sub

**Specs:**
- Spacing before hero: 80, after: 40
- Spacing before sub: 0, after: 300

**When to use:** One-pagers, flyers, landing-page-style docs. Skip for memos, board updates, internal docs.

---

### 5.3 Section Header

**Purpose:** Break document into scannable sections.

**Structure:**
- Single line, 11pt BOLD ALL CAPS, BRAND_PRIMARY
- Red underline divider (12pt thick, BRAND_ACCENT, 4pt space below text)

**Specs:**
- Spacing before: 180, after: 100
- Font: Arial 22 DXA half-points, bold, ALL CAPS

**When to use:** Every major section of every document. More scannable than H2s in body docs.

---

### 5.4 Stats Band

**Purpose:** Hero-sized numbers with small labels. Drives visual impact.

**Structure:**
- Single row, 4 equal-width columns (2520 DXA each)
- Background: LIGHT_GRAY
- Each cell: stat number on top (centered, 44pt bold BRAND_ACCENT), label below (centered, 8pt bold BRAND_PRIMARY)
- Cell margins: top/bottom 120, left/right 80

**Specs:**
- Number: 22pt (44 DXA), bold, BRAND_ACCENT
- Label: 8pt (16 DXA), bold, BRAND_PRIMARY
- Spacing around band: 200 before, 200 after

**When to use:** One-pagers, proposals, board updates. 4 stats minimum. Examples: "2hr / 70% / 85%+ / 24/7", "500+ / $2M / 12 years / 100%".

---

### 5.5 Services Grid

**Purpose:** Display 4-8 services or offerings in a clean bordered grid.

**Structure:**
- 2 equal columns (5040 DXA each)
- 2-4 rows
- Each cell: bordered, white fill
- Cell content: bold service title (11pt BRAND_PRIMARY) + description (10pt BLACK)

**Specs:**
- Cell padding: 80 top/bottom, 140 left/right
- Border color: BORDER_GRAY
- Title to description spacing: 40 after title

**When to use:** One-pagers, proposals, capability docs.

---

### 5.6 Call-Out Band (Navy Bar)

**Purpose:** High-contrast statement bar. Draws the eye.

**Structure:**
- Full content width single cell
- Background: BRAND_PRIMARY fill
- Centered label on top (7pt bold WHITE, ALL CAPS)
- Centered main text below (12pt bold BRAND_HIGHLIGHT)

**Specs:**
- Cell padding: 140 top/bottom, 200 left/right
- Label example: "INDUSTRIES SERVED"
- Main text example: "Residential • Commercial • Industrial • Healthcare"

**When to use:** One-pagers, proposals. Use sparingly — 1 per document max or it loses impact.

---

### 5.7 CTA Footer

**Purpose:** Close every client-facing document with clear next step.

**Structure:**
- Red accent divider (24pt, BRAND_ACCENT) above
- Centered bold headline (13pt BRAND_PRIMARY)
- Centered italic subhead (10pt BLACK)
- 3-column borderless contact table: CALL / EMAIL / VISIT
- Each column: 7pt bold BRAND_ACCENT label + bold contact value
- Address line below (centered, 8pt MID_GRAY)

**Specs:**
- Column widths: 2880 / 4320 / 2880 DXA (email wider to prevent wrapping)
- Header: 22pt BOLD ALL CAPS, BRAND_PRIMARY
- Contact values: 18-22pt bold, BRAND_PRIMARY
- Contact labels above values: 7pt bold, BRAND_ACCENT

**When to use:** One-pagers, flyers, proposals, any client-facing doc. Skip for internal memos.

---

### 5.8 Two-Column Body

**Purpose:** Text-heavy content blocks (About, Philosophy, Executive Summary).

**Structure:**
- Full-width paragraph OR 2-column table (equal widths) for dense content
- 11pt Arial body, BLACK
- Paragraph spacing: 100 after

**When to use:** About sections, executive summaries, narrative content. Default to single-column unless the doc is proposal-length.

---

### 5.9 Data Table

**Purpose:** Structured comparison or reference data.

**Structure:**
- First row: BRAND_PRIMARY header with WHITE bold text
- Body rows: alternating WHITE and LIGHT_GRAY shading
- Cell padding: 80 top/bottom, 120 left/right
- Border: 4pt BORDER_GRAY on all sides

**Specs:**
- Header text: 11pt bold WHITE, Arial
- Body text: 10pt regular BLACK, Arial
- Column count: Flexible; ensure widths sum to table width
- **Always use DXA widths**, never percentages (breaks in Google Docs)

**When to use:** Pricing, comparisons, specs, rosters.

---

### 5.10 Pull Quote / Testimonial Band

**Purpose:** Highlighted customer quote or key statement.

**Structure:**
- Indented left side with vertical red bar (BRAND_ACCENT)
- 13pt italic BRAND_PRIMARY quote text
- Smaller attribution below (10pt MID_GRAY)

**When to use:** Proposals, case studies, one-pagers. Max 1 per doc.

---

### 5.11 Signature Block

**Purpose:** Close memos, letters, board updates, proposals.

**Structure:**
- Small spacer
- Name (11pt bold BLACK)
- Title (10pt BLACK)
- Company (10pt BLACK)
- Date (10pt MID_GRAY italic)

**When to use:** Memos, board updates, cover letters, proposal cover pages.

---

## 6. Document Type Recipes

**Every document type = a specific chain of components.** Claude picks the recipe based on what Stephen requests.

### 6.1 ONE-PAGER

**Use case:** Company overview, service summary, BD handout.

**Component chain:**
1. Header Band (5.1)
2. Hero Tagline (5.2)
3. Section Header "WHO WE ARE" (5.3)
4. Two-Column Body — About + Philosophy (5.8)
5. Stats Band (5.4)
6. Section Header "CORE SERVICES" (5.3)
7. Services Grid — 6 services in 2x3 (5.5)
8. Call-Out Band "INDUSTRIES SERVED" (5.6)
9. CTA Footer (5.7)

**Length:** 1 page, fits exactly.

---

### 6.2 PROPOSAL

**Use case:** Client proposals, sales decks in doc form.

**Component chain:**
1. Cover Page: Header Band + large project title + client name + date
2. Page break
3. Section Header "EXECUTIVE SUMMARY" + body
4. Section Header "SCOPE OF WORK" + Services Grid
5. Stats Band — client-relevant metrics
6. Section Header "PRICING" + Data Table
7. Section Header "TERMS & CONDITIONS" + body
8. Pull Quote (optional) — customer testimonial
9. CTA Footer + Signature Block

**Length:** 4-10 pages.

---

### 6.3 MEMO

**Use case:** Internal communication, strategy memos, position papers.

**Component chain:**
1. Header Band (5.1) — compact version
2. To/From/Date/Subject table (5.9 style)
3. Body paragraphs with Section Headers (5.3) as needed
4. Signature Block (5.11)

**Length:** 1-3 pages.

**Difference from one-pager:** No hero tagline, no stats band, no call-out band, no CTA footer. Pure content.

---

### 6.4 BOARD UPDATE

**Use case:** BGP board/investor reporting.

**Component chain:**
1. Header Band (5.1)
2. Period title: "Q[X] 20[XX] Board Update" centered H1
3. Section Header "KEY METRICS" + Stats Band (5.4)
4. Section Header "COMMENTARY" + body
5. Section Header "ACTION ITEMS" + numbered list
6. Section Header "RISKS & FLAGS" + bullet list
7. Data Table — variance to budget (if applicable)
8. Signature Block

**Length:** 2-4 pages.

---

### 6.5 FLYER (single-page marketing)

**Use case:** Promotional flyers, event announcements, special offers.

**Component chain:**
1. Header Band (5.1)
2. Red "LIMITED TIME" or urgency banner (full-width, BRAND_ACCENT fill, 20pt bold WHITE)
3. Hero Headline — 48pt bold BRAND_PRIMARY, 3 lines centered
4. Offer statement — 88pt bold BRAND_ACCENT (e.g., "$1,000 OFF")
5. Sub-headline — 17pt bold BRAND_PRIMARY
6. Bulleted value props — 4 items with BRAND_ACCENT checkmarks
7. CTA Footer (5.7) — with fine print above

**Length:** 1 page, denser than one-pager.

---

### 6.6 EMAIL HEADER TEMPLATE

**Use case:** Email signatures, email header graphics.

**Component chain:**
1. Header Band (5.1) — render at 180x47 for email-size logo
2. Tagline line below header
3. Contact line — phone, email, website inline

**Length:** Compact, under 2 inches tall.

---

### 6.7 CAPABILITY STATEMENT (gov/enterprise)

**Use case:** Federal contracting, enterprise RFPs, Sodexo/CBRE-style prospects.

**Component chain:**
1. Header Band (5.1) — include "CAGE Code / DUNS / NAICS" line if applicable
2. Section Header "CORE CAPABILITIES"
3. Services Grid (5.5)
4. Section Header "DIFFERENTIATORS"
5. Bullet list — top 3-5 differentiators
6. Stats Band (5.4)
7. Section Header "PAST PERFORMANCE"
8. Data Table — client | project | contract value | outcome
9. Call-Out Band "NAICS CODES" or "CONTRACT VEHICLES"
10. CTA Footer + Signature Block

**Length:** 1-2 pages.

---

## 7. Brand-Specific Overrides

**Default:** every document follows this template exactly, substituting brand variables from the Registry.

**Overrides allowed only when:**
- Brand color contrast breaks readability (e.g., BRM's dark green on black Callout Band won't work — fall back to BRM dark green on WHITE)
- A component's default color produces a brand clash (flag to Stephen before building, don't auto-override silently)
- Stephen explicitly requests a one-off variation

### Buffalo Ridge Marketing

- No white-knockout logo yet → on any component requiring dark background logo (dark-mode Header Band, Call-Out Band with logo), fall back to regular logo on white chip, or skip logo.
- `BRAND_HIGHLIGHT` = gold `#c8a84b`, use same way BPS uses gold (accents only, never text fills).

### AGS Scientific

- Lime green is vibrant — use as accent only, never as large fills. Pair with slate blue (`#496A95`) as primary.
- AGS is a distributor — capability statements should mention manufacturer partners (NIC, A.KRÜSS Optronic).

### BGP

- More buttoned-up than BPS — reduce Hero Tagline size and skip Call-Out Band in favor of cleaner layouts.
- Board-facing docs: always include Signature Block with "Stephen D. Appelt, VP Sales & Marketing" or as appropriate.

### BPS

- Gold `#EED24A` used ONLY in lightning bolt element or in Call-Out Band highlight text. Never body text or large fills.
- Standard docx logo render: 220x57 (locked).

---

## 8. Quality Control Checklist

**Before shipping any document, verify:**

- [ ] Logo is the correct variant for background (wide on light, white on dark)
- [ ] Logo is rendered at the correct size from Registry
- [ ] All colors match the brand's locked palette — no off-brand hex codes
- [ ] Phone number, email, address pulled LIVE from website (not hardcoded)
- [ ] Tagline pulled LIVE from website
- [ ] Document fits intended page count (one-pager = 1 page exactly)
- [ ] Typography scale applied consistently (no random font sizes)
- [ ] Spacing system followed (no blank paragraph spacers)
- [ ] Red accent dividers present under section headers
- [ ] Tables use DXA widths (not percentages)
- [ ] PDF preview rendered and visually inspected before shipping

---

## 9. Expanding This System

### Adding a new component

1. Propose it to Stephen with a preview
2. Once approved, add to Section 5 with full specs
3. Reference it in relevant Document Types in Section 6

### Adding a new document type

1. Identify the component chain
2. Add to Section 6 with use case and length spec
3. Test-build once and have Stephen approve

### Adding a new brand

1. Add to Brand Assets Registry (colors, logos, website)
2. Review Section 7 for brand-specific overrides needed
3. No changes needed to this Master Template — it auto-adapts via brand variables

---

## 10. What Not to Do

**Hard rules. Breaking these damages brand consistency:**

- ❌ Never mix colors across brands (BPS navy on a BGP doc is wrong)
- ❌ Never hardcode phone numbers, addresses, or taglines — always scrape live
- ❌ Never use Unicode bullet characters in the raw text (•, ‣, ▪) — use LevelFormat.BULLET
- ❌ Never use blank paragraphs for spacing — use the spacing system
- ❌ Never render a logo at a size not specified in the Registry without a reason
- ❌ Never use percentage widths on tables (breaks in Google Docs)
- ❌ Never use ShadingType.SOLID — always CLEAR (SOLID renders as black)
- ❌ Never ship without a preview/validation step
- ❌ Never improvise fonts — Arial only unless Stephen explicitly approves a serif

---

## 11. Version History

| Date | Version | Changes |
|---|---|---|
| 2026-04-18 | v1.0 | Initial master template. Component library approach. 7 document types defined. |

---

**End of Master Document Template. Save to: `brand-assets/Master_Document_Template.md` at repo root.**
