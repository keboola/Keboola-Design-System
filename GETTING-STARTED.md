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
    
    <!-- Required Dependencies -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" rel="stylesheet">
    <link href="dist/design-system.css" rel="stylesheet">
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

## Quick Start Examples

### Creating a Simple Dashboard

```html
<div class="content-wrapper" style="display: flex; flex-direction: column; gap: var(--space-6)">
    <!-- Header with actions -->
    <header class="header">
        <h1 class="header__title heading-1">Dashboard</h1>
        <div class="header__actions">
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
                        <span class="badge-text">Active</span>
                    </span>
                </div>
                <div class="overview-card__value">1,245</div>
                <div class="overview-card__subtitle">+12% from last month</div>
            </div>
            
            <!-- Add more overview cards as needed -->
        </div>
    </section>

    <!-- Content section -->
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
                    <div class="text-input">
                        <div class="label">
                            <label class="label-text" for="item-name">Name</label>
                        </div>
                        <div class="content">
                            <input type="text" id="item-name" placeholder="Enter item name">
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
                        <input type="checkbox">
                        <div class="checkbox-box"></div>
                        <div class="checkbox-label">
                            <span class="checkbox-label-text">Make this item active</span>
                        </div>
                    </label>
                </div>
            </div>
            
            <div class="card__footer" style="margin-top: var(--space-6)">
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
            </div>
        </div>
    </section>
</div>
```

## Core Principles

When using the Keboola Design System, follow these core principles:

1. **Use the gap-based spacing approach** - Use parent container's gap property for spacing between elements
2. **Follow the component hierarchy** - Maintain proper nesting and class structure
3. **Use design tokens consistently** - Always use CSS variables for colors, spacing, etc.
4. **Maintain proper typography** - Use the provided typography classes
5. **Keep components accessible** - Ensure proper contrast, focus states, and semantic HTML

## Common Patterns

### Header with Actions

```html
<header class="header">
    <h1 class="header__title heading-1">Page Title</h1>
    <div class="header__actions">
        <button class="btn btn-secondary btn-medium">
            <span class="btn-text">CANCEL</span>
        </button>
        <button class="btn btn-primary btn-medium">
            <span class="btn-text">SAVE</span>
        </button>
    </div>
</header>
```

### Card with Footer Actions

```html
<div class="card bg-white">
    <h2 class="card__title">Card Title</h2>
    <div class="card__content">
        <!-- Card content here -->
    </div>
    <div class="card__footer" style="margin-top: var(--space-6)">
        <button class="btn btn-secondary btn-medium">
            <span class="btn-text">CANCEL</span>
        </button>
        <button class="btn btn-primary btn-medium">
            <span class="btn-text">SAVE</span>
        </button>
    </div>
</div>
```

### Empty State

```html
<div style="display: flex; align-items: center; justify-content: center; padding: var(--space-12) 0;">
    <div style="display: flex; align-items: center; gap: var(--space-3); flex-direction: column; text-align: center;">
        <div class="icon-container icon-large">
            <i class="fas fa-chart-line icon-muted"></i>
        </div>
        <span class="body-text-medium">No data available</span>
        <button class="btn btn-primary btn-medium" style="margin-top: var(--space-4)">
            <span class="btn-text">ADD DATA</span>
        </button>
    </div>
</div>
```

## Next Steps

1. Explore the example pages in the `examples/` directory:
   - `login-register.html`: Authentication forms with validation
   - `people-management.html`: User management interface
   - `transportation-dashboard.html`: Data dashboard layout

2. Review the component documentation for detailed usage guidelines

3. Check out the design tokens for colors, spacing, and typography

For more detailed information, refer to the full documentation sections in the README. 