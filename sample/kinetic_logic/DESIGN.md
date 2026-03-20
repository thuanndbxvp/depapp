```markdown
# Design System: The Kinetic Scholar

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Kinetic."** 

We are moving away from the static, boxy layouts of traditional "Learning Management Systems" and toward a fluid, high-energy editorial experience. This system prioritizes momentum, using intentional asymmetry and layered depth to guide the eye. Instead of a rigid grid, think of the UI as a series of overlapping planes that feel alive. By utilizing high-contrast typography scales and "breathing" white space, we create a premium environment that feels both academically authoritative and youthfully energetic.

## 2. Colors: Tonal Depth over Borders
Our palette is anchored in deep cosmic indigos (`#111124`), electrified by a core violet (`#7D4EF2`) and sparked by kinetic orange (`#F97316`).

### The "No-Line" Rule
**Borders are prohibited for sectioning.** To define boundaries, designers must rely exclusively on background color shifts. A `surface-container-low` section sitting on a `surface` background creates a sophisticated, modern transition that 1px lines cannot replicate.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of semi-transparent layers. 
*   **Base:** `surface` (#111124)
*   **Secondary Planes:** `surface-container-low` (#1a1a2d)
*   **Interactive Cards:** `surface-container` (#1e1e31)
*   **Floating Elements:** `surface-container-highest` (#333348)

### The "Glass & Gradient" Rule
To inject "soul" into the interface, use Glassmorphism for floating navigation and overlays. Apply `surface` colors at 60-80% opacity with a `backdrop-filter: blur(20px)`. 
*   **Signature Gradient:** For primary CTAs and Hero accents, transition from `primary-container` (#7D4EF2) to `primary` (#cfbdff) at a 135-degree angle. This creates a luminous, "lit from within" effect.

## 3. Typography: Editorial Authority
We utilize **Inter** to bridge the gap between technical precision and friendly accessibility.

*   **Display (lg/md/sm):** Used for "Big Moments"—hero headers and impact statements. Use `tight` letter-spacing (-0.02em) to create a sophisticated, "magazine" feel.
*   **Headline (lg/md/sm):** Reserved for section titles. These should feel bold and intentional.
*   **Title (lg/md/sm):** For card headers and navigational anchors.
*   **Body (lg/md):** Your workhorse. Ensure `line-height` is set to 1.6 for maximum readability during long study sessions.
*   **Label (md/sm):** Used for micro-copy and metadata. Always in `uppercase` with `+0.05em` letter-spacing to distinguish from body text.

## 4. Elevation & Depth
In this design system, depth is a feeling, not a shadow effect.

### The Layering Principle
Achieve hierarchy by "stacking" the `surface-container` tiers. Place a `surface-container-lowest` card on a `surface-container-low` section to create a soft, natural "lift." This mimics the way light interacts with matte materials.

### Ambient Shadows
If an element must float (e.g., a Modal or a FAB), use an **Ambient Shadow**:
*   **Color:** `on-surface` (#e2e0fb) at 6% opacity.
*   **Blur:** 40px to 60px.
*   **Spread:** -5px.
This creates a glow rather than a dark "drop" shadow, keeping the interface feeling "vibrant" and "youthful."

### The "Ghost Border" Fallback
If contrast testing fails and a border is required for accessibility, use a **Ghost Border**: The `outline-variant` token at 15% opacity. Never use 100% opaque strokes.

## 5. Components

### Buttons
*   **Primary:** Uses the **Signature Gradient**. `xl` (1.5rem) rounded corners. On hover, the background-position shifts to reveal more of the `primary` light tone.
*   **Secondary:** `surface-container-high` background with `on-surface` text. No border.
*   **Tertiary:** Ghost style. Transparent background, `primary` text. Use for low-emphasis actions.

### Cards & Lists
*   **Rule:** Forbid the use of divider lines. 
*   **Style:** Use `spacing scale 6` (1.5rem) as a vertical gutter between list items. For cards, use `surface-container-low` and transition to `surface-container-highest` on hover to signal interactivity.

### Input Fields
*   **Base:** `surface-container-lowest` background. 
*   **Focus State:** A 2px "Ghost Border" using `primary` at 40% opacity. 
*   **Error State:** Background shifts to a very subtle tint of `error_container` (#93000a) at 10% opacity.

### Interactive Chips
*   **Selection:** Use `primary_container` (#7d4ef2) for the active state and `surface_variant` for the inactive state. 
*   **Shape:** Always `full` (9999px) roundedness for a friendly, approachable feel.

### Progress Orbs (App Specific)
Since this is an educational platform, use "Progress Orbs" instead of flat bars. These are circular rings using the `tertiary` (#ffb690) color with a subtle outer glow to represent kinetic energy and completion.

## 6. Do's and Don'ts

### Do:
*   **Embrace White Space:** Use the `20` and `24` spacing tokens to let content breathe.
*   **Layer Surfaces:** Use `surface-container` tiers to create hierarchy.
*   **Mobile-First Layouts:** Stack elements vertically on mobile but use intentional horizontal offsets on desktop to break the "grid."

### Don't:
*   **No Black Shadows:** Never use `#000000` for shadows. Use tinted shadows to maintain color vibrancy.
*   **No Dividers:** Avoid horizontal rules (`<hr>`). Use background color shifts and padding instead.
*   **No Sharp Corners:** Never use a radius lower than `md` (0.75rem) unless it's for a tiny micro-element.
*   **No Clutter:** If a screen feels busy, remove a background color shift rather than adding a border.