# AGENTS.md

## Build/Lint/Test Commands

This is a static HTML project with no build system, package.json, or framework dependencies.

- **Preview**: Open `stitch/code.html` directly in a web browser
- **No build command required** - The project uses Tailwind CSS via CDN
- **No lint command configured**
- **No tests configured**

## Code Style Guidelines

### Project Overview
This is a static HTML website implementing a "Kinetic Brutalism" design system inspired by Slam Dunk manga. The design focuses on high-impact motion, hard-edged containers (0px radius), and intentional asymmetry.

### Technology Stack
- HTML5
- Tailwind CSS (via CDN with plugins: forms, container-queries)
- Google Fonts: Space Grotesk (headlines), Inter (body), Lexend (labels), Material Symbols Outlined (icons)

### Design Philosophy

**Kinetic Brutalism:**
- Move beyond standard web grids
- Embrace aggressive, hard-edged containers (0px radius)
- Use intentional asymmetry
- Implement "The Overlap" where typography and imagery bleed across section boundaries

**Color Strategy:**
- Primary (Shohoku Red): `#ffb3ae` (Surface Tint) / `#ce1126` (Container)
- Surface: `#131313` (main canvas, provides "Ink" aesthetic)
- NO 1px solid borders for sectioning - use background color shifts between `surface_container_low` (`#1c1b1b`) and `surface_container_high` (`#2a2a2a`)
- For separation, use negative space or hard background color shifts
- "Glass & Gradient": `surface` at 80% opacity with `20px` backdrop-blur for floating elements
- Halftone dot patterns using `outline_variant` (#5c3f3d) at 15% opacity

**Typography:**
- Space Grotesk: Display/headlines with tight letter-spacing (-0.04em), often ALL CAPS
- Inter: Clean body copy, `body-lg` is the workhorse
- Lexend: Technical labels for stats, timestamps, categories
- Always lead with size contrast - display-lg directly against body-sm metadata

**Elevation & Depth:**
- Use Material 3 surface tiers:
  - Level 0: `surface_container_lowest` (#0e0e0e) - deep background
  - Level 1: `surface` (#131313) - main content area
  - Level 2: `surface_container_highest` (#353534) - interactive elements/cards
- "Tonal Elevation" through background shifts, not drop shadows
- If shadows needed: 40px blur, 0% spread, 8% opacity tinted with `primary_container`
- For definition: `outline_variant` (#5c3f3d) at 15% opacity maximum
- Use 2px "Speed Lines" (primary token) to lead eye toward CTAs

**Component Patterns:**

**Buttons:**
- Primary: Solid `primary_container` (#ce1126) background, 0px border-radius
- Hover: Shift to `primary` (#ffb3ae) with instant transition (150ms or 0ms)
- Secondary: Ghost style with `outline` color text, 1px `outline` border at 30% opacity

**Cards & Lists:**
- NO dividers
- Use `2.75rem` (spacing-8) vertical padding to separate list items
- On hover: Shift from `surface_container_low` to `primary_container` instantly

**Inputs:**
- Bottom-border only (2px, `outline`)
- Background: `surface_container_lowest`
- Focus: Border transforms to `primary`

### Do's and Don'ts

**Do:**
- Use 0px corners everywhere - sharpness is the brand
- Use asymmetrical margins (e.g., left `spacing-12`, right `spacing-6`)
- Overlap elements - let images break container boundaries
- Use "Step" eases or fast durations (150ms) for transitions
- Left-align content for strong editorial axis

**Don't:**
- Use rounded corners - `0px` is the only allowed value
- Use soft transitions - maintain high energy
- Use gray - use `secondary` or `tertiary` tiers for neutrals
- Center-align everything - deliberate off-center balance preferred

### HTML Structure
- Use semantic HTML5 elements: `<nav>`, `<main>`, `<section>`, `<footer>`
- Tailwind config is embedded in `<script id="tailwind-config">` in the head
- Custom styles defined in `<style>` block for halftone overlays and kinetic effects
- Images use `data-alt` attributes for accessibility
