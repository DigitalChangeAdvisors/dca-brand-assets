# DCA FRONTEND DESIGN SYSTEM & AGENT SPECIFICATION
**System Version:** 1.3 (Production & AI-Agent Optimized)  
**Brand:** Digital Change Advisors (DCA)  
**Design Paradigm:** MBB Elite Consulting Authority + Apple-Style Minimalist Engineering  
**Target Environment:** Claude Code · Visual Studio Code · Next.js / React / Tailwind CSS  

---

## 1. AGENT OPERATIONAL DIRECTIVES (SYSTEM PROMPT)

> **ROLE:** You are the Lead Frontend Architect and Principal UI Designer for Digital Change Advisors (DCA).  
> **MISSION:** Build responsive, enterprise-grade user interfaces, interactive reports, and client portals that convey absolute executive authority, analytical rigor, and pristine aesthetic refinement.  
> 
> **STRICT EXECUTION PROTOCOLS:**
> 1. **Zero Hallucination:** You are strictly forbidden from inventing arbitrary colors, default framework borders, or generic animations. Apply ONLY the Design Tokens specified herein.
> 2. **Structural Breathing (White Space):** Treat negative space as an active architectural element. Use generous paddings (`120px` to `160px` between primary sections on desktop).
> 3. **Typography Discipline:** Never render headers in generic sans-serif fonts. All major titles, key metrics, and archetype names MUST use `Marcellus`. Body text, table cells, and interface labels MUST use `Montserrat`.
> 4. **Component Elevation:** Never use hard black shadows. Elevation is achieved via ultra-diffused, ambient carbon shadows (`rgba(30, 42, 56, 0.05)`) paired with soft platinum borders.
> 5. **Asset Integrity:** Always query `/assets/logos/` directly. Never break the canonical favicon rule (`dca-favicon-circle.png`).

---

## 2. DESIGN TOKENS: COLOR MATRIX

### 2.1 Primary Brand Palette (The 70 / 20 / 10 Rule)
* **Surface & Canvas (`70%`):** `#ffffff` (Pure White)
  * CSS Token: `var(--dca-white)` | Tailwind: `bg-white` / `text-white`
* **Brand Anchor (`20%`):** `#2e8b76` (Corporate Teal / Verde Agua DCA)
  * RGB: `46, 139, 118` | HSL: `166°, 50%, 36%`
  * CSS Token: `var(--dca-teal)` | Tailwind: `bg-[#2e8b76]` / `text-[#2e8b76]` / `border-[#2e8b76]`
* **Strategic Accent (`10%`):** `#a48111` (Executive Gold / Oro Estratégico)
  * RGB: `164, 129, 17` | HSL: `46°, 81%, 35%`
  * CSS Token: `var(--dca-gold)` | Tailwind: `text-[#a48111]` / `border-[#a48111]`
  * *Constraint:* Never apply transparency to gold tokens. Must remain 100% solid.

### 2.2 Secondary & Interface Architecture
* **Typography & Dark Surface:** `#1e2a38` (DCA Carbon / Carbón Corporativo)
  * RGB: `30, 42, 56`
  * CSS Token: `var(--dca-carbon)` | Tailwind: `text-[#1e2a38]` / `bg-[#1e2a38]`
* **Structural Border & Icon Neutral:** `#dfe3e1` (Tech Platinum / Platino Tecnológico)
  * RGB: `223, 227, 225`
  * CSS Token: `var(--dca-platinum)` | Tailwind: `border-[#dfe3e1]` / `bg-[#dfe3e1]`
* **Critical Warning & Severity:** `#c2593f` (Urgency Terracotta / Cobre de Alerta)
  * RGB: `194, 89, 63`
  * CSS Token: `var(--dca-terracotta)` | Tailwind: `text-[#c2593f]` / `bg-[#c2593f]`

---

## 3. DESIGN TOKENS: TYPOGRAPHIC HIERARCHY

