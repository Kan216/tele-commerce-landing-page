# Tele-Commerce Design System Specification

Extracted from existing `index.html` to guarantee 100% visual harmony across all expanded sections.

---

## 1. Color Palette Tokens

The design uses a warm, tactile, paper-and-ink aesthetic with deep nautical blue accents and gold/sage highlights.

| Token Name | Hex Value | Usage / Role |
| :--- | :--- | :--- |
| `--paper` | `#EDEAE0` | Primary page background (warm tactile paper tone) |
| `--paper-alt` | `#E4E0D2` | Secondary background / striped chat container background |
| `--ink` | `#1F2A24` | Primary body typography & dark headings (deep charcoal green) |
| `--ink-soft` | `#5B6459` | Subtitles, secondary text, metadata labels, line annotations |
| `--blue` | `#2C5F7C` | Interactive hover states & focus outlines (`:focus-visible`) |
| `--blue-deep` | `#1E4356` | Primary CTA buttons, section eyebrows, key accent elements |
| `--gold` | `#C98A2E` | Logo dot accent, ledger numbers (`01, 02, 03`), highlight underline |
| `--sage` | `#4C7A5E` | Stamp badges (`CONFIRMED`, `POPULAR`), success states, clean indicators |
| `--rule` | `#D2CBB4` | Borders, subtle dividers, dashed ticket rules |
| `--white` | `#FBFAF6` | Card background, receipt tickets, active inputs (crisp off-white) |
| `--radius` | `2px` | Subtle corner radius for buttons and ticket components |

---

## 2. Typography System

Fonts are loaded from Google Fonts: Space Grotesk, Inter, JetBrains Mono, and Noto Sans Myanmar.

| Category | Font Family | Weights Used | Application Scope |
| :--- | :--- | :--- | :--- |
| **Display / Headings** | `'Space Grotesk', 'Noto Sans Myanmar', sans-serif` | 500, 700 | Wordmark, `<h1>`, `<h2>`, `<h3>`, section titles, trust quotes |
| **Body Text** | `'Inter', 'Noto Sans Myanmar', sans-serif` | 400, 500, 600 | General paragraphs, card descriptions, subtext, FAQ body |
| **Monospace / Data** | `'JetBrains Mono', monospace` | 400, 500, 700 | Section labels (eyebrows), order numbers (`#TC-xxxx`), receipt line items, pricing figures, micro copy |
| **Burmese Language** | `'Noto Sans Myanmar'` | Fallback | Integrated seamlessly across display & body font stacks |

---

## 3. Core Visual Motifs & Components

### A. Receipt / Order Ticket Motif (`.receipt`)
- **Structure**: Off-white card (`--white`), drop shadow (`0 18px 40px -18px rgba(30,67,86,0.35)`), monospace text, and dashed border dividers (`1px dashed var(--rule)`).
- **Perforated Bottom**: Radial gradient background cut (`radial-gradient(circle at 9px 0, transparent 9px, var(--paper) 9.5px)`).
- **Stamp Badge (`.stamp`)**: Rotated badge (-9deg) with 2px solid border in `--sage` or `--gold` (e.g. `CONFIRMED`, `POPULAR`, `BEST VALUE`).
- **Reuse Application**: All Pricing Tier cards will strictly use this receipt-ticket visual language.

### B. Ledger List Motif (`.ledger`)
- Bordered rectangular container (`1px solid var(--rule)`) with numbered step columns (`01`, `02`, `03`) in `--gold` monospace font, separated by vertical dashed borders.

### C. Direct Comparison Motif (`.compare-grid`)
- Contrasting two cards: Messy Chat (striped paper background `--paper-alt` + irregular chat bubbles) vs. Clean Tele-Commerce Ledger (off-white card `--white` + organized monospace line items).

### D. CTA Buttons (`.cta-btn`)
- Deep blue (`--blue-deep`), white text (`--white`), embedded SVG icon, subtle hover lift (`translateY(-1px)`).
- Always triggers Meta Pixel `Lead` event when clicked before navigating to `https://www.tele-commerce.work.gd/`.
