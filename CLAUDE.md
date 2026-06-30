# Moco Meats — Internal Digital Platform
## Claude Code Project Handoff

---

## How to use this document

This is the master handoff brief for the Moco Meats internal sales platform. Read it fully before touching any file. Every design decision, content decision, and build decision in here has been locked through prior sessions — do not deviate from them unless explicitly instructed.

---

## ⚠️ Document Maintenance — Read This Every Session

**This document MUST be updated at the end of every build session or completed milestone.**

After every session in Claude Code or Claude.ai:
1. Update the build status tables for any completed stages or assets
2. Update the file structure table with any new files created
3. Document any new design or content decisions that were locked
4. Capture any new ideas in the Parked section — do not let them live only in your head
5. Download the updated CLAUDE.md and replace the version in the GitHub repo

**Why this matters:** This document is the single source of truth for the entire platform. If it falls out of date, future sessions in any tool will build on stale assumptions and undo decisions that were already made. Five minutes updating this file at the end of a session saves hours of rework.

**The big picture:** The goal is 18 assets (17 tools + 1 hub) that connect into a single platform a rep can open on their phone before any customer visit. Every individual build decision should serve that goal. When a new idea surfaces mid-session, note it in the Parked section and stay on the current stage. Tangents are worth capturing — they should never interrupt the build sequence.

---

## Project Overview

**What we're building:** A comprehensive internal digital platform for Moco Food Services field sales representatives. A suite of interconnected tools, quizzes, simulators and references — all built on a consistent design language — that trains, equips and supports the sales team in the field.

**The end goal:** A sales rep can open their phone before walking into a venue and access everything they need — product knowledge, sales coaching, territory context, pricing tools and conversation practice — in one place, from one link, that works like an app.

**Primary user:** Field sales reps at Moco Food Services. Territory covers South East Queensland (Brisbane, Gold Coast, Sunshine Coast, Toowoomba) and Northern Rivers NSW (Byron Bay, Ballina, Lismore, Tweed Heads). Venues served: pubs, clubs, restaurants, cafes. **All team members use iPhone.** Every build decision should optimise for iPhone Safari first.

**Platform philosophy:**
- App-like experience, browser-based — no installation, no app store
- Works on mobile, iPad and desktop — mobile first
- Single consistent design language across all tools
- Each tool is a standalone HTML file — CSS + JS + content in one file
- Built iteratively — brand guide first, everything else follows

---

## Full Platform Scope — 17 Assets + 1 Hub

### Module 1 — Sales Skills
*SPIN selling, objection handling, negotiation*

| # | Type | Description | Status |
|---|------|-------------|--------|
| 1 | Tool | 10 objections, SPIN coaching feedback, rebuttal builder | ✅ Drafted in GitHub — needs design polish to match platform design system |
| 2 | Tool | Prebuilt SPIN question sets by customer type + AI custom generator | 🔄 Drafted, needs finalising |
| 3 | Simulator | Choose-your-path sales conversations, scored outcomes | ⬜ To build |
| 4 | Tool | Pre-call checklist, customer research template, goal setter | ⬜ To build |
| 5 | Quiz | Identify the question type, rank the sequence, pick the best response | ⬜ To build |

### Module 2 — Product Knowledge
*Species, cuts, grades, provenance, cooking*

| # | Type | Description | Status |
|---|------|-------------|--------|
| 6 | Reference | **Brand Guide** — master product reference (42 brands) | ✅ Stages 1–3 complete, tested on iPhone |
| 7 | Quiz | Marbling grades, bloodlines, brand stories, BMS scoring | ⬜ To build |
| 8 | Reference | Primal map, portion cuts, MSA grading, cooking methods | ⬜ To build |
| 9 | Reference | Lamb, pork, chicken, duck, quail — key cuts, use cases, seasonality | ⬜ To build |
| 10 | Quiz | Photo-based: name the cut, match to cooking method, pick the right spec | ⬜ To build |
| 11 | Tool | GP calculator — input cost price + portion weight, outputs GP% and sell price | ⬜ To build |

### Module 3 — Territory & Customer Knowledge
*SEQ + Northern Rivers, venue types, local context*

| # | Type | Description | Status |
|---|------|-------------|--------|
| 12 | Reference | SEQ zones, Northern Rivers towns, key venue clusters by region | ⬜ To build |
| 13 | Reference | Pub, club, restaurant, cafe — buying behaviour, pain points, decision makers | ⬜ To build |
| 14 | Quiz | Read a scenario, identify the venue type and correct sales approach | ⬜ To build |

### Module 4 — Live Practice
*Roleplay, scenario practice, manager-led coaching*

