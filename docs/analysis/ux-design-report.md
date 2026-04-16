## Section 1: Design System Foundation (Design Tokens)

### Color Tokens
- **Primary:** `--color-primary: #FF4500` (OrangeRed)
- **Secondary:** `--color-secondary: #1E90FF` (DodgerBlue)
- **Accent:** `--color-accent: #FFD700` (Gold)
- **Neutral:**
  - `--color-neutral-100: #FFFFFF`
  - `--color-neutral-200: #F5F5F5`
  - `--color-neutral-300: #E5E5E5`
  - `--color-neutral-400: #D4D4D4`
  - `--color-neutral-500: #A3A3A3`
  - `--color-neutral-600: #737373`
  - `--color-neutral-700: #525252`
  - `--color-neutral-800: #404040`
  - `--color-neutral-900: #262626`
- **Semantic:**
  - `--color-success: #22C55E` (Green)
  - `--color-warning: #FBBF24` (Amber)
  - `--color-error: #EF4444` (Red)

### Typography
- **Font Families:**
  - **Heading:** "Roboto Condensed", sans-serif
  - **Body:** "Roboto", sans-serif
- **Scale:**
  - `xs`: 0.75rem
  - `sm`: 0.875rem
  - `base`: 1rem
  - `lg`: 1.125rem
  - `xl`: 1.25rem
  - `2xl`: 1.5rem
  - `3xl`: 1.875rem
  - `4xl`: 2.25rem
- **Line Heights:**
  - `body`: 1.5
  - `heading`: 1.2
- **Font Weights:**
  - `normal`: 400
  - `bold`: 700
- **Letter Spacing:**
  - `normal`: 0
  - `wider`: 0.05em

### Spacing
- **Base Unit:** 4px
- **Scale:**
  - `space-1`: 4px
  - `space-2`: 8px
  - `space-4`: 16px
  - `space-8`: 32px
  - `space-12`: 48px
  - `space-16`: 64px

### Border Radius
- `none`: 0px
- `sm`: 2px
- `md`: 4px
- `lg`: 8px
- `full`: 9999px

### Shadows
- `sm`: 0 1px 2px 0 rgba(0, 0, 0, 0.05)
- `md`: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06)
- `lg`: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05)
- `xl`: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04)

### Breakpoints
- `sm`: 640px
- `md`: 768px
- `lg`: 1024px
- `xl`: 1280px
- `2xl`: 1536px

---

## Section 2: Component Specifications

### Header
- **Purpose:** Primary site navigation and branding.
- **Visual:** Sticky header with logo, navigation links, and a CTA button.
- **Dimensions:** `height: space-16`, `padding: 0 space-4`.
- **Tokens:**
  - `background-color: --color-neutral-100`
  - `box-shadow: --shadow-md`
- **States:**
  - `a:hover`: `color: --color-primary`
- **Responsive:** Hamburger menu on `md` and smaller.
- **Content:** Logo slot, Nav Items slot, CTA slot.
- **Tailwind:** `bg-white shadow-md sticky top-0 z-50 h-16 px-4`

### Hero
- **Purpose:** Immediately capture user attention and communicate value proposition.
- **Visual:** Full-bleed video background with a text overlay and a primary CTA.
- **Dimensions:** `min-height: 75vh`.
- **Tokens:**
  - `color: --color-neutral-100`
- **Content:** Headline, Sub-headline, CTA button.
- **Tailwind:** `relative min-h-[75vh] flex items-center justify-center text-white`

### CTA Button
- **Purpose:** Encourage user to take a primary action.
- **Visual:** Solid color button with a clear label.
- **Dimensions:** `padding: space-2 space-4`.
- **Tokens:**
  - `background-color: --color-primary`
  - `color: --color-neutral-100`
  - `border-radius: --border-radius-lg`
- **States:**
  - `hover`: `background-color: #CC3700`
  - `active`: `transform: scale(0.95)`
  - `disabled`: `opacity: 0.5`, `cursor: not-allowed`
- **Tailwind:** `bg-primary text-white font-bold py-2 px-4 rounded-lg`

---

## Section 3: Page Layouts

- **Structure:** 12-column grid with `max-width: 1280px`.
- **Hierarchy:** Clear visual hierarchy with a single `h1` per page, followed by `h2`s and `h3`s.
- **Navigation:**
  - Primary navigation in the header.
  - Footer navigation for secondary links.
- **Hero Treatment:** Utilize a high-energy, short video clip of a CrossFit class as a background for the hero section on the homepage. The video should be muted, and have a semi-transparent overlay to ensure text legibility.

---

## Section 4: Accessibility Requirements

- **Color Contrast:** All text must have a minimum WCAG AA contrast ratio.
- **Keyboard Navigation:** All interactive elements must be focusable and operable with the keyboard. Focus order must be logical.
- **ARIA Roles:**
  - `nav` for navigation sections.
  - `main` for the main content area.
  - `button` for all button-like elements.
  - `aria-label` for all icon-only buttons.
- **Forms:** All form inputs must have associated labels.

---

## Section 5: Recommended Next.js File Structure

```
/app
  /api
  /components
    /ui
      Button.tsx
      Card.tsx
      Input.tsx
    /layout
      Header.tsx
      Footer.tsx
      MobileNav.tsx
    Hero.tsx
    Pricing.tsx
  /lib
    utils.ts
  /(pages)
    layout.tsx
    page.tsx
    /about
      page.tsx
    /pricing
      page.tsx
```