Base calculation: `1rem = 16px`. Both font families are imported via Google Fonts.

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Marcellus&family=Montserrat:ital,wght@0,300;0,400;0,500;0,600;0,700;1,400&display=swap" rel="stylesheet">
```

### 3.1 Display Scales (Font: `Marcellus`, Serif)
* **Monumental Display (Gauges / Hero Stats):**  
  Size: `4rem` to `5.5rem` (64px–88px) | Line-height: `1.05` | Tracking: `-0.03em`
* **H1 (Page Title / Hero Header):**  
  Size: `2.5rem` to `3rem` (40px–48px) | Line-height: `1.2` | Tracking: `-0.02em`
* **H2 (Section Header):**  
  Size: `2rem` (32px) | Line-height: `1.25` | Tracking: `-0.01em`
* **H3 (Module / Card Header):**  
  Size: `1.5rem` (24px) | Line-height: `1.3` | Tracking: `0`

### 3.2 Interface & Body Scales (Font: `Montserrat`, Sans-serif)
* **Lead In / Deck (Introductory Copy):**  
  Size: `1.125rem` (18px) | Weight: `300 (Light)` | Line-height: `1.6` | Color: `#1e2a38` (85% opacity)
* **Standard Body:**  
  Size: `1rem` (16px) | Weight: `400 (Regular)` | Line-height: `1.6` | Color: `#1e2a38` (80% opacity)
* **Sub-labels & Data Headers:**  
  Size: `0.875rem` (14px) | Weight: `600 (SemiBold)` | Tracking: `0.05em` | Text-transform: `uppercase`
* **Footnotes & Meta Tags:**  
  Size: `0.75rem` (12px) | Weight: `400 (Regular)` | Line-height: `1.4` | Color: `#1e2a38` (50% opacity)

---

## 4. DESIGN TOKENS: SPATIAL SYSTEM (8-POINT GRID)

Layout math follows an uncompromising 8px baseline:

* `space-1` (8px): Micro-spacing between icon and accompanying text.
* `space-2` (16px): Internal padding for buttons, pills, badges, and inline elements.
* `space-3` (24px): Standard margin between paragraphs and form fields.
* `space-4` (32px): Internal card padding (`p-6 sm:p-8`).
* `space-6` (48px): Gap between related grid cards and sub-modules.
* `space-8` (64px): Vertical space separating content blocks within the same topic.
* `space-macro` (120px–160px): Desktop vertical padding (`py-28 lg:py-36`) separating primary page sections.

---

## 5. UI/UX RULES: SURFACES, RADIUS & ELEVATION

### 5.1 Border Radii
* **Pills & Badges:** `rounded-[6px]` or `rounded-full` (for small numerical chips only).
* **Buttons & Inputs:** `rounded-[8px]` (`rounded-lg`).
* **Content Cards, Modals & Data Panels:** `rounded-[12px]` (`rounded-xl`).
* *Prohibition:* Zero-radius edges (excessive rigidity) and large bubble-like shapes are prohibited.

### 5.2 Ambient Elevation Formula
* **Base Card Elevation:**
  ```css
  box-shadow: 0 4px 24px rgba(30, 42, 56, 0.05), 0 1px 2px rgba(30, 42, 56, 0.03);
  border: 1px solid rgba(223, 227, 225, 0.6);
  ```
* **Interactive Hover Elevation:**
  ```css
  transform: translateY(-2px);
  box-shadow: 0 12px 32px rgba(30, 42, 56, 0.08), 0 2px 6px rgba(30, 42, 56, 0.04);
  transition: all 0.25s cubic-bezier(0.16, 1, 0.3, 1);
  ```

---

## 6. ASSET REPOSITORY MAPPING

Assets reside in `public/assets/logos/` (or web-accessible equivalent):

```text
/assets/logos/dca-logo-full-positive.png  -> Light navigation bars & white document headers
/assets/logos/dca-logo-full-negative.png  -> Dark navigation bars & Carbon sections
/assets/logos/dca-logo-full-white.png     -> Solid Teal containers & photo backgrounds
/assets/logos/dca-symbol-positive.png     -> Compact UI avatars & table indicators
/assets/logos/dca-symbol-negative.png     -> Dark-mode avatars
/assets/logos/dca-favicon-circle.png      -> CANONICAL WEB FAVICON (Mandatory in <head>)
```

---

## 7. CORE COMPONENT BLUEPRINTS (MBB STANDARD)

### 7.1 Data Tables (Executive Accounting Format)
* **Structure:** Zero vertical grid lines. Clean horizontal separators using `1px solid #dfe3e1`.
* **Header Row:** `Montserrat SemiBold` (13px), uppercase, color `#1e2a38`, letter-spacing `0.05em`.
* **Alignment:** Qualitative text aligned to the left; all financial metrics and percentages strictly aligned to the right.
* **Row Spacing:** Generous vertical padding (`16px` to `20px` per row).

