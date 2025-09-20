# Apply Tailux Design System to All Frontend Pages

This guide provides templates and patterns for applying the Tailux design system to all remaining pages in the Clevert frontend application.

## 🎯 Pages Updated So Far

✅ **Login & Signup** - Complete Tailux implementation  
✅ **Admin Dashboard** - Complete Tailux implementation  
✅ **User Profile** - Complete Tailux implementation  
✅ **User Management** - Complete Tailux implementation  
✅ **My Advertisements** - Complete Tailux implementation  

## 📋 Remaining Pages to Update

### Admin Pages
- [ ] User Settings (`src/app/admin/views/user-settings/`)
- [ ] Permission Management (`src/app/admin/views/permission-management/`)
  - [ ] User Groups
  - [ ] User Roles  
  - [ ] Approval Requests

### Advertisement Pages
- [ ] New Advertisement (`projects/module-lib/src/lib/advertisement/views/new-advertisement/`)
- [ ] All Advertisements (`projects/module-lib/src/lib/advertisement/views/advertisements/`)

### Payment Pages
- [ ] Transactions (`projects/module-lib/src/lib/payment/views/transactions/`)
- [ ] Earnings (`projects/module-lib/src/lib/payment/views/earnings/`)
- [ ] Top Up (`projects/module-lib/src/lib/payment/views/top-up/`)
- [ ] Spendings (`projects/module-lib/src/lib/payment/views/spendings/`)
- [ ] Send Money (`projects/module-lib/src/lib/payment/views/send-money/`)

### Config Pages
- [ ] Users (`projects/module-lib/src/lib/config/views/users/`)
- [ ] New User (`projects/module-lib/src/lib/config/views/new-user/`)

### Layout Components
- [ ] Navbar (`src/app/admin/layouts/navbar/`)
- [ ] Sidebar (`src/app/admin/layouts/side-bar/`)
- [ ] Footer (`src/app/admin/layouts/footer/`)
- [ ] Customizer (`src/app/admin/layouts/customizer/`)

### Shared Components
- [ ] Breadcrumb (`projects/module-lib/src/lib/shared/components/bread-crumb/`)
- [ ] Tree View (`projects/module-lib/src/lib/shared/components/tree-view-ex/`)
- [ ] Showed Entries Dropdown (`projects/module-lib/src/lib/shared/components/showed-entries-dropdown/`)

## 🎨 Standard Page Template

Use this template as the foundation for all pages:

```html
<!-- Page Name - Tailux Design System -->
<div class="w-full">
  <!-- Page Header -->
  <div class="mb-8">
    <div class="flex flex-col sm:flex-row sm:items-center sm:justify-between gap-4">
      <div>
        <h1 class="text-2xl font-semibold text-gray-900 dark:text-dark-100 flex items-center gap-2">
          <i class="fas fa-icon text-primary-600"></i>
          Page Title
        </h1>
        <p class="text-gray-600 dark:text-dark-300 mt-1">Page description goes here</p>
      </div>
      <div class="flex gap-3">
        <!-- Action buttons -->
        <button class="btn-base btn this:primary bg-this text-white hover:bg-this-darker">
          <i class="fas fa-plus"></i>
          Primary Action
        </button>
      </div>
    </div>
  </div>

  <!-- Page Content -->
  <div class="space-y-6">
    <!-- Cards, forms, tables, etc. -->
  </div>
</div>
```

## 🧩 Component Patterns

### 1. Card Component
```html
<div class="card rounded-lg border border-gray-200 dark:border-dark-600">
  <div class="px-6 py-4 border-b border-gray-200 dark:border-dark-600">
    <h3 class="text-lg font-medium text-gray-900 dark:text-dark-100">Card Title</h3>
  </div>
  <div class="p-6">
    <!-- Card content -->
  </div>
</div>
```

### 2. Form Input
```html
<div class="input-root">
  <label class="input-label">Label</label>
  <div class="input-wrapper relative mt-1.5">
    <input class="form-input-base ltr:pl-9 form-input" 
           type="text" 
           placeholder="Placeholder">
    <div class="prefix ltr:left-0">
      <i class="fas fa-icon text-gray-400"></i>
    </div>
  </div>
</div>
```

### 3. Button Styles
```html
<!-- Primary Button -->
<button class="btn-base btn this:primary bg-this text-white hover:bg-this-darker">
  <i class="fas fa-icon"></i>
  Primary Action
</button>

<!-- Secondary Button -->
<button class="btn-base btn border border-gray-300 hover:bg-gray-300/20 text-gray-900 dark:text-dark-50 dark:border-dark-450">
  <i class="fas fa-icon"></i>
  Secondary Action
</button>
```

