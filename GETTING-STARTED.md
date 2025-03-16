# Getting Started with Keboola Design System

## Installation

### 1. Add Required Dependencies

Include these dependencies in your HTML file:

```html
<!-- Required Dependencies -->
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" rel="stylesheet">
<link href="dist/design-system.css" rel="stylesheet">
```

### 2. Set Up Basic HTML Structure

Every page should follow this basic structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Keboola App</title>
    
    <!-- Preload critical fonts for performance -->
    <link rel="preload" href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" as="style">
    
    <!-- Required Dependencies -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" rel="stylesheet">
    <link href="dist/design-system.css" rel="stylesheet">
    
    <!-- REQUIRED: Base font styles -->
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: var(--font-family-base);
            background-color: var(--neutral-grey-50);
            color: var(--neutral-grey-800);
            line-height: var(--body-body-line-height);
        }
    </style>
</head>
<body class="bg-grey-50">
    <div class="container page-container" style="padding: var(--space-16)">
        <div class="content-wrapper" style="display: flex; flex-direction: column; gap: var(--space-6)">
            <header class="header">
                <h1 class="header__title heading-1">Page Title</h1>
            </header>
            
            <section class="section">
                <!-- Your content here -->
            </section>
        </div>
    </div>
</body>
</html>
```

> ⚠️ **Important**: Both the font preloading and base font styles are required for all pages. Omitting either will result in inconsistent typography and performance issues.

## Quick Start Examples

### Creating a Simple Dashboard

```html
<div class="content-wrapper" style="display: flex; flex-direction: column; gap: var(--space-6)">
    <!-- Header with actions -->
    <header class="header">
        <h1 class="header__title heading-1">Dashboard</h1>
        <div class="header__actions">
            <button class="btn btn-secondary btn-medium">
                <div class="btn-icon">
                    <i class="fas fa-download icon-muted"></i>
                </div>
                <span class="btn-text">EXPORT</span>
            </button>
            <button class="btn btn-primary btn-medium">
                <div class="btn-icon">
                    <i class="fas fa-plus text-white"></i>
                </div>
                <span class="btn-text">ADD NEW</span>
            </button>
        </div>
    </header>

    <!-- Overview cards section -->
    <section class="section">
        <div class="grid grid-cols-4" style="gap: var(--space-4)">
            <!-- Overview card 1 -->
            <div class="overview-card bg-white">
                <div class="overview-card__header">
                    <span class="overview-card__title">Total Users</span>
                    <span class="badge badge-success">
                        <span class="badge-text">+5.2%</span>
                    </span>
                </div>
                <div class="overview-card__value">1,245</div>
                <div class="overview-card__subtitle">+12 this month</div>
            </div>
            
            <!-- Overview card 2 -->
            <div class="overview-card bg-white">
                <div class="overview-card__header">
                    <span class="overview-card__title">Active Projects</span>
                </div>
                <div class="overview-card__value">37</div>
                <div class="overview-card__subtitle">3 added recently</div>
            </div>
            
            <!-- Add more overview cards as needed -->
        </div>
    </section>

    <!-- Content section with warning banner -->
    <section class="section">
        <!-- Warning Banner -->
        <div class="banner style-variant-warning">
            <div class="icon-container icon-small">
                <i class="fas fa-exclamation-triangle icon-warning"></i>
            </div>
            <div class="content">
                <div class="title">Maintenance Alert</div>
                <div class="text">Scheduled maintenance will occur on March 20th. Some services may be unavailable.</div>
            </div>
            <button class="button-close">
                <i class="fas fa-times icon-small"></i>
            </button>
        </div>
    </section>

    <!-- Activity section -->
    <section class="section">
        <div class="card bg-white">
            <h2 class="card__title">Recent Activity</h2>
            <div class="card__content">
                <!-- Activity row 1 -->
                <div class="activity-row">
                    <div class="activity-row__content">
                        <div class="icon-container icon-small">
                            <i class="fas fa-check-circle icon-success"></i>
                        </div>
                        <span class="activity-row__text">User John Doe logged in</span>
                    </div>
                    <div class="activity-row__meta">
                        <span class="small-body-text">2 hours ago</span>
                    </div>
                </div>
                
                <!-- Activity row 2 -->
                <div class="activity-row">
                    <div class="activity-row__content">
                        <div class="icon-container icon-small">
                            <i class="fas fa-file-alt icon-muted"></i>
                        </div>
                        <span class="activity-row__text">Report generated successfully</span>
                    </div>
                    <div class="activity-row__meta">
                        <span class="small-body-text">Yesterday</span>
                    </div>
                </div>
                
                <!-- Add more activity rows as needed -->
            </div>
        </div>
    </section>