### 7.2 Data Visualizations & Gauges
* **Data-Ink Ratio:** No background wallpapers, no drop-shadows on charts, and no heavy axis grids.
* **Color Hierarchy:**
  * Benchmark / Context: `#dfe3e1` (Platinum) or `#1e2a38` (20% opacity).
  * DCA Client Diagnostic: `#2e8b76` (Corporate Teal).
  * Outlier / Critical Friction: `#a48111` (Gold) or `#c2593f` (Terracotta).
* **Score Displays:** Render the primary diagnostic score in `Marcellus` at `4.5rem`, accompanied by an uppercase `Montserrat` sub-label.

---

## 8. CALIBRATED "GOLD STANDARD" TEMPLATE

Every modular insight card created by the agent must conform to this calibrated structure:

```html
<article class="group relative bg-[#ffffff] w-full max-w-md rounded-[12px] p-6 sm:p-8 border border-[#dfe3e1]/60 transition-all duration-300 ease-out hover:-translate-y-[2px] cursor-pointer" style="box-shadow: 0 4px 24px rgba(30, 42, 56, 0.05);">
  
  <!-- Header: Category Icon & Severity Badge -->
  <div class="flex items-start justify-between mb-6">
    <div class="w-12 h-12 flex items-center justify-center bg-[#dfe3e1] rounded-[8px] text-[#2e8b76] transition-colors duration-200 group-hover:bg-[#2e8b76] group-hover:text-white">
      <svg class="w-6 h-6" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round">
        <circle cx="12" cy="12" r="10"></circle>
        <path d="M12 6v6l4 2"></path>
      </svg>
    </div>
    <span class="inline-block px-2.5 py-1 rounded-[6px] text-[11px] font-semibold tracking-wider font-montserrat bg-[#f3f5f4] text-[#2e8b76] border border-[#2e8b76]/20 uppercase">
      Severidad Alta
    </span>
  </div>

  <!-- Meta Kicker -->
  <span class="font-montserrat font-semibold text-xs tracking-widest uppercase text-[#2e8b76] mb-2 block">
    Arquetipo 01 · Diagnóstico IUG
  </span>

  <!-- Display Title (Marcellus) -->
  <h3 class="font-marcellus text-2xl text-[#1e2a38] leading-[1.3] mb-4">
    El Barco sin Timón
  </h3>

  <!-- Descriptive Body (Montserrat) -->
  <p class="font-montserrat font-normal text-base text-[#1e2a38]/85 leading-[1.6] mb-8">
    Embarcación a la deriva con timón ausente. La organización tiene múltiples pilotos de IA desplegados, pero carece de un marco de gobierno unificado y de una dirección estratégica que traduzca el uso técnico en retorno económico verificable.
  </p>

  <!-- Hairline Divider -->
  <div class="w-full h-px bg-[#dfe3e1] mb-6"></div>

  <!-- Interactive Call-To-Action -->
  <div class="flex items-center justify-between">
    <button class="inline-flex items-center text-[#a48111] font-montserrat font-semibold text-sm group-hover:text-[#2e8b76] transition-colors duration-200 focus:outline-none">
      <span>Ver impacto en el P&L</span>
      <svg class="ml-2 w-4 h-4 transition-transform duration-200 group-hover:translate-x-1" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <line x1="5" y1="12" x2="19" y2="12"></line>
        <polyline points="12 5 19 12 12 19"></polyline>
      </svg>
    </button>
    <span class="text-xs font-montserrat text-[#1e2a38]/40 font-medium">120 días</span>
  </div>
</article>
```

---

## 9. TAILWIND CONFIGURATION SNIPPET

For direct integration in `tailwind.config.js`:

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ['./src/**/*.{js,ts,jsx,tsx,mdx}'],
  theme: {
    extend: {
      colors: {
        dca: {
          teal: '#2e8b76',
          gold: '#a48111',
          carbon: '#1e2a38',
          platinum: '#dfe3e1',
          terracotta: '#c2593f',
        },
      },
      fontFamily: {
        marcellus: ['Marcellus', 'serif'],
        montserrat: ['Montserrat', 'sans-serif'],
      },
      boxShadow: {
        'dca-card': '0 4px 24px rgba(30, 42, 56, 0.05), 0 1px 2px rgba(30, 42, 56, 0.03)',
        'dca-hover': '0 12px 32px rgba(30, 42, 56, 0.08), 0 2px 6px rgba(30, 42, 56, 0.04)',
      },
      borderRadius: {
        'dca-card': '12px',
        'dca-btn': '8px',
      },
    },
  },
  plugins: [],
}
```