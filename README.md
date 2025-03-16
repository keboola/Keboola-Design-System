# Keboola Design System

A comprehensive design system for building consistent web interfaces with Keboola style.

## Overview
1. [Introduction](#introduction)
2. [Getting Started](#getting-started)
   - [Required Dependencies](#required-dependencies)
   - [Example Pages](#example-pages)
   - [Basic Page Structure](#basic-page-structure)
3. [Design Tokens](#design-tokens)
   - [Color System](#color-system)
   - [Typography System](#typography-system)
   - [Spacing System](#spacing-system)
4. [Layout & Structure](#layout-and-structure)
   - [Page Container](#page-container)
   - [Grid System](#grid-system)
   - [Header & Footer Spacing](#header-and-footer-spacing)
   - [Section Spacing](#section-spacing)
5. [Core Components](#core-components)
   - [Header](#header)
   - [Buttons](#buttons)
   - [Cards](#cards)
     - [Basic Card](#basic-card)
     - [Overview Card](#overview-card)
     - [Grey Overview Card](#grey-overview-card)
     - [Grey Overview Cards in Container](#grey-overview-cards-in-container)
     - [Card Variants](#card-variants)
     - [Card Layout Helper Classes](#card-layout-helper-classes)
     - [Using Cards in Links](#using-cards-in-links)
   - [Tabs](#tabs)
   - [Form Elements](#form-elements)
   - [Activity Row](#activity-row)
   - [Badges](#badges)
6. [Icon System](#icon-system)
   - [Basic Setup](#basic-icon-setup)
   - [Sizes & Colors](#icon-sizes-and-colors)
   - [Best Practices](#icon-best-practices)
7. [Common Patterns](#common-patterns)
   - [Form Card](#form-card-pattern)
   - [Activity List](#activity-list-pattern)
8. [Best Practices and Common Mistakes](#best-practices-and-common-mistakes)
9. [Project Structure](#project-structure)
10. [Support & Contributing](#support-and-contributing)

## Introduction

The Keboola Design System provides a consistent set of components, patterns, and guidelines for building Keboola applications. It ensures visual consistency, improves development efficiency, and creates a cohesive user experience across all Keboola products.

## Getting Started

### Required Dependencies

Include these dependencies in your HTML file:

```html
<!-- Required Dependencies -->
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" rel="stylesheet">
<link href="dist/design-system.css" rel="stylesheet">
```

### Example Pages

The `examples/` directory contains complete, ready-to-use example pages that demonstrate how to implement the design system:

- **login-register.html**: A login and registration page with form validation and tabbed interface
- **people-management.html**: A user management dashboard example
- **transportation-dashboard.html**: A data visualization dashboard example

These examples showcase proper implementation of components, layout patterns, and responsive design. They're a great starting point for building your own pages.

### Basic Page Structure

Every page should follow this basic structure:

```html
<body class="bg-grey-50">
  <div class="container page-container" style="padding: var(--space-16)">
    <div class="content-wrapper" style="display: flex; flex-direction: column; gap: var(--space-6)">
      <header class="header" style="margin-bottom: var(--space-6)">
        <h1 class="header__title heading-1">Page Title</h1>
      </header>
      
      <section class="section">
        <!-- Content -->
      </section>
    </div>
  </div>
</body>
```

## Design Tokens

### Color System

#### Available Color Tokens

```css
/* Neutral Colors */
--neutral-white: #ffffff;
--neutral-grey-50: #f2f4f7;    /* Background color */
--neutral-grey-100: #edf0f5;
--neutral-grey-150: #d9dde5;
--neutral-grey-200: #c5cbd6;
--neutral-grey-300: #a2aab8;
--neutral-grey-400: #7c8594;
--neutral-grey-500-base: #565c66;
--neutral-grey-600: #454952;   /* Meta text */
--neutral-grey-800: #222529;   /* Body text */
--neutral-grey-900: #101114;   /* Headings */

/* Secondary Colors - Blue */
--secondary-blue-800: #064a8f;
--secondary-blue-700: #075fb8;
--secondary-blue-600: #0975e0;  /* Primary blue for icons and accents */
--secondary-blue-500-base: #1f8fff;
--secondary-blue-450: #3e9eff;
--secondary-blue-200: #c2e0ff;
--secondary-blue-100: #e0f0ff;

/* Success Colors - Green */
--success-green-800: #158b15;
--success-green-700: #189f18;
--success-green-600: #1bb31b;
--success-green-500-base: #1ec71e;
--success-green-200: #baf5ba;
--success-green-100: #e0ffe0;

/* Warning Colors - Orange */
--warning-orange-600: #d17d00;
--warning-orange-550: #e38800;
--warning-orange-500-base: #f59300;
--warning-orange-300: #ffd699;
--warning-orange-200: #ffe7c2;
--warning-orange-100: #fff3e0;

/* Error Colors - Red */
--error-red-700: #a3001b;
--error-red-600: #b8001f;
--error-red-550: #c40021;
--error-red-500-base: #e00025;
--error-red-200: #ffc2cc;
--error-red-100: #ffe0e6;

/* Accent Colors */
--accent-purple-600: #6f36e0;
--accent-purple-500-base: #925cff;
--accent-purple-200: #d6c2ff;
--accent-purple-100: #ebe0ff;
--accent-cyan-600: #00a0b2;
--accent-cyan-500-base: #00bbd1;
--accent-cyan-200: #bef3ff;
--accent-cyan-100: #e0f9ff;
--accent-teal-600: #00a673;
--accent-teal-500-base: #00c287;
--accent-teal-200: #96ffce;
--accent-teal-100: #cfffe6;
```

#### Using Color Tokens

```html
<!-- Using color tokens in inline styles -->
<div style="background-color: var(--secondary-blue-600);">Blue background</div>

<!-- Using predefined background classes -->
<div class="bg-white">White background</div>
<div class="bg-grey-50">Light grey background</div>

<!-- Text colors -->
<p class="text-grey-900">Primary Text</p>
<p class="text-grey-600">Subtitle Text</p>

<!-- ✅ Do use CSS variables -->
<div style="background-color: var(--secondary-blue-600);">Correct</div>
<!-- ❌ Don't use hex values directly -->
<div style="background-color: #0975e0;">Wrong</div>
```

### Typography System

#### Font Setup

```html
<head>
    <!-- Preload critical fonts for performance -->
    <link rel="preload" href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" as="style">
    
    <!-- Required font dependencies -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    
    <!-- Design System CSS -->
    <link href="dist/design-system.css" rel="stylesheet">
    
    <!-- REQUIRED: Base font styles -->
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: var(--body-body-family);
            background-color: var(--neutral-grey-50);
            color: var(--neutral-grey-800);
            line-height: var(--body-body-line-height);
        }
    </style>
</head>
```

> ⚠️ **Important**: Both the font preloading and base font styles are required for all pages. Omitting either will result in inconsistent typography and performance issues.

#### Text Hierarchy

```html
<!-- Headings -->
<h1 class="heading-1">32px, Medium (500)</h1>
<h2 class="heading-2">24px, Medium (500)</h2>
<h3 class="heading-3">16px, Medium (500)</h3>
<h4 class="heading-4">12px, Medium (500)</h4>

<!-- Body Text -->
<p class="body-text">14px, Regular (400)</p>
<p class="body-text-medium">14px, Medium (500)</p>

<!-- Small Text -->
<p class="small-body-text">12px, Regular (400)</p>
<p class="small-body-text-medium">12px, Medium (500)</p>
```

#### Links

The design system provides several link components with proper styling and hover states:

```html
<!-- Link Variants -->
<a href="#" class="link-h3">Heading Link</a>
<a href="#" class="link-body-medium">Medium Body Link</a>
<a href="#" class="link-body">Regular Body Link</a>
<a href="#" class="link-small-body-medium">Small Medium Link</a>

<!-- ✅ Do use link classes -->
<a href="#" class="link-small-body-medium">Forgot password?</a>
<!-- ❌ Don't use custom link styles -->
<a href="#" style="color: blue; text-decoration: underline;">Forgot password?</a>
```

Link components include:
- Proper text decoration (underlined by default)
- Correct color (var(--secondary-blue-500-base))
- Appropriate hover states (color changes to var(--secondary-blue-600))
- Consistent font family, size, weight, and line height

#### Text Colors

```html
<!-- Text Colors -->
<p class="text-grey-900">Primary Text</p>
<p class="text-grey-800">Secondary Text</p>
<p class="text-grey-600">Subtitle Text</p>
<p class="text-grey-500">Disabled Text</p>
```

#### Font Weights

- `400` - Regular text, body content
- `500` - Medium weight, headings and emphasis
- `600` - Semibold, strong emphasis
- `700` - Bold, very strong emphasis

#### Typography Best Practices

1. Use the provided typography classes instead of direct font properties
2. Follow the font-weight guidelines
3. Include fallback fonts
4. **Always preload critical fonts** - This is mandatory for performance
5. **Always include base font styles** - This ensures consistent typography across all pages
6. Use proper font subsets when possible

### Spacing System

#### Spacing Variables

```css
--space-0: 0;
--space-1: 4px;
--space-2: 8px;
--space-3: 12px;
--space-4: 16px;
--space-5: 20px;
--space-6: 24px;
--space-8: 32px;
--space-10: 40px;
--space-12: 48px;
--space-16: 64px;
```

#### Gap-Based Spacing Approach

The Keboola Design System uses a gap-based spacing approach for more consistent, maintainable layouts:

- **Container-level spacing**: Use `gap` properties on parent containers to create consistent spacing between child elements
- **Component-specific internal spacing**: Use margins and padding within components for internal spacing

This approach eliminates the need for margin hacks and creates more predictable layouts.

#### Benefits of Gap-Based Spacing

1. **Cleaner Code**: Eliminates the need for margin hacks or "margin-bottom-except-last-child" patterns
2. **More Predictable**: Creates consistent spacing without the complexity of collapsing margins
3. **Easier Maintenance**: Only need to change one value (the gap) instead of multiple margin declarations
4. **Better for Responsive Design**: Scales more predictably across different screen sizes

#### Migration from Margin-Based to Gap-Based Spacing

##### Before (Margin-Based Approach)
```html
<div class="content-wrapper">
  <header class="header" style="margin-bottom: var(--space-6)">
    <!-- Header content -->
  </header>
  
  <section class="section" style="margin-bottom: var(--space-6)">
    <!-- Section content -->
  </section>
  
  <section class="section" style="margin-bottom: var(--space-6)">
    <!-- Another section -->
  </section>
</div>
```

##### After (Gap-Based Approach)
```html
<div class="content-wrapper" style="display: flex; flex-direction: column; gap: var(--space-6)">
  <header class="header">
    <!-- Header content -->
  </header>
  
  <section class="section">
    <!-- Section content -->
  </section>
  
  <section class="section">
    <!-- Another section -->
  </section>
</div>
```

##### Migration Steps:
1. Add `display: flex; flex-direction: column; gap: var(--space-6)` to the content wrapper
2. Remove all `margin-bottom` or `margin-top` from sections
3. Keep component-specific internal spacing (like card footer margin-top)

#### Common Spacing Patterns

- Use `var(--space-4)` (16px) for:
  - All card layouts (both within rows and between rows)
  - Internal component spacing
  - Form group spacing
  - Card content padding
  - Grid gaps for card layouts
- Use `var(--space-6)` (24px) for:
  - Spacing between major sections
  - Container gap for sections
  - Content block separation
- Use `var(--space-8)` (32px) for:
  - Large component separation
  - Major content blocks
- Use `var(--space-16)` (64px) for:
  - Page container padding
  - Major layout divisions

## Layout & Structure

### Page Container

Every page must follow these container rules:

```html
<body class="bg-grey-50">
  <div class="container page-container" style="padding: var(--space-16)">
    <div class="content-wrapper" style="display: flex; flex-direction: column; gap: var(--space-6)">
      <header class="header">
        <h1 class="header__title heading-1">Page Title</h1>
      </header>
      
      <section class="section">
        <!-- Content -->
      </section>
    </div>
  </div>
</body>
```

Key requirements:
- Always use `bg-grey-50` on body
- Wrap content in `container page-container` with padding: var(--space-16) (64px)
- Use `content-wrapper` with gap: var(--space-6) (24px) for vertical spacing between sections
- **Do not add margins to sections** - rely on the parent container's gap

### Shadows

The design system provides consistent shadow variables for different UI elements:

```css
/* Shadow Variables */
--card-shadow: 0 3px 3px 0 rgba(34 37 41 / 0.08);
--dialog-shadow: 0 3px 4px 0 rgba(34 37 41 / 0.12);
--active-element: 0 0 0 4px rgba(31 143 255 / 0.2);
```

Usage examples:
```html
<!-- Card with proper shadow -->
<div class="card bg-white">...</div>

<!-- Custom element with card shadow -->
<div style="box-shadow: var(--card-shadow);">...</div>

<!-- ✅ Do use shadow variables -->
<div style="box-shadow: var(--card-shadow);">Correct</div>
<!-- ❌ Don't use custom shadow values -->
<div style="box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);">Wrong</div>
```

### Grid System

The design system provides a consistent grid system:

#### Card Grid
```html
<div class="grid grid-cols-3" style="gap: var(--space-4)">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```
- Use `gap: var(--space-4)` (16px) consistently for all card layouts
- This creates visual consistency across all card-based layouts

#### Section Grid
```html
<div class="content-wrapper" style="display: flex; flex-direction: column; gap: var(--space-6)">
  <section>Section 1</section>
  <section>Section 2</section>
</div>
```
- Use `gap: var(--space-6)` (24px) for spacing between major sections
- This creates clear visual separation between content sections

### Header & Footer Spacing

While we use gap for spacing between components, internal component spacing still uses margins and padding:

#### Header Spacing
```html
<header class="header">
  <h1 class="header__title">Page Title</h1>
</header>
```
- Headers no longer need margin-top or margin-bottom - the parent container's gap handles spacing
- This creates a clear visual separation between the header and content below/above

#### Footer Spacing
```html
<div class="card__footer" style="margin-top: var(--space-6)">
  <button class="btn btn-primary">
    <span class="btn-text">Submit</span>
  </button>
</div>
```
- Card footers should have `margin-top: var(--space-6)` to separate them from content above
- This creates breathing room between main content and footer actions

### Section Spacing

```html
<!-- Sections with cards -->
<section class="section">
  <!-- Content -->
</section>
```

- Use the parent container's `gap: var(--space-6)` for spacing between sections
- Use `gap: var(--space-4)` (16px) for cards within sections
- Use `gap: var(--space-8)` (32px) for large content blocks

### Layout Examples

#### Dashboard Layout Example
```html
<div class="content-wrapper" style="display: flex; flex-direction: column; gap: var(--space-6)">
  <header class="header">
    <h1 class="header__title">Dashboard</h1>
    <div class="header__actions">
      <button class="btn btn-primary">
        <span class="btn-text">NEW ITEM</span>
      </button>
    </div>
  </header>

  <section class="section">
    <div class="grid grid-cols-4" style="gap: var(--space-4)">
      <!-- Overview cards -->
    </div>
  </section>

  <section class="section">
    <div class="grid grid-cols-2" style="gap: var(--space-6)">
      <!-- Content cards -->
    </div>
  </section>
</div>
```

#### Form Layout Example
```html
<div class="content-wrapper" style="display: flex; flex-direction: column; gap: var(--space-6)">
  <header class="header">
    <h1 class="header__title">Create New Item</h1>
  </header>

  <section class="section">
    <div class="card bg-white">
      <h2 class="card__title">Form Title</h2>
      <div class="card__content" style="display: flex; flex-direction: column; gap: var(--space-4)">
        <div class="form-group">
          <!-- Form inputs -->
        </div>
        <div class="form-group">
          <!-- More form inputs -->
        </div>
      </div>
      <div class="card__footer" style="margin-top: var(--space-6)">
        <button class="btn btn-primary">
          <span class="btn-text">SUBMIT</span>
        </button>
      </div>
    </div>
  </section>
</div>
```

## Core Components

### Header

```html
<header class="header">
  <h1 class="header__title">Page Title</h1>
  <div class="header__actions">
    <!-- Secondary buttons first -->
    <button class="btn btn-secondary btn-medium">
      <div class="btn-icon">
        <i class="fas fa-cog icon-muted"></i>
      </div>
      <span class="btn-text">SETTINGS</span>
    </button>
    <!-- Primary button last -->
    <button class="btn btn-primary btn-medium">
      <div class="btn-icon">
        <i class="fas fa-plus text-white"></i>
      </div>
      <span class="btn-text">ADD NEW</span>
    </button>
  </div>
</header>
```

Header requirements:
- Use `.header` as the main container
- Include `.header__title` for the page title
- Use `.header__actions` for button container
- Place secondary buttons before primary buttons
- No margin-bottom needed - parent container's gap handles spacing

### Buttons

```html
<!-- Primary Button (Medium - 40px) -->
<button class="btn btn-primary btn-medium">
  <div class="btn-icon">
    <i class="fas fa-plus text-white"></i>
  </div>
  <span class="btn-text">BUTTON TEXT</span>
</button>

<!-- Secondary Button (Medium - 40px) -->
<button class="btn btn-secondary btn-medium">
  <div class="btn-icon">
    <i class="fas fa-cog icon-muted"></i>
  </div>
  <span class="btn-text">BUTTON TEXT</span>
</button>

<!-- Small Primary Button (32px) -->
<button class="btn btn-primary btn-small">
  <span class="btn-text">BUTTON TEXT</span>
</button>

<!-- Small Secondary Button (32px) -->
<button class="btn btn-secondary btn-small">
  <span class="btn-text">BUTTON TEXT</span>
</button>

<!-- Icon-Only Primary Button (Medium - 40px) -->
<button class="btn btn-primary btn-icon-only btn-medium">
  <div class="btn-icon">
    <i class="fas fa-plus text-white"></i>
  </div>
</button>

<!-- Icon-Only Secondary Button (Medium - 40px) -->
<button class="btn btn-secondary btn-icon-only btn-medium">
  <div class="btn-icon">
    <i class="fas fa-cog icon-muted"></i>
  </div>
</button>

<!-- Icon-Only Primary Button (Small - 32px) -->
<button class="btn btn-primary btn-icon-only btn-small">
  <div class="btn-icon">
    <i class="fas fa-plus text-white"></i>
  </div>
</button>

<!-- Icon-Only Secondary Button (Small - 32px) -->
<button class="btn btn-secondary btn-icon-only btn-small">
  <div class="btn-icon">
    <i class="fas fa-cog icon-muted"></i>
  </div>
</button>
```

Button requirements:
- Always wrap text in `.btn-text`
- Always use UPPERCASE for button text
- Wrap icons in `.btn-icon`
- Use `text-white` for icons in primary buttons
- Use `icon-muted` for icons in secondary buttons
- Use `btn-medium` (40px) for standard buttons
- Use `btn-small` (32px) for compact UI areas or secondary actions

### Cards

#### Basic Card
```html
<div class="card bg-white">
  <h2 class="card__title">Card Title</h2>
  <div class="card__content">
    <!-- Content -->
  </div>
  <div class="card__footer">
    <!-- Footer actions -->
  </div>
</div>
```

#### Overview Card
```html
<div class="overview-card bg-white">
  <div class="overview-card__header">
    <span class="overview-card__title">Title</span>
    <span class="badge badge-success">
      <span class="badge-text">Status</span>
    </span>
  </div>
  <div class="overview-card__value">Value</div>
  <div class="overview-card__subtitle">Subtitle</div>
</div>
```

#### Grey Overview Card
```html
<div class="overview-card overview-card--grey">
  <div class="overview-card__header">
    <span class="overview-card__title">Title</span>
  </div>
  <div class="overview-card__value">Value</div>
  <div class="overview-card__subtitle">Subtitle</div>
</div>
```

#### Grey Overview Cards in Container
```html
<div class="card bg-white">
  <h2 class="card__title">Container Title</h2>
  <div class="card__content">
    <div class="grid grid-cols-3" style="gap: var(--space-4)">
      <div class="overview-card overview-card--grey">
        <!-- Overview card content -->
      </div>
      <div class="overview-card overview-card--grey">
        <!-- Overview card content -->
      </div>
      <div class="overview-card overview-card--grey">
        <!-- Overview card content -->
      </div>
    </div>
  </div>
</div>
```

#### Card Variants

```html
<!-- Standard Card -->
<div class="card bg-white">
  <h2 class="card__title">Card Title</h2>
  <div class="card__content">
    <!-- Content -->
  </div>
</div>

<!-- Card with Description -->
<div class="card card--with-description bg-white">
  <h2 class="card__title">Card Title</h2>
  <div class="card__content">
    <p class="body-text">This is a description paragraph. The card--with-description variant handles paragraph margins, sets text color to grey-400, and includes hover effects.</p>
  </div>
</div>

<!-- Card with Icon Title -->
<div class="card bg-white">
  <div class="card__title--with-icon">
    <div class="icon-container icon-small">
      <i class="fas fa-chart-line"></i>
    </div>
    <span class="card__title-text">Card Title with Icon</span>
  </div>
  <div class="card__content">
    <!-- Content -->
  </div>
</div>

<!-- Card with Action Button -->
<div class="card card--with-description">
  <h2 class="card__title">Card Title</h2>
  <div class="card__content">
    <p>Card content goes here.</p>
  </div>
  <div class="card__footer">
    <button class="btn btn-primary btn-small">
      <span class="btn-text">ACTION</span>
    </button>
  </div>
</div>

<!-- Combined: Card with Description, Icon Title, and Action Button -->
<div class="card card--with-description bg-white">
  <div class="card__title--with-icon">
    <div class="icon-container icon-small">
      <i class="fas fa-chart-line"></i>
    </div>
    <span class="card__title-text">Card with Everything</span>
  </div>
  <div class="card__content">
    <p class="body-text">This card combines all features: icon title, description styling, and an action button.</p>
  </div>
  <div class="card__footer">
    <button class="btn btn-primary btn-small">
      <span class="btn-text">ACTION</span>
    </button>
  </div>
</div>
```

Card variant requirements:
- `card--with-description`: Optimized for cards with a title and description paragraph
  - Adds proper padding (12px top, 24px sides and bottom)
  - Automatically handles paragraph margins
  - Sets description text color to grey-400
  - Adds hover effect with enhanced shadow and slight opacity change
  - Includes proper cursor pointer for clickable cards
- `card__title--with-icon`: Displays an icon next to the card title
  - Uses the standard `icon-container` component for icons
  - Requires a card__title-text element for the title text
  - Icons are grey (neutral-grey-400) by default
  - Properly aligns icon and title with consistent spacing
- `card__footer`: Positions buttons or actions at the bottom of the card
  - Adds 16px top margin for proper spacing from content
  - Supports multiple buttons with 16px gap between them
  - Aligns with the card's content area

#### Card Layout Helper Classes

The design system provides helper classes for controlling card layouts within grid containers:

```html
<!-- Equal height cards -->
<div class="grid grid-cols-2 equal-height-cards" style="gap: var(--space-6)">
  <div class="card bg-white">...</div>
  <div class="card bg-white">...</div>
</div>

<!-- Cards with aligned footers -->
<div class="grid grid-cols-2 equal-height-cards aligned-footers" style="gap: var(--space-6)">
  <div class="card bg-white">
    <h2 class="card__title">Card Title</h2>
    <div class="card__content">...</div>
    <div class="card__footer">...</div>
  </div>
  <div class="card bg-white">
    <h2 class="card__title">Card Title</h2>
    <div class="card__content">...</div>
    <div class="card__footer">...</div>
  </div>
</div>
```

**Important requirements:**
- `equal-height-cards`: Makes all cards in a row the same height
- `aligned-footers`: Positions card footers at the bottom of each card
- When using `aligned-footers`, **all cards must have a footer element**
- If some cards don't need footers, don't use the `aligned-footers` class
- For simple card layouts, use only the grid classes without these helpers

**Example use cases:**
- Use `equal-height-cards` when cards have varying content lengths but should appear uniform
- Use `aligned-footers` when cards have action buttons that should be aligned at the bottom
- For dashboard layouts with mixed content types, prefer simple grid layouts without these helpers

**Common mistakes to avoid:**
- ❌ Don't use `aligned-footers` when some cards don't have footer elements
- ❌ Don't add these helper classes to all grid containers by default
- ❌ Don't mix cards with and without footers in the same `aligned-footers` container

#### Using Cards in Links

When wrapping cards in `<a>` tags to make them clickable, be aware of potential style inheritance issues:

```html
<!-- Proper way to use cards in links -->
<a href="page.html" class="card-link">
  <div class="card card--with-description">
    <!-- Card content -->
  </div>
</a>
```

```css
/* Required CSS to prevent link color inheritance */
a.card-link {
  text-decoration: none;
  color: inherit;
}

/* Ensure icon colors aren't affected by link color */
.card__title--with-icon .icon-container {
  color: var(--neutral-grey-400);
}
```

This prevents the default browser link color (#0000ee) from being inherited by card elements, especially icons.

### Tabs

```html
<!-- Tabs (standalone component) -->
<div class="tabs tabs-large">
    <div class="tab-item active">
        <div class="tab-content">
            <div class="icon-container icon-small">
                <i class="fas fa-globe"></i>
            </div>
            <div class="tab-text">Tab Label</div>
        </div>
        <div class="tab-active-line"></div>
    </div>
</div>
```

Tab requirements:
- Use tabs as standalone components
- Don't wrap tabs in cards
- Include `.tab-active-line` for active tabs
- Use proper icon containers in tabs

### Form Elements

#### Form Spacing
```html
<div class="card">
    <h2 class="card__title">Form Title</h2>
    <div class="card__content" style="display: flex; flex-direction: column; gap: var(--space-4)">
        <div class="form-group">
            <!-- Form element -->
        </div>
        <div class="form-group">
            <!-- Next form element -->
        </div>
    </div>
</div>
```

#### Text Input
```html
<div class="form-group">
  <div class="text-input">
    <div class="label">
      <label class="label-text" for="input-id">Label</label>
    </div>
    <div class="content">
      <input type="text" id="input-id" placeholder="Placeholder">
    </div>
  </div>
</div>
```

#### Textarea
```html
<div class="form-group">
  <div class="text-input">
    <div class="label">
      <label class="label-text" for="textarea-id">Label</label>
    </div>
    <div class="content">
      <textarea id="textarea-id" rows="3" placeholder="Placeholder"></textarea>
    </div>
  </div>
</div>
```

#### Select
```html
<div class="form-group">
  <div class="select">
    <div class="label">
      <label class="label-text" for="select-id">Label</label>
    </div>
    <button type="button" class="select-trigger" id="select-id">
      <span>Select option</span>
      <i class="fas fa-chevron-down"></i>
    </button>
  </div>
</div>
```

Form requirements:
- Use `gap: var(--space-4)` on `card__content` for spacing between form groups
- Keep form elements organized in `form-group` and `text-input` structure
- Always include labels with proper `for` attributes

### Activity Row

```html
<div class="activity-row">
  <div class="activity-row__content">
    <div class="icon-container icon-small">
      <i class="fas fa-check-circle"></i>
    </div>
    <span class="activity-row__text">Activity Description</span>
  </div>
  <div class="activity-row__meta">
    <span>Time or Status</span>
  </div>
</div>
```

### Badges

```html
<span class="badge badge-success">
  <span class="badge-text">Success</span>
</span>

<span class="badge badge-warning">
  <span class="badge-text">Warning</span>
</span>

<span class="badge badge-error">
  <span class="badge-text">Error</span>
</span>
```

## Icon System

### Basic Icon Setup

```html
<!-- Basic Icon -->
<div class="icon-container icon-small">
    <i class="fas fa-user icon-muted"></i>
</div>

<!-- Large Icon -->
<div class="icon-container icon-large">
    <i class="fas fa-user icon-muted"></i>
</div>
```

### Icon Sizes and Colors

#### Icon Sizes
- `icon-small`: 20x20px container with 16x16px icon (default)
- `icon-large`: 32x32px container with 24x24px icon

#### Icon Colors
```html
<!-- Default grey icons (use this most of the time) -->
<div class="icon-container icon-small">
    <i class="fas fa-user icon-muted"></i>
</div>

<!-- Semantic colors (use only when icon represents a status) -->
<div class="icon-container icon-small">
    <i class="fas fa-check icon-success"></i>
</div>
<div class="icon-container icon-small">
    <i class="fas fa-exclamation-triangle icon-warning"></i>
</div>
<div class="icon-container icon-small">
    <i class="fas fa-times-circle icon-error"></i>
</div>
```

### Icon Best Practices

1. Always wrap icons in `icon-container`
2. Always specify the size (`icon-small` or `icon-large`)
3. Use `icon-muted` class for default grey icons
4. Use semantic colors only for status indicators
5. Keep icons aligned with text using the container
6. Use Font Awesome 6.5.1 or newer

### Icon + Text Spacing

When combining icons with text (especially in empty states or status indicators), always use a 12px gap (var(--space-3)) between the icon and text:

```html
<!-- Icon + Text with proper 12px spacing -->
<div style="display: flex; align-items: center; gap: var(--space-3);">
    <div class="icon-container icon-large">
        <i class="fas fa-chart-pie icon-muted"></i>
    </div>
    <span class="body-text-medium">Text label</span>
</div>
```

This consistent 12px spacing creates proper visual hierarchy and improves readability across the interface.

#### Empty State Example

```html
<!-- Empty state with icon + text -->
<div style="display: flex; align-items: center; justify-content: center;">
    <div style="display: flex; align-items: center; gap: var(--space-3);">
        <div class="icon-container icon-large">
            <i class="fas fa-chart-line icon-muted"></i>
        </div>
        <span class="body-text-medium">No data available</span>
    </div>
</div>
```

## Common Patterns

### Form Card Pattern

```html
<div class="card bg-white">
  <h2 class="card__title">Form Title</h2>
  <div class="card__content" style="display: flex; flex-direction: column; gap: var(--space-4)">
    <div class="form-group">
      <!-- Form inputs -->
    </div>
  </div>
  <div class="card__footer" style="margin-top: var(--space-6)">
    <button class="btn btn-primary btn-medium">
      <span class="btn-text">SUBMIT</span>
    </button>
  </div>
</div>
```

### Activity List Pattern

```html
<div class="card bg-white">
  <h2 class="card__title">Recent Activity</h2>
  <div class="card__content">
    <div class="activity-row">
      <!-- Activity row content -->
    </div>
    <div class="activity-row">
      <!-- Activity row content -->
    </div>
  </div>
</div>
```

## Best Practices and Common Mistakes

### Typography
- ✅ Use typography classes instead of direct font properties
- ✅ Follow the font-weight guidelines
- ✅ Include proper text color classes
- ❌ Don't mix typography classes incorrectly
- ❌ Don't skip small-body-text for subtitles
- ❌ Don't use raw font-size or font-weight values

### Layout
- ✅ Use `bg-grey-50` on body element
- ✅ Use `container page-container` with proper padding
- ✅ Use `content-wrapper` with gap for spacing between sections
- ✅ Use gap-based spacing instead of margins between components
- ❌ Don't skip page-container class
- ❌ Don't forget padding: var(--space-16) on page-container
- ❌ Don't use raw pixel values for gaps
- ❌ Don't add margins to sections when using gap-based spacing
- ❌ Don't wrap tabs in card components

### Components
- ✅ Use BEM naming convention
- ✅ Follow component hierarchy
- ✅ Use semantic HTML elements
- ❌ Don't use buttons without btn-text wrapper
- ❌ Don't forget to uppercase button text
- ❌ Don't skip icon-container for icons
- ❌ Don't skip default icon-muted for non-semantic icons
- ❌ Don't use muted icons in primary buttons (must be white)

### Header & Buttons
- ✅ Use header__actions container for buttons
- ✅ Place secondary buttons before primary buttons
- ❌ Don't use raw flex classes for header actions
- ❌ Don't place primary button before secondary buttons
- ❌ Don't skip header__actions container
- ❌ Don't use icons without btn-icon wrapper

### Spacing
- ✅ Use the content-wrapper's gap property (var(--space-6)) for spacing between sections
- ✅ Use consistent 16px gap (var(--space-4)) for all card layouts
- ✅ Maintain component-specific internal spacing (like card footer margin-top)
- ✅ Use 12px gap (var(--space-3)) between icons and text
- ❌ Don't add margins to sections when using gap-based spacing
- ❌ Don't mix margin-based and gap-based spacing at the same level
- ❌ Don't use raw pixel values instead of spacing variables
- ❌ Don't use different gap values for cards within the same layout

### Card Layouts
- ✅ Use simple grid layouts for most card arrangements
- ✅ Only use `equal-height-cards` when cards need to be the same height
- ✅ Only use `aligned-footers` when all cards have footer elements
- ✅ Ensure consistent card structure within the same grid container
- ❌ Don't use `aligned-footers` with cards that don't have footers
- ❌ Don't mix cards with and without footers in the same grid container
- ❌ Don't add helper classes to all grid containers by default

## Project Structure

```
project/
├── dist/
│   └── design-system.css (imports all components)
├── tokens/
│   ├── variables.css
│   ├── colors.css
│   ├── spacing.css
│   └── typography.css
├── styles/
│   └── layout.css
├── components/
│   ├── atoms/
│   └── molecules/
└── assets/
```

## Support and Contributing

### Support & Documentation
1. Check the example pages in the `examples/` directory:
   - `login-register.html`: Authentication forms with validation
   - `people-management.html`: User management interface
   - `transportation-dashboard.html`: Data dashboard layout with proper card grid implementation
2. Review component usage in `showcase.html`
3. Follow BEM naming conventions
4. Use the design tokens consistently

### Contributing
1. Follow the code quality standards
2. Test across different browsers
3. Ensure accessibility compliance
4. Document any new components
5. Update example pages as needed 