| # | Type | Description | Status |
|---|------|-------------|--------|
| 15 | Simulator | Rep chats with a simulated customer — AI plays the buyer, coaches after | ⬜ To build |
| 16 | Reference | Manager scorecard for ride-alongs and call reviews — SPIN, objections, close | ⬜ To build |
| 17 | Reference | One skill focus per week, team challenge, debrief prompt for manager | ⬜ To build |

### Training Hub
| # | Type | Description | Status |
|---|------|-------------|--------|
| 18 | Hub | Module cards, progress tracker, links to all tools and quizzes | ⬜ To build — last thing built, connects everything |

---

## Brand Guide — Build Status

| Stage | Description | Status |
|-------|-------------|--------|
| Stage 1 | Navigation shell — screens, transitions, breadcrumb, species/category/brand grids | ✅ Complete |
| Stage 2 | Design language — leather home screen, category colour systems, tier card hierarchy, topbar tint, animations | ✅ Complete |
| Stage 3 | Brand detail bottom sheet — 42 brands fully populated, accordion system, swipe-to-dismiss | ✅ Complete, tested on iPhone |
| Stage 4 | Photos and logos — swap banner gradient placeholders for real brand photos | ⬜ To build |
| Stage 5 | Final polish — any refinements after photos in, prep for team rollout | ⬜ To build |

**Current working file:** `moco-stage3.html`
**Live URL:** `https://peaceful-yeot-f4484f.netlify.app`
**GitHub repo:** `https://github.com/chrisoes12-commits/Meat`

---

## File Structure

| File | Status | Notes |
|------|--------|-------|
| `moco-stage3.html` | Current build | Stages 1–3 complete. This is the file to work from. |
| `moco-brand-guide-updated.html` | Content source | All 42 brands, full content. Do not edit. |
| `moco-stage2.html` | Archived | Superseded by stage3 |
| `moco-stage1.html` | Archived | Navigation shell only |
| `moco-design-system.md` | Reference | Full design token documentation |
| `CLAUDE.md` | This file | Master handoff — update after every session |

---

## BRANDS Data Object — Actual Field Names (as built in moco-stage3.html)

This is critical. The field names below are what actually exists in the JS. Do not use alternative names.

```javascript
BRANDS['Brand Name'] = {
  producer: "Producer Name · Location",   // producer and location string
  catId:    'wagyu',                       // category ID — see list below
  tier:     'Super Premium',              // tier label — see list below
  quick:    "One-line brand summary",     // the always-visible summary line
  specs:    ['Spec 1', 'Spec 2'],         // array of spec pill strings
  provenance: "Full provenance text",     // null for brands with no story
  venues:   [{name:'Fine Dining', strong:true}, {name:'Pub', strong:false}],
  sellingPoints: ['Point 1', 'Point 2'],  // array of selling point strings
  conversation: "Conversation starter text"  // single string, no outer quotes needed
}
```

**Valid catId values:** `'wagyu'`, `'grain'`, `'grass'`, `'moco-beef'`, `'all-lamb'`, `'all-pork'`, `'moco-chicken'`

**Valid tier values:** `'Super Premium'`, `'Premium'`, `'Mid-Range'`, `'Entry Level'`, `'Featured'`

**provenance: null** — used for Entry Level and some Mid-Range brands with no provenance story. When null, the Provenance accordion is not rendered.

---

## Design System — Non-Negotiable Decisions

### Typography
- **Display / Brand names:** Playfair Display — 400, 600, 700, 400 italic
- **Body / UI:** DM Sans — 300, 400, 500, 600
- Google Fonts with `preconnect` hints for faster mobile loading

### Base Colour Tokens
```
--bg:          #0F0E0B
--bg-card:     #1A1814
--bg-raised:   #222018
--gold:        #C4973A
--gold-dim:    rgba(196,151,58,0.32)
--gold-pale:   rgba(196,151,58,0.08)
--text-1:      #F0EAE0
--text-2:      #A09078
--text-3:      #564A3C
--border:      rgba(196,151,58,0.10)
--border-hi:   rgba(196,151,58,0.28)
```

### Category Colour Systems
Each category has a full theme object. This is the locked CAT_THEMES object as implemented:

