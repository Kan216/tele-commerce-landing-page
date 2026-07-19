# Tele-Commerce Site Structure & Navigation Architecture

This document defines the layout hierarchy, tab navigation logic, and dependency-free implementation details.

---

## 1. Page Layout Structure

The page will maintain a single-page structure (`index.html`) with smooth in-page tab navigation.

```
+-----------------------------------------------------------------------+
|  HEADER / STICKY NAV BAR (Wordmark + 4 Nav Tabs + Quick CTA)           |
+-----------------------------------------------------------------------+
|  TAB 1: #overview (Hero + How It Works + Before/After + Trust CTA)     |
+-----------------------------------------------------------------------+
|  TAB 2: #features (6 Feature Cards Grid + Business Categories)        |
+-----------------------------------------------------------------------+
|  TAB 3: #pricing (3 Receipt-Ticket Pricing Cards + Feature Matrix)    |
+-----------------------------------------------------------------------+
|  TAB 4: #faq-contact (Accordion FAQ + Direct Access Banner)           |
+-----------------------------------------------------------------------+
|  FOOTER (Copyright + Target Audience Note)                            |
+-----------------------------------------------------------------------+
```

---

## 2. Navigation Architecture

### A. Sticky Top Bar (`<nav class="sticky-nav">`)
- **Positioning**: Fixed / Sticky at `top: 0`, `z-index: 100`, with `background: var(--paper)` and `border-bottom: 1px solid var(--rule)`.
- **Left Element**: Logo Wordmark (`.wordmark`) with gold dot.
- **Center Element**: Horizontal Tab Switcher (`.nav-tabs`) containing 4 buttons/links:
  1. `Overview` (`#overview`)
  2. `Features` (`#features`)
  3. `Pricing` (`#pricing`)
  4. `FAQ & Contact` (`#faq-contact`)
- **Right Element**: Compact CTA Button (`Tele-Commerce ဖွင့်ပါ` -> `https://www.tele-commerce.work.gd/`).

### B. Mobile Navigation Handling
- Mobile-first CSS rules ensure the navigation tabs scroll horizontally (`overflow-x: auto; white-space: nowrap; -webkit-overflow-scrolling: touch;`) on smaller screens without hamburger menus, keeping all 4 tabs instantly accessible with 1 tap.

### C. In-Page Tab Switching & Scroll Sync
- **Dependency-Free Vanilla JS**:
  - Uses native smooth scrolling (`scroll-behavior: smooth`).
  - Implements `IntersectionObserver` on `#overview`, `#features`, `#pricing`, and `#faq-contact` sections to automatically highlight the active tab in the navbar as the user scrolls.
  - Clicking any tab button smoothly scrolls to the section and updates the `aria-selected` and active CSS state (`.nav-tab.active`).

---

## 3. Technical & SEO Compliance

- **Meta Pixel**: Kept intact in `<head>` (ID: `3382658948573524`) and triggered on all CTA clicks.
- **Accessibility**:
  - Semantic HTML5 elements (`<nav>`, `<header>`, `<main>`, `<section>`, `<footer>`).
  - Proper heading hierarchy (`<h1>` for Hero, `<h2>` for section headings, `<h3>` for cards).
  - All interactive links and buttons have descriptive text and visible `:focus-visible` outlines (`3px solid var(--blue)`).
- **Reduced Motion**: Respects `prefers-reduced-motion: reduce` for ticket unspooling and stamp animations.
- **No Build Step**: 100% pure HTML5, CSS3, and Vanilla JavaScript.
