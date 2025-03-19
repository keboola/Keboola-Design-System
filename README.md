# Keboola Design System

A comprehensive design system for building consistent web interfaces with Keboola style.

## Documentation

- [Component Guide](./COMPONENT-GUIDE.md) - Detailed implementation guide for all components
- [Tokens](./tokens/) - Design tokens for colors, typography, and variables
- [Components](./components/) - Reusable UI components

## Table of Contents

1. [Introduction](#introduction)
2. [Project Structure](#project-structure)
3. [Getting Started](#getting-started)
   - [Installation](#installation)
   - [Basic Page Structure](#basic-page-structure)
   - [Example Pages](#example-pages)
4. [Design Tokens](#design-tokens)
   - [Color System](#color-system)
   - [Typography System](#typography-system)
   - [Spacing System](#spacing-system)
5. [Layout & Structure](#layout-and-structure)
   - [Page Container](#page-container)
   - [Shadows](#shadows)
   - [Grid System](#grid-system)
   - [Header & Footer Spacing](#header-and-footer-spacing)
   - [Section Spacing](#section-spacing)
   - [Layout Examples](#layout-examples)
6. [Core Components](#core-components)
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
   - [Banners](#banners)
7. [Icon System](#icon-system)
   - [Basic Icon Setup](#basic-icon-setup)
   - [Icon Sizes & Colors](#icon-sizes-and-colors)
   - [Icon Best Practices](#icon-best-practices)
   - [Icon + Text Spacing](#icon--text-spacing)
8. [Common Patterns](#common-patterns)
   - [Form Card Pattern](#form-card-pattern)
   - [Activity List Pattern](#activity-list-pattern)
9. [Best Practices and Common Mistakes](#best-practices-and-common-mistakes)
   - [Typography](#typography)
   - [Layout](#layout)
   - [Components](#components)
   - [Header & Buttons](#header--buttons)
   - [Spacing](#spacing)
   - [Card Layouts](#card-layouts)
10. [Support & Contributing](#support-and-contributing)
    - [Support & Documentation](#support--documentation)
    - [Contributing](#contributing)

## Introduction

The Keboola Design System provides a consistent set of components, patterns, and guidelines for building Keboola applications. It ensures visual consistency, improves development efficiency, and creates a cohesive user experience across all Keboola products.

## Project Structure

```
project/
├── dist/
│   └── design-system.css (imports all components)
├── tokens/
│   ├── variables.css    (spacing, radius, shadows)
│   ├── colors.css       (color palette, system colors)
│   └── typography.css   (font definitions, text styles)
├── components/
│   ├── atoms/           (basic building blocks)
│   │   ├── badge.css
│   │   ├── button.css
│   │   ├── icon.css     (icon sizing, containers, colors)
│   │   └── ...
│   ├── molecules/       (composite components)
│   │   ├── banner.css
│   │   ├── card.css
│   │   ├── topbar.css   (navigation component)
│   │   └── ...
│   └── organisms/       (complex component groups)
│       ├── dashboard.css
│       └── ...
├── styles/
│   └── layout.css       (grid system, containers)
└── assets/
    ├── icons/
    ├── logos/
    └── avatars/
```

This organization follows atomic design principles:
- **Tokens**: Design foundations like colors, typography, and spacing
- **Atoms**: Smallest UI elements (buttons, icons, badges)
- **Molecules**: Groups of atoms forming distinct sections (cards, banners)
- **Organisms**: Complex components combining multiple molecules
- **Assets**: Static resources used across components

All CSS is modular and follows a consistent naming convention to prevent conflicts.

## Getting Started

For a comprehensive guide on getting started with the Keboola Design System, please refer to the [Component Guide](./COMPONENT-GUIDE.md).

### Installation

⚠️ **Important Installation Considerations**:

1. **Folder Naming**: 
   - ✅ Recommended: Use "keboola-design-system" with hyphens
   - ❌ Avoid: Spaces in folder names like "keboola design system" can cause issues in some environments

2. **Path References**: 
   - If you place the design system in a subfolder of your project, update CSS paths accordingly:
   ```html
   <!-- Example if design system is in a subfolder -->
   <link href="keboola-design-system/dist/design-system.css" rel="stylesheet">
   ```

3. **Asset References**:
   - Update any paths to assets (logos, images) to reflect your folder structure
   - Example files may need path adjustments to work in your specific setup

4. **Testing After Installation**:
   - Always verify that styles are loading correctly after installation
   - Check browser console for any 404 errors related to missing files

### Example Pages

The `examples/` directory contains complete, ready-to-use example pages that demonstrate how to implement the design system:

- **index.html**: Main examples index page
- **login-register.html**: A login and registration page with form validation and tabbed interface
- **people-management.html**: A user management dashboard example
- **transportation-dashboard.html**: A data visualization dashboard example
- **car-dashboard.html**: An automotive metrics dashboard
- **bitcoin-dashboard.html**: A cryptocurrency tracking dashboard
- **sales-dashboard.html**: A sales analytics dashboard with proper banner implementation
- **overview-card-demo.html**: Examples of different overview card implementations

These examples showcase proper implementation of components, layout patterns, and responsive design. They're a great starting point for building your own pages.

> **⚠️ Important Note**: The `examples/` directory is for reference and learning purposes only. When implementing the design system in your own project:
> 
> 1. **DO NOT** add new pages to the `examples/` directory
> 2. **DO NOT** modify existing example pages unless you're fixing bugs
> 3. **DO** create your own HTML files in your project directory
> 4. **DO** use the examples as reference for proper implementation patterns
>
> The examples directory should only be modified when developing new components or debugging existing ones.

### Basic Page Structure

Every page should follow this basic structure:

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
--secondary-blue-600: #0975e0;
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
    <h1 class="header__title heading-1">Car Fleet Management Dashboard</h1>
    <div class="header__actions">
      <button class="btn btn-secondary btn-medium">
        <div class="btn-icon">
          <i class="fas fa-download icon-muted"></i>
        </div>
        <span class="btn-text">EXPORT REPORT</span>
      </button>
      <button class="btn btn-primary btn-medium">
        <div class="btn-icon">
          <i class="fas fa-plus text-white"></i>
        </div>
        <span class="btn-text">ADD VEHICLE</span>
      </button>
    </div>
  </header>

  <div class="tabs tabs-large">
    <div class="tab-item active">
      <div class="tab-content">
        <div class="icon-container icon-small">
          <i class="fas fa-car"></i>
        </div>
        <div class="tab-text">Fleet Overview</div>
      </div>
      <div class="tab-active-line"></div>
    </div>
    <!-- Additional tabs -->
  </div>

  <section class="section">
    <div class="grid grid-cols-4" style="gap: var(--space-4)">
      <!-- Overview cards -->
    </div>
  </section>
</div>
```

#### Form Layout Example
```html
<div class="auth-container">
  <div class="auth-card bg-white">
    <div class="auth-header">
      <img src="../assets/logo.svg" alt="Keboola Logo" width="120" height="32">
      <h1 class="heading-2" style="margin-top: var(--space-6)">Sign In</h1>
    </div>
    
    <div class="tabs tabs-large" style="margin: var(--space-6) 0;">
      <div class="tab-item active">
        <div class="tab-content">
          <div class="tab-text">Sign In</div>
        </div>
        <div class="tab-active-line"></div>
      </div>
      <div class="tab-item">
        <div class="tab-content">
          <div class="tab-text">Register</div>
        </div>
      </div>
    </div>
    
    <form style="display: flex; flex-direction: column; gap: var(--space-4)">
      <div class="form-group">
        <div class="text-input">
          <div class="label">
            <label class="label-text" for="email">Email</label>
          </div>
          <div class="content">
            <input type="email" id="email" placeholder="Enter your email">
          </div>
        </div>
      </div>
      
      <div class="form-group">
        <div class="text-input">
          <div class="label">
            <label class="label-text" for="password">Password</label>
          </div>
          <div class="content">
            <input type="password" id="password" placeholder="Enter your password">
          </div>
        </div>
      </div>
      
      <div style="margin-top: var(--space-4)">
        <button type="submit" class="btn btn-primary btn-medium" style="width: 100%">
          <span class="btn-text">SIGN IN</span>
        </button>
      </div>
    </form>
  </div>
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
- `card--no-padding`: Removes all internal padding from the card
  - Useful for cards that need custom internal spacing
  - Often used for cards with full-width content like tables or charts
- `card--compact`: Reduces the card's internal padding
  - Uses smaller padding values for more condensed layouts
  - Useful for information-dense interfaces
- `card--bordered`: Adds a border to the card instead of a shadow
  - Uses a 1px border with neutral-grey-200 color
  - Useful for cards that need to be visually separated but with less visual weight

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
    <div class="tab-item">
        <div class="tab-content">
            <div class="icon-container icon-small">
                <i class="fas fa-chart-line"></i>
            </div>
            <div class="tab-text">Another Tab</div>
        </div>
        <div class="tab-active-line"></div>
    </div>
</div>
```

Tab requirements:
- Use tabs as standalone components
- Don't wrap tabs in cards
- Include `.tab-active-line` for all tabs (required for hover effects)
- Use proper icon containers in tabs

### Form Elements

#### Form Spacing

Form elements should have consistent spacing between them. The design system provides a built-in rule for form-group spacing:

```html
<!-- Form with proper spacing -->
<form>
  <div class="form-group">
    <div class="text-input">
      <!-- Input content -->
    </div>
  </div>
  
  <div class="form-group">
    <div class="select">
      <!-- Select content -->
    </div>
  </div>
  
  <div class="form-group">
    <label class="checkbox">
      <!-- Checkbox content -->
    </label>
  </div>
</form>
```

This approach automatically adds a 16px (var(--space-4)) gap between form elements. When form-groups are used inside grid or flex containers, the container's gap property takes precedence to avoid double spacing.

✅ Do:
- Wrap each form element in a `.form-group` div
- Let the built-in spacing handle the gaps between elements
- Use grid or flex with gap for complex form layouts

❌ Don't:
- Add custom margins to form elements
- Use inconsistent spacing between form elements

#### Form Structure

For proper form organization and spacing, follow these guidelines:

```html
<!-- Form in a card -->
<div class="card bg-white">
  <h2 class="card__title">Form Title</h2>
  <div class="card__content" style="display: flex; flex-direction: column; gap: var(--space-4);">
    <!-- Group related form elements -->
    <div>
      <h3 class="heading-3" style="margin-bottom: var(--space-4);">Section Title</h3>
      <div style="display: flex; flex-direction: column; gap: var(--space-4);">
        <div class="form-group">
          <!-- Form element 1 -->
        </div>
        <div class="form-group">
          <!-- Form element 2 -->
        </div>
      </div>
    </div>
    
    <!-- Another group of related form elements -->
    <div>
      <h3 class="heading-3" style="margin-bottom: var(--space-4);">Another Section</h3>
      <div style="display: flex; flex-direction: column; gap: var(--space-4);">
        <div class="form-group">
          <!-- Form element 3 -->
        </div>
      </div>
    </div>
  </div>
  <div class="card__footer">
    <button class="btn btn-primary btn-medium">
      <span class="btn-text">SUBMIT</span>
    </button>
  </div>
</div>
```

This structure ensures:
- 16px spacing between major form sections
- 16px spacing between individual form elements within each section
- Proper visual grouping of related form elements
- Clear section headings for form organization

#### Text Input

```html
<!-- Standard Text Input -->
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

<!-- Required Text Input -->
<div class="form-group">
  <div class="text-input required">
    <div class="label">
      <label class="label-text" for="required-input">Required Input</label>
    </div>
    <div class="content">
      <input type="text" id="required-input" placeholder="Required field">
    </div>
  </div>
</div>

<!-- Disabled Text Input -->
<div class="form-group">
  <div class="text-input disabled">
    <div class="label">
      <label class="label-text" for="disabled-input">Disabled Input</label>
    </div>
    <div class="content">
      <input type="text" id="disabled-input" placeholder="Disabled field" disabled>
    </div>
  </div>
</div>
```

#### Textarea

```html
<div class="form-group">
  <div class="text-input">
    <div class="label">
      <label class="label-text" for="textarea-id">Description</label>
    </div>
    <div class="content">
      <textarea id="textarea-id" rows="3" placeholder="Enter description"></textarea>
    </div>
  </div>
</div>
```

#### Select

```html
<div class="form-group">
  <div class="select">
    <div class="label">
      <label class="label-text" for="select-id">Select Option</label>
    </div>
    <div class="select-wrapper">
      <select id="select-id" class="select-trigger">
        <option value="">Select an option</option>
        <option value="option1">Option 1</option>
        <option value="option2">Option 2</option>
        <option value="option3">Option 3</option>
      </select>
    </div>
  </div>
</div>
```

#### Checkbox

```html
<div class="form-group">
  <label class="checkbox">
    <input type="checkbox" id="checkbox-id">
    <div class="checkbox-box"></div>
    <div class="checkbox-label">
      <span class="checkbox-label-text">Checkbox label</span>
    </div>
  </label>
</div>

<!-- Checked Checkbox -->
<div class="form-group">
  <label class="checkbox">
    <input type="checkbox" id="checked-checkbox" checked>
    <div class="checkbox-box"></div>
    <div class="checkbox-label">
      <span class="checkbox-label-text">Checked checkbox</span>
    </div>
  </label>
</div>
```

#### Radio Buttons

```html
<div class="form-group">
  <label class="radio-button">
    <input type="radio" name="radio-group" value="option1" checked>
    <div class="radio-box"></div>
    <div class="radio-label">
      <span class="radio-label-text">Option 1</span>
    </div>
  </label>
</div>

<div class="form-group">
  <label class="radio-button">
    <input type="radio" name="radio-group" value="option2">
    <div class="radio-box"></div>
    <div class="radio-label">
      <span class="radio-label-text">Option 2</span>
    </div>
  </label>
</div>
```

#### Form Grid Layout

For forms with multiple columns, use the grid system:

```html
<div class="form-group">
  <div class="grid grid-cols-2" style="gap: var(--space-4)">
    <div class="text-input">
      <div class="label">
        <label class="label-text" for="first-name">First Name</label>
      </div>
      <div class="content">
        <input type="text" id="first-name" placeholder="Enter first name">
      </div>
    </div>
    <div class="text-input">
      <div class="label">
        <label class="label-text" for="last-name">Last Name</label>
      </div>
      <div class="content">
        <input type="text" id="last-name" placeholder="Enter last name">
      </div>
    </div>
  </div>
</div>
```

#### Form Validation

The design system includes styles for form validation states:

```html
<!-- Error State -->
<div class="form-group">
  <div class="text-input error">
    <div class="label">
      <label class="label-text" for="error-input">Input with Error</label>
    </div>
    <div class="content">
      <input type="text" id="error-input" placeholder="Error field">
    </div>
    <div class="error-message">
      This field is required
    </div>
  </div>
</div>

<!-- Success State -->
<div class="form-group">
  <div class="text-input success">
    <div class="label">
      <label class="label-text" for="success-input">Valid Input</label>
    </div>
    <div class="content">
      <input type="text" id="success-input" value="Correct value">
    </div>
  </div>
</div>
```

#### Form Best Practices

1. **Consistent Structure**: Always use the proper nesting structure for form elements
2. **Proper Spacing**: Use form-group for consistent spacing between elements
3. **Logical Grouping**: Group related form elements together with section headings
4. **Clear Labels**: Always include clear, descriptive labels for all form elements
5. **Validation States**: Use the built-in validation states for error and success feedback
6. **Responsive Layout**: Use the grid system for multi-column forms on larger screens
7. **Accessible Forms**: Include proper for/id attributes to connect labels with inputs
8. **Required Fields**: Use the required class to indicate mandatory fields
9. **Consistent Button Placement**: Place form buttons in the card__footer with proper spacing

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

<!-- Inline Badge (with left margin) -->
<span class="badge badge-success badge-inline">
  <span class="badge-text">Active</span>
</span>
```

#### Badge Variants

- **Default**: Blue badge (no additional class needed)
- **Success**: Green badge with `badge-success` class
- **Warning**: Orange badge with `badge-warning` class
- **Error**: Red badge with `badge-error` class
- **Inline**: Any badge with `badge-inline` class (adds left margin for inline use with text)

#### Badge Usage

- Use badges to indicate status, counts, or labels
- Always use `<span>` elements for badges, not `<div>` elements
- When placing badges inline with text, use the `badge-inline` class instead of inline styles
- For detailed examples, see the [badge-showcase.html](examples/badge-showcase.html) example page

> **Note**: Until dedicated label and tag components are created, the badge component can be used for these purposes. For label-like usage, consider using the default blue badge or the grey badge (`badge-grey`) for a more neutral appearance.

### Banners

Banners are used to display important messages, alerts, or notifications to users. They come in different variants to indicate the type of message.

```html
<!-- Default/Info Banner (with close button) -->
<div class="banner">
    <div class="icon-container icon-small">
        <i class="fas fa-info-circle"></i>
    </div>
    <div class="content">
        <div class="title body-text-medium">Information Message</div>
        <div class="text body-text">This is a standard information banner that provides helpful context to users.</div>
    </div>
    <button class="button-close">
        <div class="icon-container icon-small">
            <i class="fas fa-times"></i>
        </div>
    </button>
</div>

<!-- Warning Banner -->
<div class="banner style-variant-warning">
    <div class="icon-container icon-small">
        <i class="fas fa-exclamation-triangle icon-warning"></i>
    </div>
    <div class="content">
        <div class="title body-text-medium">Warning Alert</div>
        <div class="text body-text">This is a warning banner that alerts users to potential issues.</div>
    </div>
    <button class="button-close">
        <div class="icon-container icon-small">
            <i class="fas fa-times"></i>
        </div>
    </button>
</div>

<!-- Error Banner -->
<div class="banner style-variant-error">
    <div class="icon-container icon-small">
        <i class="fas fa-exclamation-circle icon-error"></i>
    </div>
    <div class="content">
        <div class="title body-text-medium">Error Message</div>
        <div class="text body-text">This is an error banner that indicates a critical issue.</div>
    </div>
    <button class="button-close">
        <div class="icon-container icon-small">
            <i class="fas fa-times"></i>
        </div>
    </button>
</div>

<!-- Success Banner -->
<div class="banner style-variant-success">
    <div class="icon-container icon-small">
        <i class="fas fa-check-circle icon-success"></i>
    </div>
    <div class="content">
        <div class="title body-text-medium">Success Message</div>
        <div class="text body-text">This is a success banner that confirms a completed action.</div>
    </div>
    <button class="button-close">
        <div class="icon-container icon-small">
            <i class="fas fa-times"></i>
        </div>
    </button>
</div>
```

#### Banner Styling

Each banner variant uses specific colors for background and border:

- **Info (blue)**: Background `var(--secondary-blue-100)`, Border `var(--secondary-blue-200)`
- **Warning (orange)**: Background `var(--warning-orange-100)`, Border `var(--warning-orange-200)`
- **Error (red)**: Background `var(--error-red-100)`, Border `var(--error-red-200)`
- **Success (green)**: Background `var(--success-green-100)`, Border `var(--success-green-200)`

All banners use a 1px border with the 200 shade of their respective color and have a 12px gap between the title and text.

#### Persistent Banners (Without Close Button)

For messages that should remain visible and cannot be dismissed, simply omit the close button element:

```html
<!-- Persistent Warning Banner (without close button) -->
<div class="banner style-variant-warning">
    <div class="icon-container icon-small">
        <i class="fas fa-exclamation-triangle icon-warning"></i>
    </div>
    <div class="content">
        <div class="title body-text-medium">Persistent Warning</div>
        <div class="text body-text">This is a warning banner without a close button for messages that should remain visible.</div>
    </div>
</div>
```

#### Banner Structure

Each banner consists of:
1. An icon that indicates the type of message (in an `icon-container`)
2. Content with a title (`body-text-medium` class) and descriptive text (`body-text` class)
3. An optional close button with properly structured icon container

#### Typography Classes

- **Banner Title**: Always add the `body-text-medium` class to the `.title` element
- **Banner Text**: Always add the `body-text` class to the `.text` element
- These classes provide the correct typography styling as the CSS handles only layout properties

#### Best Practices

- Use banners sparingly to avoid overwhelming users
- Choose the appropriate variant based on the message importance:
  - **Info (blue)**: General information, tips, or context
  - **Warning (orange)**: Potential issues that require attention
  - **Error (red)**: Critical issues that need immediate attention
  - **Success (green)**: Confirmation of completed actions
- Keep messages clear and concise
- Use persistent banners only for information that must remain visible
- Always include the proper typography classes for title and text
- Wrap close button icons in an icon-container

For a complete showcase of all banner variants, see the [banner-examples.html](examples/banner-examples.html) example page.

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
- `icon-medium`: 24x24px container with 20x20px icon
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
2. Always specify the size (`icon-small`, `icon-large`, or `icon-medium`)
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
- ✅ Always apply typography classes to component text elements
- ✅ Combine component classes with typography classes (e.g., `<div class="title body-text-medium">`)
- ❌ Don't mix typography classes incorrectly
- ❌ Don't skip small-body-text for subtitles
- ❌ Don't use raw font-size or font-weight values
- ❌ Don't create components with text elements missing typography classes
- ❌ Don't define typography properties in component CSS (use typography classes instead)

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

## Support and Contributing

### Support & Documentation
1. Check the example pages in the `examples/` directory:
   - `login-register.html`: Authentication forms with validation
   - `people-management.html`: User management interface
   - `transportation-dashboard.html`: Data dashboard layout with proper card grid implementation
2. Review component usage in the example pages
3. Follow BEM naming conventions
4. Use the design tokens consistently

### Contributing
1. Follow the code quality standards
2. Test across different browsers
3. Ensure accessibility compliance
4. Document any new components
5. Update example pages as needed 