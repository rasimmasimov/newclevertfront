# Tailux Design System Implementation

This project now uses the complete Tailux design system for consistent styling across all frontend pages.

## 🎨 What's Been Implemented

### 1. **Complete Tailux Design System** (`src/styles/tailux-design-system.scss`)
- **Color Palette**: Primary blue theme, comprehensive gray scale, dark mode support
- **Typography**: Font scales, weights, and line heights
- **Spacing**: Consistent spacing tokens (1-96 scale)
- **Components**: Form inputs, buttons, cards, layout utilities
- **Responsive Design**: Mobile-first approach with proper touch targets
- **Accessibility**: Focus states, proper contrast ratios

### 2. **Updated Login Page** 
- **Exact Tailux Layout**: Matches the original Tailux login template
- **Proper Sizing**: 26rem max-width container with correct padding
- **Color Scheme**: Uses official Tailux color tokens
- **Responsive**: Optimized for mobile and desktop
- **Accessibility**: Proper focus states and touch targets

### 3. **Updated Signup Page**
- **Consistent Design**: Matches login page styling
- **Same Layout Structure**: Uses identical Tailux components

## 🚀 How to Use the Design System

### Available CSS Classes

#### Layout & Sizing
```html
<div class="min-h-screen grid place-items-center">
  <div class="w-full max-w-[26rem] p-4 sm:px-5">
    <!-- Content -->
  </div>
</div>
```

#### Form Components
```html
<!-- Input Field -->
<div class="input-root">
  <label class="input-label">Email</label>
  <div class="input-wrapper relative mt-1.5">
    <input class="form-input-base ltr:pl-9 form-input" />
    <div class="prefix ltr:left-0">
      <!-- Icon -->
    </div>
  </div>
</div>

<!-- Checkbox -->
<input class="form-checkbox this:primary" type="checkbox">

<!-- Button -->
<button class="btn-base btn this:primary bg-this text-white hover:bg-this-darker">
  Sign In
</button>
```

#### Card Component
```html
<div class="card rounded-lg border border-gray-200 dark:border-dark-600 p-5 lg:p-7">
  <!-- Card content -->
</div>
```

#### Colors
```html
<!-- Text Colors -->
<p class="text-gray-600 dark:text-dark-100">Content</p>
<p class="text-primary-600">Primary text</p>

<!-- Background Colors -->
<div class="bg-gray-50">Background</div>
<div class="bg-white dark:bg-dark-100">Card background</div>
```

## 🎯 Design Tokens

### Color System
- **Primary**: Blue scale (primary-50 to primary-950)
- **Gray**: Slate scale (gray-50 to gray-950)  
- **Dark**: Cinder scale (dark-50 to dark-950)
- **Semantic**: Success, error, warning, info variants

### Spacing Scale
- **Small**: 1-4 (0.25rem - 1rem)
- **Medium**: 5-12 (1.25rem - 3rem)
- **Large**: 16-96 (4rem - 24rem)

### Typography Scale
- **Sizes**: xs, sm, base, lg, xl, 2xl, 3xl, 4xl, 5xl, 6xl
- **Weights**: 400 (normal), 500 (medium), 600 (semibold)

## 📱 Responsive Design

The system follows a mobile-first approach:

```scss
// Mobile (default)
.btn-base { min-height: 2.5rem; }

// Mobile optimization
@media (max-width: 640px) {
  .btn-base { 
    min-height: 3rem; // Larger touch targets
    font-size: 1rem; // Prevent zoom on inputs
  }
}

// Tablet and up
@media (min-width: 640px) {
  .sm\:px-5 { padding-left: 1.25rem; }
}
```

## 🌙 Dark Mode Support

Dark mode is fully supported with automatic color switching:

```html
<html class="dark">
  <!-- All components automatically switch to dark variants -->
</html>
```

## ♿ Accessibility Features

- **Focus States**: Visible focus indicators on all interactive elements
- **Touch Targets**: Minimum 44px (48px on mobile) for buttons
- **Color Contrast**: WCAG AA compliant color combinations
- **Reduced Motion**: Respects `prefers-reduced-motion` setting

## 🔧 Extending the System

### Adding New Components
1. Create component-specific SCSS files
2. Use existing design tokens
3. Follow the established patterns

Example:
```scss
.my-component {
  background-color: var(--card-bg);
  border: 1px solid var(--card-border);
  border-radius: var(--card-radius);
  padding: var(--card-padding);
  box-shadow: var(--card-shadow);
}
```

### Customizing Colors
Modify the CSS custom properties in `tailux-design-system.scss`:

```scss
:root {
  --color-primary-600: #your-brand-color;
  --color-primary-700: #your-brand-color-darker;
}
```

## 🚨 Important Notes

1. **Global Import**: The design system is globally imported in `styles.scss`
2. **Component Styles**: Individual components should only contain overrides
3. **Consistency**: Always use design tokens instead of hardcoded values
4. **Mobile First**: Design for mobile first, then enhance for larger screens
5. **Dark Mode**: Test all components in both light and dark modes

## 📋 Checklist for New Pages

When creating new pages, ensure:

- [ ] Use Tailux layout classes (`min-h-screen`, `grid`, `place-items-center`)
- [ ] Apply proper container sizing (`max-w-[26rem]`)
- [ ] Use design system colors (`text-gray-600`, `bg-gray-50`)
- [ ] Implement proper spacing (`p-4`, `sm:px-5`, `mt-4`)
- [ ] Add dark mode support (`dark:text-dark-100`)
- [ ] Test responsive behavior on mobile
- [ ] Verify accessibility (focus states, touch targets)
- [ ] Test with dark mode enabled

This design system ensures visual consistency, excellent user experience, and maintainable code across the entire Clevert frontend application.
