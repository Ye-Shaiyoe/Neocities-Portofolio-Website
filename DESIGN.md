# DESIGN.md — Neocities Gothic Cyber-Horror Personal Page

## Project Overview
A **Serial Experiments Lain**-inspired gothic cyber-horror personal website hosted on Neocities. The design emphasizes abandoned internet aesthetics, retro-cyberpunk vibes, and psychological horror themes. Built as a "lost girl in the wired" narrative persona.

### Key Concept
- **Theme**: "LAYER:07 — lost in the wired" (inspired by Serial Experiments Lain)
- **Aesthetic**: Gothic + Cyber-horror + 90s Retro Web
- **Target Feel**: Mysterious, isolated, abandoned, haunting yet beautiful
- **Interactivity**: Custom cursors, glitch effects, floating particles, CRT scanlines

---

## Technical Stack

### Frontend
- **HTML5** — Semantic markup
- **Tailwind CSS** — Responsive utility-first CSS framework (via CDN)
- **Vanilla JavaScript** — DOM manipulation, animations, interactions
- **Custom CSS** — Extensive animations, filters, and visual effects

### Fonts (Google Fonts)
- **Cinzel** — Serif, elegant, used for titles and headers
- **EB Garamond / Cormorant Garamond** — Serif, content body text
- **VT323** — Monospace, retro terminal/pixel aesthetic
- **Press Start 2P** — Pixel art font (available, for potential future use)

### Assets
- Custom cursors (`.cur` files) in `cursor/` folder
- Background images in `img/background/`
- Music files in `music/`
- Sound effects in `sound/`
- GIFs in `gif/`
- Project files in `project/`
- Skill/portfolio items in `skill/`

---

## Color Palette

### Primary Colors
```
Gothic Black:      #020001 (main background)
Deep Background:   #0a0406
Text Primary:      #e8d8c8 (pale beige/cream)
Accent Red:        #c86464 (blood-red accent)
```

### Secondary Colors (Gradients & Effects)
- **Grays**: #111111, #222222, #1a1a1a, #1c1c1c (borders, shadows)
- **Glitch Colors**: Bright red/cyan for digital distortion effects
- **Particles**: rgba(180, 30, 30, 0.35) (red floating particles)
- **Cryptic Text**: rgba(200, 80, 80, 0.6) (muted red monospace text)

### Design Principle
- **High contrast** but **desaturated** — filters reduce saturation to ~40-60%
- **Darkness emphasized** — brightness filters at 50-90% to maintain gothic tone
- **Accent colors** sparingly placed (red/cyan glitches) for dramatic effect

---

## Layout Structure

### Page Container
- **Fixed dimensions**: 1100px × 600px
- **Centered** on viewport
- **Box-shadow**: Deep shadows for depth and separation from background

### Main Components

#### 1. **Sidebar (Left, 200px)**
- **Avatar Frame**: Square bordered frame with scanline overlay
- **Navigation Buttons**: Monospace VT323 font, boxy 90s-style buttons
- **Interactive States**:
  - `.nav-btn:hover` — Glitch animation with red/cyan text-shadow
  - `.nav-btn:active` — Pressed appearance
  - `.nav-btn.active` — Highlighted current page
- **Bottom Elements**:
  - Visit counter (retro style, flickering animation)
  - Guestbook button with icon
  - Blinking star decorations
  - Character illustration (chibi, positioned overlapping at bottom-right)

#### 2. **Main Content Area (Right, flex)**
- **Header Bar** (24px min-height):
  - Title in VT323 monospace
  - Control dots (decorative, simulating old window chrome)
- **Banner** (110px):
  - Large background image
  - Overlay gradients for readability
  - Title and subtitle text positioned absolutely
- **Content Body** (flex layout):
  - **Welcome Panel**: Intro text with italic title
  - **Diary Panel**: Scrollable list of entries (red scrollbar)
  - Right sidebar (future expansion: links, status, etc.)

---

## Animation & Effects

### Background Layers (Fixed & Layered)
1. **Wallpaper** (z-index: 0) — Lain wallpaper with desaturation filters
2. **Vignette** (z-index: 1) — Radial gradients for dark edges, red tint corners
3. **Texture** (z-index: 2) — Subtle repeating patterns (lace-like)
4. **Scanlines** (z-index: 3) — CRT horizontal lines (1px every 2px)
5. **Noise** (z-index: 4) — Static overlay with slight jitter animation
6. **Glitch** (z-index: 5) — Occasional red/dark horizontal glitches (8s cycle)
7. **Particles** (z-index: 6) — Floating red particles rising from bottom
8. **Cryptic Text** (z-index: 6) — Mysterious monospace text drifting

