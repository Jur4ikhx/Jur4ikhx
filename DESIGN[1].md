# Design System Document: The Living Archive

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Curator"**

This design system is not a mere repository of facts; it is a high-end editorial experience designed to evoke the prestige of a world-class institution. We are moving away from the "template" look of standard educational portals. Instead, we embrace the "Living Archive"—a visual language that balances the weight of history with the clarity of modern curation.

To achieve this, we break the rigid grid. We utilize intentional asymmetry, allowing large serif typography to bleed into negative space. We layer elements using tonal depth rather than structural lines, creating a UI that feels like stacked sheets of fine vellum and heavy cardstock. The result is an interface that feels authored, not just assembled.

---

## 2. Colors & Surface Logic
Our palette is rooted in tradition: deep academic Navy, archival Cream, and illuminated Gold.

### The "No-Line" Rule
**Strict Mandate:** Designers are prohibited from using 1px solid borders to define sections. Layout boundaries must be established solely through background color shifts. Use `surface-container-low` (#f6f3ed) against a `surface` (#fcf9f3) background to denote a change in content. This creates a seamless, "museum-wall" transition rather than a digital box.

### Surface Hierarchy & Nesting
Treat the UI as a physical desk. 
- **Base Layer:** `surface` (#fcf9f3) is your primary canvas.
- **Content Blocks:** Use `surface-container-low` (#f6f3ed) for secondary sections.
- **Interactive Layers:** Use `surface-container-highest` (#e5e2dc) for elements that require immediate focus, such as search bars or active modals.

### Glass & Gradient Rule
To prevent the "flat" look of 2010s minimalism, utilize **Glassmorphism** for floating navigation and temporary overlays. Use the `surface` color at 85% opacity with a `backdrop-blur` of 20px. 
- **Signature Gradients:** For primary CTAs and Hero sections, apply a subtle linear gradient from `primary` (#000e24) to `primary_container` (#00234b). This mimics the depth of a premium fountain pen ink.

---

## 3. Typography
The typography is our primary voice. It must feel authoritative yet accessible.

- **Display & Headlines (Noto Serif):** Used for storytelling and exhibit titles. These should be set with generous leading. `display-lg` (3.5rem) is your "Curator’s Voice"—use it sparingly for high-impact statements.
- **Body & Labels (Inter):** The "Scholar’s Note." This provides the utilitarian contrast to the serif. It must remain highly legible, using `body-md` (0.875rem) for the bulk of historical descriptions.
- **Hierarchy as Identity:** Always pair a `headline-sm` serif with a `label-md` all-caps Inter subtitle in `secondary` (Gold) to create a "Placard" effect common in physical museums.

---

## 4. Elevation & Depth
In this system, depth is felt, not seen.

### The Layering Principle
Avoid the "drop shadow" tool by default. Instead, stack `surface-container` tiers. A `surface-container-lowest` (#ffffff) card placed on a `surface-container-low` (#f6f3ed) background provides a crisp, "paper-on-table" lift that is far more sophisticated than a shadow.

### Ambient Shadows
When an element must float (e.g., a high-level modal), use **Ambient Shadows**. 
- **Value:** `0px 12px 32px`
- **Color:** Use `on_surface` (#1c1c18) at 4-6% opacity. 
- **Effect:** The shadow should feel like a soft glow of light blocked by a physical object, never a dark smudge.

### The Ghost Border Fallback
If a border is required for accessibility (e.g., input fields), use a **Ghost Border**. Use the `outline_variant` token at 15% opacity. High-contrast, 100% opaque borders are strictly forbidden as they break the editorial flow.

---

## 5. Components

### Buttons
- **Primary:** `primary` (#000e24) fill with `on_primary` (#ffffff) text. Use `DEFAULT` rounding (0.25rem) for a sharp, formal look.
- **Secondary:** `outline` ghost button with a `secondary` (Gold) text color. Use this for "Explore More" or "View Collection."
- **States:** On hover, primary buttons should shift to `primary_container` (#00234b) with a subtle `2.5` (0.85rem) vertical lift via ambient shadow.

### Cards & Lists
- **Rule:** Forbid divider lines.
- **Implementation:** Separate list items using the Spacing Scale (specifically `4` (1.4rem) or `6` (2rem)). Use a `surface-variant` hover state to highlight list items. 
- **Exhibit Cards:** Use `surface-container-lowest` with a "Ghost Border." Image headers should have a 1% inner glow to feel like framed photography.

### Input Fields
- **Styling:** Use a `surface-container-low` fill with a bottom-only `outline` (2px) in `primary`. This mimics the look of a traditional ledger or archival form.
- **Error States:** Use `error` (#ba1a1a) only for the label and a subtle `error_container` tint for the background.

### Custom Component: The "Curator’s Sidebar"
A persistent or slide-in element using `surface_dim` (#dcdad4) and a 40px backdrop blur. It should house metadata, citations, or related artifacts, using `label-sm` for all text to maintain a "footnote" aesthetic.

---

## 6. Do's and Don'ts

### Do
- **Embrace White Space:** Use the `16` (5.5rem) and `20` (7rem) spacing tokens to let content breathe. High-end design is defined by what you leave out.
- **Use Intentional Asymmetry:** Align text to a traditional grid, but let hero images or gold accents break the margin.
- **Mix Weights:** Pair `display-md` (Regular) with `label-md` (Bold) to create a modern typographic rhythm.

### Don't
- **No 1px Lines:** Do not use lines to separate content. Use color blocks or space.
- **No Pure Black:** Never use #000000. Use `primary` (#000e24) for depth and `on_surface` (#1c1c18) for text.
- **No Heavy Rounding:** Avoid `xl` or `full` rounding for primary components. We are an institution of history, not a social media app. Stick to `DEFAULT` (0.25rem) or `sm` (0.125rem).