# Kalamata Baked Olives - AI Coding Instructions

## Project Overview
This is a static HTML/CSS website for Kalamata Baked Olives, a Greek food product. The site uses a **component-based HTML architecture** with standalone component files, custom CSS variables, and Parcel for bundling.

## Architecture & File Structure

### Component System
- **Standalone Components**: Each component in `/components/` is a complete HTML file with its own CSS
  - `header.html` + `header.css` - Navigation and site header
  - `banner.html` + `banner.css` - Hero section with product imagery  
  - `feature-card.html` + `feature-card.css` - Product feature highlights
  - `question1.html` + `question1.css` - FAQ/informational sections
- **Component Independence**: Components are self-contained with embedded styles and can be viewed standalone
- **Cross-References**: Components link to `../style.css` for shared design tokens

### Page Structure
- **Main Pages**: `index.html`, `products.html`, `404.html` each with corresponding CSS files
- **Shared Styles**: `style.css` contains CSS custom properties (design tokens) and utility classes
- **Page-Specific**: `index.css`, `products.css`, `404.css` contain page-specific component styles

### CSS Architecture
```css
/* Design tokens defined in style.css */
:root {
  --dl-color-custom-primary1: #35452B;
  --dl-color-custom-accent1: #C7B090;
  --dl-space-space-unit: 16px;
  /* ... extensive design system */
}
```

## Development Patterns

### CSS Naming Convention
- **BEM-style**: `.home-container`, `.feature-card-text`, `.question1-container`
- **Component Prefix**: Each component uses its filename as CSS class prefix
- **Responsive**: Media queries at `767px` and `479px` breakpoints

### Asset Management
- **Images**: Product photos in `/public/` with WebP + PNG fallbacks
- **Naming**: Descriptive filenames like `kalamata_baked_olives_-01-500h.webp`
- **External Assets**: Uses CloudImg CDN for some images and external font/script CDNs

### HTML Structure
- **Inline Styles**: Reset and default styles embedded in `<head>`
- **External Dependencies**: 
  - Animate.css for animations
  - Google Fonts (Inter, Cabin)
  - TeleportHQ custom scripts
- **Meta Tags**: Comprehensive SEO and social media meta tags on every page

## Development Workflow

### Build System
- **Bundler**: Parcel v1.6.1 (legacy version) - configured but no npm scripts defined
- **Static Serving**: Files can be served directly (no build step required for development)

### Adding New Components
1. Create `component-name.html` and `component-name.css` in `/components/`
2. Include full HTML document structure with shared meta tags
3. Link to `../style.css` for design tokens
4. Use component name as CSS class prefix (e.g., `.component-name-container`)

### Styling Guidelines
- **Custom Properties**: Always use CSS variables from `style.css` for colors, spacing, and sizes
- **Responsive Design**: Include mobile breakpoints at `767px` and `479px`
- **Component Isolation**: Keep component styles in dedicated CSS files

### Common Patterns
- **Button Styling**: Use `.button` utility class from `style.css`
- **Layout**: Flexbox-based layouts with CSS Grid for complex sections
- **Images**: Always provide WebP + fallback format with descriptive alt text

## Key Files for Context
- `style.css` - Design system and utility classes
- `index.html` - Homepage structure and main navigation
- `components/header.html` - Site navigation pattern
- `package.json` - Dependencies and potential build scripts