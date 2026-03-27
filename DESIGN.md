# Design System Strategy: Luminous Curator

## 1. Overview & Creative North Star

The "Luminous Curator" aesthetic is a high-end editorial approach to utility. This design system rejects the "standard SaaS" look in favor of a sophisticated, high-contrast digital environment. It functions as an intentional gallery: clear, authoritative, and brilliantly lit.

**Creative North Star: The Illuminating Anchor.**
While the industry trends toward soft blurs and muddy grays, this system uses a vibrant, solid primary anchor—solid yellow (#facc15)—set against a backdrop of deep slate and light architectural grays. By utilizing intentional asymmetry and a "borderless" philosophy, we create a layout that feels curated rather than generated. We break the grid through varying card heights and layered surfaces, ensuring the interface feels like a bespoke editorial piece.

---

## 2. Colors: High Contrast & Tonal Depth

This system relies on the interplay between the "Glow" (Primary Yellow) and the "Anchor" (Deep Slate). Purple is strictly forbidden; all depth is achieved through blue-toned grays and charcoals.

### The "No-Line" Rule

Traditional 1px borders are prohibited for sectioning. Structural boundaries must be defined through **Surface Layering** (e.g., a `surface-container-lowest` card sitting on a `surface-container-low` background). This creates a cleaner, more premium look that mimics physical materials rather than digital boxes.

### Surface Hierarchy & Nesting

Treat the UI as a series of nested layers. Importance is dictated by lightness:

- **Base Layer:** `surface` (#f0f7ff) - Light Blue
- **Subtle Inset:** `surface-container-low` (#e6f0ff) - Deep Sky Blue
- **Main Component Layer:** `surface-container-lowest` (#ffffff)
- **Floating/Elevated:** `surface-bright` (#f0f7ff) with Glassmorphism.

### Signature Textures

While interactive elements remain solid and flat, page backgrounds and hero sections may use a subtle linear gradient (e.g., `surface` to `surface-container`) to provide "soul" and depth to the canvas.

---

## 3. Typography: The Editorial Scale

We utilize **Plus Jakarta Sans** for its modern, geometric clarity. The hierarchy is designed to feel like a high-end magazine.

- **Display (Large/Medium):** Reserved for hero moments. Use `clamp()` for fluid responsiveness and tight letter-spacing (-0.02em) to create an authoritative, "bold" presence.
- **Headlines:** The workhorse of the curator look. Use `headline-md` with `clamp()` for section titles to command attention without overwhelming the content.
- **Title & Body:** `title-md` provides a clear anchor for card headers, while `body-lg` (16px) with intentional line-height (1.6) ensures maximum readability.
- **Labels:** Small, all-caps or high-weight labels (`label-md`) are used for metadata, mimicking the fine print in an exhibition catalog.

---

## 4. Elevation & Depth: Tonal Layering

We move away from the "shadow-heavy" look of the 2010s. Depth is achieved through color shifts and "Ghost" properties.

- **The Layering Principle:** Place a `surface-container-lowest` (#ffffff) card on a `surface-container-low` (#f2f3ff) background. This creates a soft, natural "lift."
- **Ambient Shadows:** If an element must "float" (like a dropdown), use an extra-diffused shadow.
  - _Spec:_ `0px 12px 32px rgba(19, 27, 46, 0.06)` (Tinted with `on-surface`).
- **The Ghost Border:** If accessibility requires a border, use `outline-variant` at 15% opacity or a `1.5px` stroke with muted alpha. Never use a 100% opaque border.
- **Glassmorphism:** For floating navigation or tooltips, use `surface-container-lowest` at 80% opacity with a `20px` backdrop-blur. This integrates the component into the environment.
- **Spring Animations:** Interactive elements (like flashcards) use a spring-feel `cubic-bezier(0.34, 1.56, 0.64, 1)` for a premium, responsive touch.

---

## 5. Components: Flat, Solid, & Precise

All interactive elements must be solid. Gradients on buttons are forbidden to maintain the "Luminous" clarity.

- **Primary Button:**
  - **Color:** `primary-container` (#facc15).
  - **Text:** `on-primary-fixed` (#231b00) - High-contrast charcoal.
  - **Radius:** 8px.
  - **Style:** Flat. No inner shadows. No gradients.
- **Chips:**
  - Use `secondary-container` for neutral tags and `tertiary-container` for specific actions.
  - Avoid borders; use solid background fills with `0.5rem` (8px) radius.
- **Input Fields:**
  - Background: `surface-container-lowest`.
  - Border: `outline-variant` at 20% opacity.
  - On Focus: Border becomes `primary` (#735c00) at 100% opacity, 2px stroke.
- **Cards:**
  - Strictly **No Dividers**. Use `2.5rem` (40px) vertical whitespace to separate header from body, or a subtle background shift between the card header and content area.
- **Flashcards:**
  - Include an interactive hint ("Tap to Flip") to encourage discovery.
  - Implement 3D flip with `backface-visibility: hidden`.
- **Interactive Tabs:**
  - Use a solid "pill" indicator rather than an underline. The active tab should be `secondary-fixed` with `on-secondary-fixed` text.

---

## 6. Do's and Don'ts

### Do

- **DO** use the vibrant yellow (#facc15) sparingly but intentionally to guide the eye.
- **DO** use 8px (0.5rem) as your base radius for a modern, slightly softened look.
- **DO** embrace white space. If an element feels "stuck," double the spacing using the `spacing-10` (2.5rem) token.
- **DO** use high-contrast charcoal for all text on yellow backgrounds to pass WCAG AAA standards.

### Don't

- **DON'T** use purple or pink tones for surfaces. Stick to blue-tinted grays and light sky blues.
- **DON'T** use 1px solid dividers between list items. Use spacing or tonal shifts.
- **DON'T** apply gradients to buttons. The "Luminous Curator" aesthetic relies on the "pop" of solid, flat color.
- **DON'T** use harsh black shadows. Always tint your shadows with the deep slate of the design system.
