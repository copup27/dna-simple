# CSS/JS DNA Strand Animation (Recreation)

This project is an HTML, CSS, and JavaScript recreation of an animated DNA strand effect, based visually on a code demonstration video attributed to "One Person Studio".

## Description

This single HTML file creates a 3D representation of a rotating DNA helix. Key features include:

*   A double helix structure built with simple HTML divs.
*   3D rotation effect using CSS `perspective` and `transform`.
*   Individual nodes (representing base pairs/components) styled as circles with borders.
*   Connecting "rungs" between the node pairs using CSS pseudo-elements.
*   Staggered animation delays applied to each strand using CSS `calc()` with `sin()` (or a JavaScript fallback for older browsers), creating a wave-like "jump" effect for the nodes.
*   Scaling animation applied to the connecting rungs synchronized with the node jumps.
*   Small orbiting dots within each node (using CSS `::after`).
*   Randomly assigned colors to the nodes from a predefined palette using JavaScript.

## Demo

The intended visual result is based on the animation shown being coded in the source video clip. Opening the `dna_animation.html` (or whatever you name the file) in a modern browser will display the animation.

*(Optional: You could add a screenshot or animated GIF here if you create one)*

## How it Works

1.  **HTML (`<div class="dna">`, etc.):** Provides the semantic structure. CSS variables (`--total`, `--index`) are set inline to pass data for calculations.
2.  **CSS (`<style>` block):** Handles the vast majority of the styling and animation.
    *   `perspective` and `transform-style: preserve-3d` create the 3D environment.
    *   CSS Custom Properties (variables like `--speed`, `--delay`, `--bg`, `--destination`) allow for dynamic control and calculations within CSS.
    *   `display: grid` arranges the strands vertically, while `display: flex` arranges the nodes horizontally within a strand.
    *   `::before` pseudo-element creates the rungs.
    *   `::after` pseudo-element creates the orbiting dots.
    *   `@keyframes` define the `rotate`, `jump`, `scale`, and `orbit` animations.
    *   `calc(sin(...))` is used to create the sophisticated, wave-like staggered delay for the `jump` and `scale` animations.
3.  **JavaScript (`<script>` block):**
    *   Provides a *fallback* mechanism to calculate and apply the animation delays (`--delay`) if the browser doesn't support the `sin()` function within CSS `calc()`.
    *   Assigns a random background color (`--bg`) to each `.strand_node` from a predefined `COLORS` array for visual variety.

## How to Use

1.  Save the complete code block into a single file named `dna_animation.html` (or any other `.html` name).
2.  Open this HTML file in a modern web browser that supports CSS Grid, Flexbox, Custom Properties, 3D Transforms, and Animations.

## Attribution and Disclaimer

***CREDIBILITY AND USAGE NOTE***

*   **Original Code Concept:** DNA Strand Animation
*   **Original Author/Demonstrator:** "One Person Studio" (based on video context)

This HTML file is a recreation based *solely* on the visual demonstration provided in the source video clip. It attempts to faithfully reproduce the HTML structure, CSS styling, and JavaScript logic shown being typed.

*   **Ownership:** No ownership of the original code or concept is claimed by the creator of this specific recreation. Full credit for the design and implementation shown in the video belongs to the original author ("One Person Studio").
*   **Disclaimer:** This code is provided "AS IS", without warranty of any kind, express or implied. **Use this code entirely at your own risk.** The creator of this recreation assumes no liability for any issues, damages, or consequences resulting from its use or modification. Verify browser compatibility and performance for your specific needs.