</div>
```

### Creating a Simple Form

```html
<div class="content-wrapper" style="display: flex; flex-direction: column; gap: var(--space-6)">
    <header class="header">
        <h1 class="header__title heading-1">Create New Item</h1>
    </header>

    <section class="section">
        <div class="card bg-white">
            <h2 class="card__title">Item Details</h2>
            <div class="card__content" style="display: flex; flex-direction: column; gap: var(--space-4)">
                <!-- Text input -->
                <div class="form-group">
                    <div class="text-input required">
                        <div class="label">
                            <label class="label-text" for="item-name">Name</label>
                        </div>
                        <div class="content">
                            <input type="text" id="item-name" placeholder="Enter item name">
                        </div>
                    </div>
                </div>
                
                <!-- Select input -->
                <div class="form-group">
                    <div class="select">
                        <div class="label">
                            <label class="label-text" for="item-category">Category</label>
                        </div>
                        <div class="select-wrapper">
                            <select id="item-category" class="select-trigger">
                                <option value="">Select a category</option>
                                <option value="category1">Category 1</option>
                                <option value="category2">Category 2</option>
                                <option value="category3">Category 3</option>
                            </select>
                        </div>
                    </div>
                </div>
                
                <!-- Textarea -->
                <div class="form-group">
                    <div class="text-input">
                        <div class="label">
                            <label class="label-text" for="item-description">Description</label>
                        </div>
                        <div class="content">
                            <textarea id="item-description" rows="3" placeholder="Enter item description"></textarea>
                        </div>
                    </div>
                </div>
                
                <!-- Checkbox -->
                <div class="form-group">
                    <label class="checkbox">
                        <input type="checkbox" id="item-active">
                        <div class="checkbox-box"></div>
                        <div class="checkbox-label">
                            <span class="checkbox-label-text">Make this item active</span>
                        </div>
                    </label>
                </div>
            </div>
            
            <div class="card__footer">
                <button class="btn btn-secondary btn-medium">
                    <span class="btn-text">CANCEL</span>
                </button>
                <button class="btn btn-primary btn-medium">
                    <span class="btn-text">SAVE</span>
                </button>
            </div>
        </div>
    </section>
</div>
```

## Creating a Tabbed Interface

```html
<div class="content-wrapper" style="display: flex; flex-direction: column; gap: var(--space-6)">
    <header class="header">
        <h1 class="header__title heading-1">Settings</h1>
    </header>

    <!-- Tabs navigation -->
    <div class="tabs tabs-large">
        <div class="tab-item active">
            <div class="tab-content">
                <div class="icon-container icon-small">
                    <i class="fas fa-user"></i>
                </div>
                <div class="tab-text">Profile</div>
            </div>
            <div class="tab-active-line"></div>
        </div>
        
        <div class="tab-item">
            <div class="tab-content">
                <div class="icon-container icon-small">
                    <i class="fas fa-bell"></i>
                </div>
                <div class="tab-text">Notifications</div>
            </div>
            <div class="tab-active-line"></div>
        </div>
        
        <div class="tab-item">
            <div class="tab-content">
                <div class="icon-container icon-small">
                    <i class="fas fa-shield-alt"></i>
                </div>
                <div class="tab-text">Security</div>
            </div>
            <div class="tab-active-line"></div>
        </div>
    </div>

    <!-- Tab content -->
    <section class="section">
        <div class="card bg-white">
            <h2 class="card__title">Profile Information</h2>
            <div class="card__content" style="display: flex; flex-direction: column; gap: var(--space-4)">
                <!-- Form content here -->
                <div class="form-group">
                    <div class="grid grid-cols-2" style="gap: var(--space-4)">
                        <div class="text-input">
                            <div class="label">
                                <label class="label-text" for="first-name">First Name</label>
                            </div>
                            <div class="content">
                                <input type="text" id="first-name" value="John">
                            </div>
                        </div>
                        <div class="text-input">
                            <div class="label">
                                <label class="label-text" for="last-name">Last Name</label>
                            </div>
                            <div class="content">
                                <input type="text" id="last-name" value="Doe">
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="form-group">
                    <div class="text-input">
                        <div class="label">
                            <label class="label-text" for="email">Email</label>
                        </div>
                        <div class="content">
                            <input type="email" id="email" value="john.doe@example.com">
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="card__footer">
                <button class="btn btn-primary btn-medium">
                    <span class="btn-text">SAVE CHANGES</span>
                </button>
            </div>
        </div>
    </section>
