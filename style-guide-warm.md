# Design System: Matt Portfolio (Warm Edition)

## 1. Project Meta & Philosophy
*   **Target Audience:** Recruiters, engineering leads, and academic peers.
*   **Tone:** Professional, factual, grounded. "Show, don't tell."
*   **Core Identity:** Multidisciplinary (Molecular Biosciences + Mechanical Engineering + Software Development).
*   **Domain:** `mawimmer.dev`

## 2. Global Styling & Tailwind Configuration
The portfolio uses a custom warm dark theme built on top of Tailwind CSS.

### Custom Colors (Tailwind Config)
*   **Backgrounds & Surfaces (Stone/Warm-Gray tint):**
    *   `dark-900` (`#1c1917`): Main body background, primary header background (Tailwind `stone-900`).
    *   `dark-800` (`#292524`): Secondary surfaces, project cards, skill cards (Tailwind `stone-800`).
    *   `dark-700` (`#44403c`): Borders, subtle dividers, inactive states (Tailwind `stone-700`).
*   **Primary Accent (Orange/Amber):**
    *   `accent-400` (`#fb923c`): Bright highlight for text, hover states, icons (Tailwind `orange-400`).
    *   `accent-500` (`#f97316`): Deep highlight, primary buttons (Tailwind `orange-500`).
*   **Project-Specific Accents:**
    *   *Smart Lighting:* `amber-400` (Amber)
    *   *Espresso Machine:* `rose-400` / `rose-500` (Rose/Red)
    *   *Modpack/Server:* `yellow-400` / `yellow-500` (Yellow)

### Typography
*   **Primary Font:** `Inter` (Google Fonts), sans-serif.
*   **Monospace Font:** `JetBrains Mono` or `Fira Code` (Google Fonts) for code snippets, tags, and technical UI elements.
*   **Weights:** Light (300), Regular (400), Semibold (600), Bold (700).
*   **Text Colors:**
    *   Headings: `text-white` / `text-stone-100`
    *   Body text: `text-stone-300` or `text-stone-400`
    *   Code snippets: `text-stone-300` (handled by Prism.js)

## 3. Core Components

### Hero Section & Background Lighting
*   **Glow Effect:** Absolute positioned radial gradients (`bg-orange-500/10` and `bg-rose-500/10`) with `blur-3xl` to create a warm, dynamic ambient light behind the main text.
*   **Texture:** A faint dot-matrix grid overlay to imply engineering/CAD drafting paper before the user scrolls.

### Section Headers
*   **Base Styling:** `text-3xl md:text-4xl font-bold text-white mb-4 relative z-10`
*   **Ambient Glow:** A restrained, highly blurred ellipse (`absolute w-32 h-16 bg-accent-500/10 blur-2xl -z-10`) pinned behind the text to subtly lift it from the background without overwhelming the hero lighting.

### Project Cards
*   **Base Styling:** `bg-dark-900 border border-dark-700 rounded-2xl p-6`
*   **Hover Effect:** `hover:-translate-y-1 hover:shadow-[0_20px_40px_-15px_rgba(...)] transition-all duration-500`
*   **Tags:** Small rounded pill-shapes (`text-xs font-mono font-medium text-[accent-color]`)

### Technical Proof Slide-Over Drawer
*   **Trigger Button:** `w-full py-3 px-4 rounded-xl bg-dark-800 border border-dark-700 hover:bg-dark-700 transition-all`
*   **Behavior:** Replaces the inline accordion. Clicking "View Details" opens a sleek panel that slides in from the right side of the screen (`fixed inset-y-0 right-0 w-full max-w-md bg-dark-900 border-l border-dark-700 z-50`), preserving the project grid layout.

### Experience Timeline
*   **Structure:** Replaces flat cards with a vertical timeline layout. A continuous left-aligned border (`border-l-2 border-dark-700`) connects the experience nodes, visualizing the multidisciplinary journey from mechanical engineering to life sciences.

### Interest Cards
*   **Visuals:** Desaturated, highly darkened background images (e.g., a climbing wall texture, a dark keyboard setup) replacing flat colors.
*   **Styling:** Uses a `bg-blend-multiply` or overlay gradient to ensure text readability while adding a human, personalized touch.

### Visual Proof Lightbox (Modal)
*   **Thumbnails:** `h-24 bg-dark-800 border-dark-700 rounded-lg overflow-hidden cursor-pointer relative group/thumb`.
*   **Modal Overlay:** `fixed inset-0 bg-dark-900/90 backdrop-blur-md z-[100]`.
*   **Behavior:** Shows CAD drawing, PCB layer, or CNC photograph with a technical caption.