```javascript
const CAT_THEMES = {
  'wagyu':        {tint:'rgba(80,15,5,0.28)',  glow:'rgba(139,42,18,0.22)',  spBgA:'#1A0A06',spBgB:'#1A1210',spBorder:'rgba(196,151,58,0.28)',prBg:'#18100C',prBorder:'rgba(139,42,18,0.25)',cardGlow:'rgba(100,20,5,0.12)',  sheetBg:'#100806',sheetBorder:'rgba(139,42,18,0.25)',  bannerBg:'linear-gradient(140deg,#2A0A04 0%,#14080A 100%)',bannerText:'rgba(196,151,58,0.20)'},
  'grain':        {tint:'rgba(80,55,5,0.25)',  glow:'rgba(139,96,24,0.20)',  spBgA:'#1A1006',spBgB:'#1A1610',spBorder:'rgba(196,151,58,0.26)',prBg:'#181408',prBorder:'rgba(139,96,24,0.22)',cardGlow:'rgba(100,70,5,0.10)',   sheetBg:'#100E06',sheetBorder:'rgba(139,96,24,0.22)',   bannerBg:'linear-gradient(140deg,#241A04 0%,#12100A 100%)',bannerText:'rgba(196,151,58,0.18)'},
  'grass':        {tint:'rgba(10,40,10,0.28)', glow:'rgba(42,92,34,0.22)',   spBgA:'#091408',spBgB:'#101A10',spBorder:'rgba(42,92,34,0.35)',  prBg:'#0E1A0C',prBorder:'rgba(42,92,34,0.28)', cardGlow:'rgba(10,60,10,0.10)',  sheetBg:'#080E08',sheetBorder:'rgba(42,92,34,0.30)',    bannerBg:'linear-gradient(140deg,#0A2008 0%,#081008 100%)',bannerText:'rgba(42,92,34,0.50)'},
  'moco-beef':    {tint:'rgba(5,10,40,0.32)',  glow:'rgba(26,58,139,0.22)',  spBgA:'#080C1A',spBgB:'#101420',spBorder:'rgba(100,130,200,0.28)',prBg:'#0C1020',prBorder:'rgba(100,130,200,0.20)',cardGlow:'rgba(5,10,80,0.12)', sheetBg:'#080A14',sheetBorder:'rgba(100,130,200,0.22)', bannerBg:'linear-gradient(140deg,#0A1030 0%,#080C18 100%)',bannerText:'rgba(100,130,200,0.35)'},
  'all-lamb':     {tint:'rgba(60,20,5,0.25)',  glow:'rgba(122,58,24,0.20)',  spBgA:'#1A0C06',spBgB:'#1A1410',spBorder:'rgba(180,120,80,0.28)',prBg:'#18100A',prBorder:'rgba(122,58,24,0.25)',cardGlow:'rgba(80,30,5,0.10)',   sheetBg:'#100A06',sheetBorder:'rgba(122,58,24,0.25)',   bannerBg:'linear-gradient(140deg,#201008 0%,#10080A 100%)',bannerText:'rgba(180,120,80,0.25)'},
  'all-pork':     {tint:'rgba(50,5,40,0.25)',  glow:'rgba(106,34,88,0.18)',  spBgA:'#180610',spBgB:'#1A0E18',spBorder:'rgba(180,100,160,0.26)',prBg:'#160812',prBorder:'rgba(106,34,88,0.22)',cardGlow:'rgba(60,5,50,0.10)',  sheetBg:'#0E0610',sheetBorder:'rgba(106,34,88,0.25)',   bannerBg:'linear-gradient(140deg,#1E0618 0%,#0E0610 100%)',bannerText:'rgba(180,100,160,0.25)'},
  'moco-chicken': {tint:'rgba(5,30,8,0.30)',   glow:'rgba(26,58,28,0.22)',   spBgA:'#061208',spBgB:'#0E1A10',spBorder:'rgba(43,107,53,0.35)', prBg:'#0C1A0E',prBorder:'rgba(43,107,53,0.28)',cardGlow:'rgba(5,50,10,0.12)', sheetBg:'#060E08',sheetBorder:'rgba(43,107,53,0.28)',   bannerBg:'linear-gradient(140deg,#082010 0%,#061008 100%)',bannerText:'rgba(43,107,53,0.50)'},
};
```

### Tier System
| Tier | Class | Colour |
|------|-------|--------|
| Super Premium | `.sp` | Gold `#C4973A` |
| Premium | `.pr` | Warm `#B09070` |
| Mid-Range | `.mr` | `var(--text-2)` |
| Entry Level | `.en` | `var(--text-3)` |
| Featured (Moco) | `.fe` | Blue `#8899CC` |

### Texture System
- **Home screen hero:** CSS leather texture — layered radial gradients + SVG feTurbulence grain. Home screen ONLY.
- **Super Premium brand cards:** Faint SVG grain overlay on `.brand-card.sp::after` only.
- **Section heroes:** Radial glow using `--cat-glow` variable set dynamically by JS.
- **Sheet banner:** SVG grain texture overlay at `opacity:0.05`, mix-blend-mode:overlay.