### Key Animations
- **containerFadeIn** (1.5s) — Smooth fade and scale-up on load
- **particleFloat** — Particles rise from bottom with drift
- **vhsGlitch** (8s) — Occasional full-screen glitch lines
- **navGlitch** (0.4s) — Hover on nav buttons triggers color-shift glitch
- **counterFlicker** (4s) — Visitor counter flickers like old display
- **noiseShift** (0.15s) — Static noise shifts position
- **crypticDrift** (12s) — Floating text drifts vertically
- **starBlink** (2s) — Decorative stars blink with staggered delays

### Cursor Effects
- **Default cursor**: `cursor/cursor-normal.cur`
- **Interactive elements** (a, button, input): `cursor/cursor-select.cur`

---

## Component Styling Details

### Buttons & Interactive Elements
- **3D bevel effect**: Inset borders with lighter top/left, darker bottom/right
- **Transition**: 0.2s ease on hover
- **Monospace font**: VT323 for retro aesthetic
- **Text transform**: Lowercase for consistency

### Text Styling
- **Headers**: Cinzel serif, italic, with text-shadow for depth
- **Body**: EB Garamond serif, 13px, line-height 1.7
- **Monospace**: VT323 for technical/status elements
- **Accent**: Reduced saturation globally, selective red highlights

### Borders & Frames
- **Avatar frame**: Multiple nested borders (3px solid, 2px outline, 1px inset)
- **Panels**: Subtle 1px borders with slight glow on hover
- **Container**: 2px black border with heavy box-shadow

---

## File Structure

```
Neocities-web/
├── index.html              # Main page (the 1100×600 layout)
├── DESIGN.md               # This file
├── cursor/
│   ├── cursor-normal.cur   # Default cursor
│   └── cursor-select.cur   # Interactive element cursor
├── img/
│   └── background/
│       └── Lain-wallpaper.jpg  # Main background image
├── gif/                    # GIF assets (for future use)
├── music/                  # Background music files
├── sound/                  # Sound effects
├── skill/                  # Portfolio/skill section (structure TBD)
├── project/                # Project showcases (structure TBD)
├── webmaster/              # Admin/webmaster section
│   ├── index.html
│   ├── script.js
│   └── style.css
└── [avatar images]         # Avatar image files (not listed)
```

---

## Sections & Content Areas

### Currently Implemented
1. **Sidebar**
   - Avatar with scanline effect
   - Navigation menu (buttons: home, diary, projects, skills, links, etc.)
   - Visitor counter
   - Guestbook button
   - Character decoration

2. **Main Content**
   - Banner with title and subtitle
   - Welcome panel (intro text)
   - Diary panel (scrollable list of entries)

### Future Expansion Areas
- **Projects section** (`project/` folder)
- **Skills/portfolio** (`skill/` folder)
- **Webmaster panel** (`webmaster/` folder) — for administration
- **Right sidebar** — Currently empty in content-body; could add:
  - Links section
  - Status/online indicators
  - Recent updates
  - External links to social media

---

## Design Principles & Patterns

### 1. **Layered Depth**
- Multiple fixed background layers create visual depth
- Use of shadows, outlines, and inset borders
- Z-index hierarchy carefully managed (0-50 range)

### 2. **Gothic Aesthetic**
- Dark color palette with selective red accents
- Serif fonts (Cinzel, Garamond) for elegance
- Monospace fonts (VT323) for technical/mysterious feel
- Text-shadow and glow effects for atmospheric quality

### 3. **Retro-Cyberpunk**
- CRT scanlines and glitch effects
- 90s-style window chrome (header dots, beveled buttons)
- Floating particles and noise
- Static/analog feel despite digital medium

### 4. **Interactivity**
- Custom cursors for immersion
- Hover states with glitch animation
- Flickering effects on text/counters
- Smooth transitions (0.2-0.5s)

### 5. **Performance**
- Animations use CSS (GPU-accelerated)
- Filters applied to background layers (not main content)
- Pointer-events: none on decorative layers
- Optimized box-shadows for visual impact without overhead

---

## Responsive Considerations

