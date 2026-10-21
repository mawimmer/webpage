# Design System: Matt Portfolio

## 1. Project Meta & Philosophy
*   **Target Audience:** Recruiters, engineering leads, and academic peers.
*   **Tone:** Professional, factual, grounded. "Show, don't tell."
*   **Core Identity:** Multidisciplinary (Molecular Biosciences + Mechanical Engineering + Software Development).
*   **Domain:** `mawimmer.dev`

## 2. Global Styling & Tailwind Configuration
The portfolio uses a custom dark theme built on top of Tailwind CSS.

### Custom Colors (Tailwind Config)
*   **Backgrounds & Surfaces (Slate/Blue-Gray tint):**
    *   `dark-900` (`#0f172a`): Main body background, primary header background.
    *   `dark-800` (`#1e293b`): Secondary surfaces, project cards, skill cards.
    *   `dark-700` (`#334155`): Borders, subtle dividers, inactive states.
*   **Primary Accent (Blue/Cyan):**
    *   `accent-400` (`#38bdf8`): Bright highlight for text, hover states, icons.
    *   `accent-500` (`#0ea5e9`): Deep highlight, primary buttons.
*   **Project-Specific Accents:**
    *   *Smart Lighting:* `accent-400` (Blue)
    *   *Espresso Machine:* `emerald-400` / `emerald-500` (Green)
    *   *Modpack/Server:* `purple-400` / `purple-500` (Purple)

### Typography
*   **Primary Font:** `Inter` (Google Fonts), sans-serif.
*   **Weights:** Light (300), Regular (400), Semibold (600), Bold (700).
*   **Text Colors:**
    *   Headings: `text-white`
    *   Body text: `text-slate-300` or `text-slate-400`
    *   Code snippets: `text-slate-300` (handled by Prism.js)

## 3. Core Components

### Project Cards
*   **Base Styling:** `bg-dark-900 border border-dark-700 rounded-2xl p-6`
*   **Hover Effect:** `hover:-translate-y-1 hover:shadow-[0_20px_40px_-15px_rgba(...)] transition-all duration-500`
*   **Tags:** Small rounded pill-shapes (`text-xs font-medium text-[accent-color]`)

### Technical Proof Accordion
*   **Trigger Button:** `w-full py-3 px-4 rounded-xl bg-dark-800 border border-dark-700 hover:bg-dark-700 transition-all`
*   **Behavior:** When clicked, it expands smoothly. The active card spans the full width of the grid (`md:col-span-3`), while sibling cards are hidden via a combination of opacity, scale, and display toggling.

### Code Snippets (Prism.js)
*   **Theme:** Okaidia (Dark Theme).
*   **Structure:** `<pre class="bg-black/50 p-3 rounded-lg border border-dark-700">` containing a `<code class="language-[cpp/javascript]">`.
*   **Features:** Top bar with a title, optional GitHub link / Private Repo badge, and a functional "Copy" button.

### Visual Proof Lightbox (Modal)
*   **Thumbnails:** `h-24 bg-dark-800 border-dark-700 rounded-lg overflow-hidden cursor-pointer relative group/thumb`. Uses an overlay gradient and text on hover.
*   **Modal Overlay:** `fixed inset-0 bg-dark-900/90 backdrop-blur-md z-[100]`.
*   **Behavior:** Clicking a thumbnail opens the full-screen modal showing the CAD drawing, PCB layer, or CNC photograph with a technical caption.

## 4. Third-Party Libraries
*   **Tailwind CSS:** Styling framework (loaded via CDN for prototyping).
*   **FontAwesome (v6.4.0):** Used for all icons (`fas fa-cogs`, `fab fa-github`, etc.).
*   **Prism.js (v1.29.0):** Used for syntax highlighting (C, C++, JavaScript).

## 5. Asset Guidelines
*   **Format:** WebP or optimized PNG/JPG.
*   **CAD/Blueprint Screenshots:** Must be clean, showing tool UI elements (like PTC Creo or EasyEDA menus) only if it adds authentic engineering context.
*   **Sizing:** Lightbox images should be high-resolution but optimized for web viewing (max 1920x1080).