### Navigation Pattern
- Multi-layer: Home → Species → (Category) → Brands → Sheet
- Tappable breadcrumb below topbar, above section hero
- Back button in topbar — checks if sheet is open first, closes sheet before navigating back
- Breadcrumb jumpback — closes sheet before screen transition
- Transitions: 320ms, `cubic-bezier(0.4,0,0.2,1)`, same duration both directions
- `will-change:transform` + `-webkit-backface-visibility:hidden` for Safari
- `requestAnimationFrame` wrapping back animations prevents Safari mid-animation dropout
- `navLocked` boolean prevents race conditions on rapid taps

### Brand Card Hierarchy
- **Super Premium:** Full-width on mobile (grid-column span 2), 160px+ height, category gradient, grain overlay, larger brand name (17px)
- **Premium:** Standard size, subtle category gradient
- **Mid-Range / Entry Level:** Standard size, flat `--bg-card`

### Brand Card Photo Placeholders (Stage 3)
- Replaced static "Photo" text with category banner gradient background + faint brand name
- Uses `theme.bannerBg` as background, `theme.bannerText` as name colour
- Stage 4: swap gradient for `background-image: url(photo)` — no structural change needed

### Bottom Sheet (Stage 3)
- 90% screen height, `border-radius: 20px 20px 0 0`
- Background: `theme.sheetBg` | Top border: `theme.sheetBorder`
- Overlay: `rgba(8,7,5,0.75)` + `backdrop-filter: blur(4px)`
- Drag handle: `36px × 4px`, `rgba(196,151,58,0.22)`
- Swipe-down threshold: 80px — snap back if not reached
- Accordion uses `max-height: 2000px` (not scrollHeight) — safe for default-open state
- Key Selling Points accordion: `class="acc-block open"` baked into HTML — opens without JS timing risk

### Moco Brands
- Always visually distinct — deep blue tones, push priority labelling
- Acacia Valley Chicken: forest green `#1A3A1C` locked
- "Push priority" tag shown on category cards
- Featured tier (`.fe`), Blue `#8899CC`

---

## Brand Guide — All 42 Brands

**Beef — Wagyu (7):** Muse, Sir Harry, Senku, Jacks Creek Pure Bred, Icon XB, Black Opal, Jacks Creek Cross Bred

**Beef — Grain Fed (14):** The Bachelor, Pure Prime, Ebony Black Angus, Jacks Creek Black Angus, Riverina Black Angus, Yardstick, Kilcoy Black Diamond, Beef City Platinum, Royal, AMH White, AMH Black, Beef City Black, Kilcoy Blue Diamond

**Beef — Grass/Pasture Fed (7):** Southern Ranges, Vintage Beef, Roam, AMG, Right to Roam, AMH

**Beef — Moco Brands (3):** Pioneer's Cut, Jack's Best, Centenary Station

**Lamb (4):** Margra, Sovereign, Snowy Peaks, Ambassador

**Pork (8):** Borrowdale, Oria, Apple Tree, Barkers Creek, MOR, Schulz's, Sunpork, Spring Grove

**Chicken / Moco (1):** Acacia Valley

---

## Key Content Rules (Non-Negotiable)

- Moco house brands referred to as "Moco Brands" throughout — never "house brands" in UI
- Grain Fed range correctly described as "100-day to 150-day" — Ebony Black Angus is 150 days (longest)
- 500-day programs belong in Wagyu, NOT Grain Fed
- Barkers Creek is produced by SunPork (not Spring Grove)
- Snowy Peaks is a distinct Spring Grove lamb program
- Sovereign does NOT carry a "Gold" suffix
- Right to Roam is in Grass/Pasture Fed
- Beef total: 29 carton brands + 3 Moco house brands = 32

---

## Parked — Do Not Build Yet

- Cowhide watermark on Beef species card — revisit Stage 4+
- Home screen personalisation (Today's focus / territory prompt) — future platform phase
- Moco brand positioning line on home screen — future phase

---

## Key Principles

- **Moco Brands are push priority** — always visually distinct and prominent throughout all tools
- **Design system is reusable** — every decision made in the brand guide carries into every future tool
- **Mobile first** — the primary use case is a rep on their phone in a car park before a call
- **Content before design** — always lock content before building the visual layer
- **Build in stages** — validate each stage before proceeding to the next
- **Plan in Claude.ai, build in Claude Code** — decisions are locked in conversation before any code is written