### Current State
- **Fixed container** (1100×600) centered on screen
- **No mobile optimization** — This is by design (retro web aesthetic)
- Could add: viewport detection and mobile fallback if needed

### Potential Mobile Approach (Future)
- Detect screen size, adjust container width
- Stack elements vertically
- Adjust font sizes for readability
- Maintain gothic aesthetic at smaller scales

---

## Content Management

### Diary Entries
- Located in `.diary-panel`
- Each entry: `.diary-entry` with date, title, content
- Border separators between entries
- Scrollable with custom red scrollbar

### Navigation
- Defined in `.sidebar-nav` as `.nav-btn` elements
- Links to different pages/sections
- Active state managed via `.nav-btn.active` class

### Welcome Message
- `.welcome-panel` — Static intro text
- Can be updated without code changes (edit HTML content)

---

## Browser Compatibility

### Tested/Optimized For
- Modern browsers supporting:
  - CSS Grid & Flexbox
  - CSS animations & transforms
  - CSS filters (brightness, saturate, contrast)
  - Custom cursors (.cur files)
  - Google Fonts

### Known Limitations
- `.cur` cursor files may not work on all systems
- Scanlines and filters have visual artifacts on very old browsers
- JavaScript features assume ES6+ support

---

## Future Development

### Short-term Enhancements
1. **Populate project and skill sections** with content
2. **Add more diary entries** with timestamps
3. **Create webmaster panel** functionality (if needed)
4. **Add music/sound effects** integration
5. **Optimize images** for loading speed

### Medium-term Features
1. **Interactive elements**:
   - Clickable links that navigate to new pages
   - Modal dialogs for guestbook, forms, etc.
   - Animation on tab/section switch
2. **Additional sections**:
   - Photo gallery (with gothic styling)
   - Music player (retro design)
   - Comments/social section
3. **Mobile responsiveness** (optional, maintains desktop design as primary)

### Long-term Vision
1. **Backend integration** (if migrating from static Neocities)
   - Database for diary entries
   - Guestbook submission storage
   - Visitor tracking
2. **User authentication** (if webmaster section expands)
3. **Dynamic content loading** (JavaScript-based single-page app approach)

---

## Accessibility Notes

### Current Limitations
- Fixed color contrast (meets WCAG AA in most areas)
- No alt-text for decorative images (intentional aesthetic choice)
- Interactive elements labeled but not extensively marked up
- Custom cursors may confuse some users

### Improvements to Consider
- Add ARIA labels to interactive sections
- Provide high-contrast alternative theme toggle
- Ensure keyboard navigation works
- Add skip-to-content link for screen readers

---

## Customization Guide

### To Change Colors
1. Update CSS custom properties or hex values in `<style>` tag
2. Main locations:
   - Background: `#020001`, `#0a0406`
   - Text: `#e8d8c8`
   - Accent: `#c86464` (search for all instances)

### To Add New Sections
1. Create new `.nav-btn` in sidebar
2. Duplicate page or create new `.main-panel` content area
3. Use same styling patterns for consistency

### To Modify Animations
1. Find `@keyframes` rules in CSS
2. Adjust duration (e.g., `8s` in `vhsGlitch`)
3. Change transform or opacity values
4. Test in browser for performance

### To Replace Images
1. Swap files in `img/` or `gif/` folders
2. Update src paths in HTML if filenames change
3. Maintain same aspect ratios for layout integrity

---

## Notes for Next Developer

- **Preserve the aesthetic**: Gothic + cyberpunk themes are core to design
- **Animations are intentional**: Glitches, scanlines, and noise create atmosphere
- **Color restraint**: Desaturated palette with red accents — avoid bright colors
- **Typography matters**: Serif vs. monospace choices affect readability and mood
- **Layer management**: Z-index values are carefully chosen; test before adjusting
- **Performance**: Animations use CSS, not JavaScript, for smooth 60fps
- **Interactivity**: Hover states and transitions enhance engagement without breaking immersion

---

## External References

- **Inspiration**: Serial Experiments Lain (anime series)
- **Hosting**: Neocities (static site hosting for retro web aesthetic)
- **Fonts**: Google Fonts API (CDN-loaded)
- **Framework**: Tailwind CSS (via CDN, minimal custom CSS override)

---

**Last Updated**: May 31, 2026  
**Status**: Active Development  
**Version**: 1.0 (Initial Structure)
