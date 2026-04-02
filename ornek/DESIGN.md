# Design System Strategy: The Digital Alchemist

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Alchemist."** 

We are moving away from the "utility tool" aesthetic and toward a "high-end laboratory" feel. This design system treats a user’s photo gallery not as a junk drawer, but as a digital archive that requires precision, light, and transparency to clean. We break the traditional SaaS "box-on-box" template by using **intentional asymmetry**, **overlapping glass layers**, and **light-driven depth**. 

Instead of rigid grids, we use breathing room and focal glows to guide the eye. The interface should feel like a specialized optical instrument—precise, expensive, and powerful.

---

### 2. Colors & Surface Logic
The palette is rooted in deep space navies, punctuated by high-energy gases (Electric Blue, Cyan, and Pink-Purple).

*   **Primary Hierarchy:** `primary` (#9bcbff) and `primary_container` (#4facfe) drive the core action.
*   **The "No-Line" Rule:** Standard 1px solid borders are strictly prohibited for sectioning. We define space through "Tonal Carving." A section is born when a `surface_container_low` area transitions into `surface_container_high`.
*   **Surface Hierarchy & Nesting:** 
    *   **Level 0 (Base):** `surface` (#0c1324) is the infinite void.
    *   **Level 1 (Sections):** `surface_container` (#191f31) defines major content groupings.
    *   **Level 2 (Interactive):** `surface_container_highest` (#2e3447) is used for cards that demand a tap.
*   **The "Glass & Gradient" Rule:** Use `surface_variant` at 40% opacity with a `20px` backdrop blur for floating modals. Apply a linear gradient from `primary_container` (#4facfe) to `secondary_container` (#00f1fd) on hero buttons to create a "liquid light" effect.
*   **Signature Textures:** Incorporate a subtle 2% noise overlay on the `background` to eliminate banding in dark gradients and add a "physical" film-grain quality.

---

### 3. Typography: Editorial Utility
We pair **Outfit** (Geometric/Technical) with **Urbanist** (Modern/Humanist) to balance precision with readability.

*   **Display & Headlines (Outfit):** Use `display-lg` through `headline-sm`. These must always be **Bold**. Set letter-spacing to `-0.02em` for headlines to create a tight, authoritative "Editorial" look.
*   **Body (Outfit):** Use `body-lg` and `body-md` in **Regular**. This provides a clean, technical legibility that feels like a modern iOS utility.
*   **Labels (Urbanist):** Use `label-md` and `label-sm`. Urbanist’s slightly wider tracking makes it perfect for metadata (file sizes, dates, categories). Always use `uppercase` for `label-sm` to denote technical specs.

---

### 4. Elevation & Depth
In this design system, light does not come from "above"—it comes from the "objects" themselves.

*   **The Layering Principle:** Avoid shadows on nested elements. Use the scale: a `surface_container_lowest` card sitting on a `surface_container` background creates an "etched" look. A `surface_container_high` card on a `surface` background creates a "lifted" look.
*   **Ambient Glows:** For "Floating" states (like the primary "Clean" button), use a shadow colored `primary_container` at 15% opacity with a `32px` blur. This isn't a shadow; it’s an atmospheric glow.
*   **The "Ghost Border" Fallback:** Where separation is vital for accessibility, use the `outline_variant` token at **15% opacity**. It should be felt, not seen.
*   **Glassmorphism:** Navigation bars and floating action headers must use `surface_container_low` at 60% opacity with a `16px` backdrop-blur.

---

### 5. Components

*   **Primary Action Button:** 
    *   **Style:** Gradient fill (`primary_container` to `secondary_container`). 
    *   **Radius:** `full` (pill shape). 
    *   **Interaction:** On press, scale to 96% and increase `surface_brightness`.
*   **Glass Cards (Cleanup Groups):** 
    *   **Background:** `surface_variant` at 30% opacity. 
    *   **Border:** `outline_variant` at 20% opacity. 
    *   **Effect:** 12px Backdrop Blur. No dividers between internal list items; use `8px` vertical spacing instead.
*   **Selection Chips:**
    *   **Unselected:** `surface_container_high` with `on_surface_variant` text.
    *   **Selected:** `tertiary_container` (#df84eb) with a `2px` glow of `tertiary`.
*   **Input Fields:**
    *   **Style:** Minimalist. No background box. Only a `surface_container_highest` bottom stroke (2px). Label (Urbanist) floats above in `primary` when active.
*   **The "Smart Feed" List:** 
    *   **Rule:** Forbid the use of divider lines. Separate "Similiar Photos" or "Large Files" using `surface_container_lowest` pods with `lg` (1rem) corner radius.

---

### 6. Do’s and Don’ts

**Do:**
*   **Do** use `tertiary` (Pink-Purple) sparingly for "Success" or "Magic" moments (e.g., "1.2GB Cleaned!").
*   **Do** use asymmetrical margins. For example, a headline might be indented `spacing-8`, while the body text below it is indented `spacing-10`.
*   **Do** use `spacing-px` (1px) for very thin, decorative "optical" lines that don't reach the edges of the screen.

**Don’t:**
*   **Don't** use pure black (#000000). Always use `surface_dim` (#0c1324) to maintain the "Navy Tech" depth.
*   **Don't** use standard iOS blue for links. Use `secondary_fixed` (#6ff6ff) for all interactive text.
*   **Don't** use heavy dropshadows. If a container needs to stand out, use a color shift or a `1px` ghost border.
*   **Don't** cram the UI. If you are unsure, add `spacing-6` of vertical white space.