</div>
```

## Core Principles

When using the Keboola Design System, follow these core principles:

1. **Use the gap-based spacing approach** - Use parent container's gap property for spacing between elements instead of margins
2. **Follow the component hierarchy** - Maintain proper nesting and class structure for all components
3. **Use design tokens consistently** - Always use CSS variables for colors, spacing, typography, etc.
4. **Maintain proper typography** - Use the provided typography classes and font stack with fallbacks
5. **Keep components accessible** - Ensure proper contrast, focus states, and semantic HTML
6. **Use consistent icon implementation** - Always wrap icons in icon-container with proper size classes
7. **Follow form element structure** - Use the proper nesting structure for all form elements
8. **Use proper banner variants** - Choose the appropriate banner type based on the message importance

## Common Patterns

### Header with Actions

```html
<header class="header">
    <h1 class="header__title heading-1">Page Title</h1>
    <div class="header__actions">
        <!-- Secondary buttons first -->
        <button class="btn btn-secondary btn-medium">
            <span class="btn-text">CANCEL</span>
        </button>
        <!-- Primary button last -->
        <button class="btn btn-primary btn-medium">
            <span class="btn-text">SAVE</span>
        </button>
    </div>
</header>
```

### Card with Form

```html
<div class="card bg-white">
    <h2 class="card__title">Form Title</h2>
    <div class="card__content" style="display: flex; flex-direction: column; gap: var(--space-4);">
        <div class="form-group">
            <!-- Form element -->
        </div>
    </div>
    <div class="card__footer">
        <button class="btn btn-primary btn-medium">
            <span class="btn-text">SUBMIT</span>
        </button>
    </div>
</div>
```

### Empty State

```html
<div style="display: flex; flex-direction: column; align-items: center; justify-content: center; padding: var(--space-16); text-align: center;">
    <div class="icon-container icon-large" style="margin-bottom: var(--space-4);">
        <i class="fas fa-chart-line icon-muted"></i>
    </div>
    <h3 class="heading-3" style="margin-bottom: var(--space-2);">No Data Available</h3>
    <p class="body-text" style="margin-bottom: var(--space-4);">There is no data to display at this time.</p>
    <button class="btn btn-primary btn-medium">
        <span class="btn-text">ADD DATA</span>
    </button>
</div>
```

### Banner Notifications

```html
<!-- Info Banner -->
<div class="banner">
    <div class="icon-container icon-small">
        <i class="fas fa-info-circle"></i>
    </div>
    <div class="content">
        <div class="title">Information Message</div>
        <div class="text">This is a standard information banner that provides helpful context to users.</div>
    </div>
    <button class="button-close">
        <i class="fas fa-times icon-small"></i>
    </button>
</div>

<!-- Warning Banner (Persistent) -->
<div class="banner style-variant-warning style-variant-persistent">
    <div class="icon-container icon-small">
        <i class="fas fa-exclamation-triangle icon-warning"></i>
    </div>
    <div class="content">
        <div class="title">Persistent Warning</div>
        <div class="text">This is a warning banner without a close button for messages that should remain visible.</div>
    </div>
</div>
```

Remember to check the [README.md](README.md) file for comprehensive documentation on all components and patterns available in the Keboola Design System.

## Next Steps

1. Explore the real-world example pages in the `examples/` directory:
   - `login-register.html`: Authentication forms with validation
   - `car-dashboard.html`: Vehicle fleet management dashboard
   - `transportation-dashboard.html`: Transportation data visualization
   - `people-management.html`: User management interface
   - `bitcoin-dashboard.html`: Cryptocurrency dashboard
   - `overview-card-demo.html`: Card component showcase

2. Review the component documentation for detailed usage guidelines

3. Check out the design tokens for colors, spacing, and typography

## Real-World Examples

The examples directory contains several complete, production-ready interfaces that demonstrate how to implement the design system in real applications:

### Authentication Pages

The `login-register.html` example demonstrates:
- Centered authentication layout
- Form validation with error states
- Tab-based navigation between login and registration
- Password strength indicators
- Responsive design for mobile and desktop

### Data Dashboards

The dashboard examples (`car-dashboard.html`, `transportation-dashboard.html`, and `bitcoin-dashboard.html`) showcase:
- Overview cards with metrics and trends
- Data tables with sorting and filtering
- Interactive charts and visualizations
- Warning banners and notifications
- Tab-based navigation between dashboard sections

### Management Interfaces

The `people-management.html` example demonstrates:
- Data tables with user information
- Filtering and search functionality
- Status indicators and badges
- Modal dialogs for editing and creating records
- Responsive layout for different screen sizes

For more detailed information, refer to the full documentation sections in the README. 