### 4. Table Structure
```html
<div class="card rounded-lg border border-gray-200 dark:border-dark-600 overflow-hidden">
  <div class="overflow-x-auto">
    <table class="w-full">
      <thead class="bg-gray-50 dark:bg-dark-800">
        <tr>
          <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 dark:text-dark-300 uppercase tracking-wider">
            Column Header
          </th>
        </tr>
      </thead>
      <tbody class="bg-white dark:bg-dark-100 divide-y divide-gray-200 dark:divide-dark-600">
        <tr class="hover:bg-gray-50 dark:hover:bg-dark-700 transition-colors">
          <td class="px-6 py-4 text-sm text-gray-900 dark:text-dark-100">
            Cell content
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</div>
```

### 5. Stats Cards
```html
<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
  <div class="card rounded-lg border border-gray-200 dark:border-dark-600 p-6">
    <div class="flex items-center">
      <div class="flex-shrink-0">
        <div class="w-8 h-8 bg-blue-100 dark:bg-blue-900 rounded-lg flex items-center justify-center">
          <i class="fas fa-icon text-blue-600 dark:text-blue-400"></i>
        </div>
      </div>
      <div class="ml-4">
        <p class="text-sm font-medium text-gray-600 dark:text-dark-300">Label</p>
        <p class="text-2xl font-semibold text-gray-900 dark:text-dark-100">Value</p>
      </div>
    </div>
  </div>
</div>
```

### 6. Filter Section
```html
<div class="mb-6" *ngIf="showFilters">
  <div class="card rounded-lg border border-gray-200 dark:border-dark-600 p-6">
    <form class="grid grid-cols-1 md:grid-cols-3 gap-4">
      <!-- Filter inputs here -->
      <div class="flex gap-3 col-span-full">
        <button type="button" class="btn-base btn this:primary bg-this text-white hover:bg-this-darker">
          Apply Filters
        </button>
        <button type="button" class="btn-base btn border border-gray-300 hover:bg-gray-300/20">
          Clear
        </button>
      </div>
    </form>
  </div>
</div>
```

### 7. Empty State
```html
<div class="text-center py-12">
  <div class="flex flex-col items-center">
    <i class="fas fa-icon text-gray-400 text-6xl mb-4"></i>
    <h3 class="text-xl font-medium text-gray-900 dark:text-dark-100 mb-2">No items found</h3>
    <p class="text-gray-500 dark:text-dark-300 mb-6 max-w-md">
      Description of empty state
    </p>
    <button class="btn-base btn this:primary bg-this text-white hover:bg-this-darker">
      <i class="fas fa-plus"></i>
      Create First Item
    </button>
  </div>
</div>
```

## 🎨 Color Guidelines

### Status Colors
- **Success**: `bg-green-100 text-green-800 dark:bg-green-900 dark:text-green-200`
- **Warning**: `bg-yellow-100 text-yellow-800 dark:bg-yellow-900 dark:text-yellow-200`  
- **Error**: `bg-red-100 text-red-800 dark:bg-red-900 dark:text-red-200`
- **Info**: `bg-blue-100 text-blue-800 dark:bg-blue-900 dark:text-blue-200`

### Icon Colors
- **Primary**: `text-primary-600 dark:text-primary-400`
- **Success**: `text-green-600 dark:text-green-400`
- **Warning**: `text-yellow-600 dark:text-yellow-400`
- **Error**: `text-red-600 dark:text-red-400`
- **Neutral**: `text-gray-400 dark:text-dark-300`

## 📱 Responsive Guidelines

### Grid Breakpoints
- **Mobile**: `grid-cols-1`
- **Tablet**: `md:grid-cols-2` 
- **Desktop**: `lg:grid-cols-3` or `lg:grid-cols-4`

### Text Sizing
- **Page Title**: `text-2xl`
- **Section Title**: `text-lg` 
- **Card Title**: `text-lg font-medium`
- **Body Text**: `text-sm`
- **Caption**: `text-xs`

### Button Sizing
- **Default**: `btn-base btn`
- **Small**: `!px-2 !py-1 !text-xs`
- **Large**: `!px-6 !py-3 !text-base`

## 🚀 Quick Start Steps

For each page you're updating:

1. **Replace container structure** with Tailux layout
2. **Update page header** using the standard template
3. **Convert forms** to use Tailux input components
4. **Update buttons** to use Tailux button classes
5. **Modernize tables** with Tailux table structure
6. **Add responsive classes** for mobile optimization
7. **Test dark mode** compatibility

## 🔧 Component-Specific SCSS

Create minimal SCSS files for each component:

```scss
// Component-specific overrides only
:host {
  display: block;
  width: 100%;
  height: 100%;
}

// Custom component styles here
// Avoid duplicating Tailux system styles
```

## ✅ Checklist for Each Page

- [ ] Page header with title and description
- [ ] Proper card layout structure  
- [ ] Tailux form inputs with icons
- [ ] Consistent button styling
- [ ] Responsive grid layout
- [ ] Dark mode support
- [ ] Empty state handling
- [ ] Loading state (if applicable)
- [ ] Error state handling
- [ ] Mobile-friendly touch targets
- [ ] Accessibility (focus states, ARIA labels)

This systematic approach ensures consistent design across all pages while maintaining the high-quality Tailux aesthetic.
