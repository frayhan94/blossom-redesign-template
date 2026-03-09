# Kali Dogwear Theme

A custom Shopify theme based on Dawn, featuring sustainable dog products with a focus on eco-friendly materials and Bali-inspired design.

## 🐾 About Kali Dogwear

Kali Dogwear creates sustainable dog accessories including:
- **Collars & Leashes** made from recycled materials
- **Dog Beds** filled with coconut fiber
- **Bandanas** and accessories
- **Eco-friendly products** supporting Bali street dogs

## 🚀 Theme Features

### Navigation Structure
- **Home** - Main landing page
- **Shop** - Product overview page with categories
- **Products** (dropdown) - Full product catalog:
  - Bandanas
  - Toys
  - Dog Bowls
  - Dog Beds
  - Collars
  - Leashes
  - Tote Bags
  - Raincoat
  - Treats
- **About** - Company story, team, and values
- **Blog** - News and updates

### Key Pages

#### Shop Page (`/pages/shop`)
- Product category overview
- Featured collections
- Image-with-text sections for each category
- Dawn theme compatible layout

#### About Page (`/pages/about`)
- Team photos and profiles
- Company values (Kindness, Responsibility, Honesty, Collaboration)
- Founder story and company history
- Production philosophy

#### Blog (`/blogs/news`)
- Grid layout with large images
- Publication dates shown
- Author names hidden
- Dawn theme styling

## 🛠️ Technical Details

### Theme Structure
```
kalidogwear/
├── snippets/
│   ├── header-dropdown-menu.liquid    # Main navigation with dropdown
│   ├── header-mega-menu.liquid        # Alternative mega menu layout
│   └── header-drawer.liquid           # Mobile navigation drawer
├── sections/
│   ├── header.liquid                  # Header section with logo
│   ├── footer.liquid                  # Footer with policy links
│   └── slideshow.liquid              # Homepage testimonials
├── templates/
│   ├── page.shop.json                 # Shop page configuration
│   ├── page.about.json                # About page configuration
│   ├── blog.json                      # Blog page settings
│   └── index.json                     # Homepage sections
└── assets/
    └── CSS and JS files
```

### Custom Modifications

#### Navigation Enhancements
- Added Shop, About, and Blog links
- Reordered navigation: Home → Shop → Products → About → Blog
- Filtered out catalog links for cleaner navigation
- Consistent styling across desktop and mobile

#### Footer Updates
- Restored "Info" section with policy links
- Enabled policy display in footer configuration
- Maintained Resources and Help sections

#### Header Improvements
- Added logo URL: `//id.kalidogwear.com/cdn/shop/files/logo-square-1212-x-1212-300-dpi_3x_120x_3964f5c7-08d9-45dd-bc4f-3a1de1599cac_120x.png?v=1641810214`
- Added 25px margin-top to navigation elements
- Responsive design with proper spacing

#### Homepage Slideshow
- Fixed testimonial text visibility
- Added color scheme settings for all slides
- Enhanced customer testimonials display

## 🎨 Design System

### Color Schemes
- **Scheme-1**: Primary theme colors
- **Background-1**: Neutral backgrounds
- Consistent color usage throughout sections

### Typography
- Dawn theme font stack
- Responsive heading sizes
- Caption-large for navigation items

### Layout Components
- **Image-with-text**: Product category showcases
- **Featured-collection**: Product displays
- **Slideshow**: Customer testimonials
- **Footer**: Multi-column layout with links

## 📱 Responsive Design

### Breakpoints
- Mobile: < 750px
- Tablet: 750px - 990px
- Desktop: > 990px

### Mobile Features
- Collapsible navigation drawer
- Touch-friendly dropdown menus
- Optimized spacing and sizing

## 🔧 Configuration

### Theme Settings
```json
{
  "logo_position": "middle-left",
  "mobile_logo_position": "center",
  "menu": "main-menu",
  "menu_type_desktop": "dropdown",
  "sticky_header_type": "on-scroll-up",
  "show_policy": true,
  "enable_country_selector": true,
  "enable_language_selector": true
}
```

### Collection Handles
- `/collections/bandanas`
- `/collections/toys`
- `/collections/dog-bowls`
- `/collections/dog-beds`
- `/collections/collars`
- `/collections/dog-leashes`
- `/collections/totebags`
- `/collections/raincoat`
- `/collections/treats`

## 🌍 Sustainability Focus

### Eco-Friendly Materials
- Recycled t-shirt yarn
- Coconut fiber filling
- Recycled plastic bottles (raincoats)
- Coconut yarn and macrame

### Social Impact
- Supports Bali street dog rescue
- Fair production practices
- Local Bali manufacturing
- Plastic reduction initiatives

## 📋 Testing Checklist

### Navigation
- [ ] All links work correctly
- [ ] Dropdown menus function properly
- [ ] Mobile navigation works
- [ ] Catalog links are hidden

### Pages
- [ ] Shop page loads with all sections
- [ ] About page displays team content
- [ ] Blog shows grid layout correctly
- [ ] Homepage slideshow displays testimonials

### Footer
- [ ] Policy links are visible
- [ ] All footer links work
- [ ] Copyright information displays

### Responsive
- [ ] Mobile layout works
- [ ] Tablet layout works
- [ ] Desktop layout works
- [ ] Touch interactions work

## 🔄 Version History

### Current Version
- Added Shop navigation and page
- Added About navigation and page
- Added Blog navigation
- Reordered navigation structure
- Restored footer policy links
- Fixed slideshow testimonial visibility
- Updated header logo configuration
- Added catalog filtering

### Previous Changes
- Fixed header-drawer snippet error
- Updated product collection handles
- Enhanced mobile navigation
- Improved footer structure

## 🛠️ Local Development Setup

### Prerequisites
- Node.js (v16+)
- Shopify CLI
- Theme Kit (optional)
- Git for version control

### Installation Steps

#### 1. Install Shopify CLI
```bash
npm install -g @shopify/cli @shopify/theme
```

#### 2. Clone the Repository
```bash
git clone <repository-url>
cd kalidogwear
```

#### 3. Authenticate with Shopify
```bash
shopify login --store your-store-name.myshopify.com
```

#### 4. Start Local Development
```bash
shopify theme dev
```

### Development Commands

#### Start Local Server
```bash
shopify theme dev
# Opens theme at http://localhost:9293
# Automatically syncs changes to preview
```

#### Push Changes to Live Theme
```bash
shopify theme push
# Pushes current theme to live store
```

#### Deploy to Development Theme
```bash
shopify theme push --theme <theme-id>
# Push to specific theme ID
```

#### Pull Live Theme Changes
```bash
shopify theme pull
# Downloads latest theme files
```

### File Watching & Hot Reload
- **Automatic**: Shopify CLI watches for file changes
- **Live Preview**: Changes appear instantly in browser
- **Sync**: Files automatically uploaded to preview theme

## 🎨 Template Customization Guide

### Navigation Customization

#### Add New Navigation Item
**File**: `snippets/header-dropdown-menu.liquid`

```liquid
<!-- Add after existing links -->
<li>
  <a
    id="HeaderMenu-NewItem"
    href="/pages/new-page"
    class="header__menu-item list-menu__item link link--text focus-inset"
  >
    <span>New Item</span>
  </a>
</li>
```

#### Modify Navigation Order
**Current Order**: Home → Shop → Products → About → Blog
- Edit the placement of `{%- if link.handle == 'home' -%}` blocks
- Rearrange the hardcoded links section

#### Add New Dropdown Category
**File**: `snippets/header-dropdown-menu.liquid`

```liquid
<li>
  <a
    id="HeaderMenu-Products-NewCategory"
    href="/collections/new-category"
    class="header__menu-item list-menu__item link link--text focus-inset caption-large"
  >
    New Category
  </a>
</li>
```

### Page Template Customization

#### Create New Page Template
1. **Copy existing template**:
   ```bash
   cp templates/page.shop.json templates/page.new-page.json
   ```

2. **Edit template content**:
   ```json
   {
     "sections": {
       "main": {
         "type": "main-page",
         "settings": {
           "page": "new-page-handle"
         }
       }
     },
     "order": ["main"]
   }
   ```

3. **Create corresponding Liquid file** (if needed):
   ```liquid
   <!-- sections/main-new-page.liquid -->
   <div class="page-width">
     <h1>{{ page.title }}</h1>
     <div>{{ page.content }}</div>
   </div>
   ```

#### Customize Shop Page Sections
**File**: `templates/page.shop.json`

```json
{
  "sections": {
    "custom-section": {
      "type": "image-with-text",
      "blocks": {
        "heading": {
          "type": "heading",
          "settings": {
            "heading": "Custom Section Title"
          }
        }
      },
      "settings": {
        "image": "shopify://shop_images/your-image.jpg",
        "layout": "image_first"
      }
    }
  }
}
```

### Footer Customization

#### Add Footer Section
**File**: `sections/footer.liquid`

```liquid
<div class="footer-block grid__item">
  <h2 class="footer-block__heading inline-richtext">Custom Section</h2>
  <ul class="footer-block__details-content list-unstyled">
    <li><a href="/pages/custom" class="link link--text list-menu__item list-menu__item--link">Custom Link</a></li>
  </ul>
</div>
```

#### Modify Footer Settings
**File**: `sections/footer-group.json`

```json
{
  "settings": {
    "show_policy": true,
    "newsletter_enable": true,
    "show_social": true
  }
}
```

### Header Customization

#### Update Logo
**File**: `sections/header.liquid`

```liquid
{%- if settings.logo != blank -%}
  <img src="{{ settings.logo | img_url: width: 300 }}" 
       alt="{{ settings.logo.alt | default: shop.name }}" 
       class="header__heading-logo">
{%- endif -%}
```

#### Adjust Header Spacing
**Files**: `snippets/header-dropdown-menu.liquid`, `snippets/header-mega-menu.liquid`

```liquid
<nav class="header__inline-menu" style="margin-top: 25px;">
```

### Styling Customization

#### Add Custom CSS
**File**: `assets/custom.css`

```css
/* Custom navigation styles */
.header__menu-item {
  color: #your-color;
}

/* Custom button styles */
.btn--primary {
  background-color: #your-brand-color;
}
```

#### Include Custom CSS
**File**: `layout/theme.liquid`

```liquid
{{ 'custom.css' | asset_url | stylesheet_tag }}
```

### Collection Customization

#### Add New Collection Handle
1. **Create collection in Shopify Admin**
2. **Update navigation links**:
   ```liquid
   <a href="/collections/new-collection">New Collection</a>
   ```

3. **Add to Shop page**:
   ```json
   {
     "type": "featured-collection",
     "settings": {
       "collection": "new-collection"
     }
   }
   ```

### Local Development Tips

#### File Organization
```
kalidogwear/
├── assets/          # CSS, JS, images
├── config/          # Theme settings
├── layout/          # Base templates
├── sections/        # Reusable sections
├── snippets/        # Reusable code snippets
├── templates/       # Page templates
└── locales/         # Translation files
```

#### Best Practices
1. **Use Liquid comments**: `{% comment %} Description {% endcomment %}`
2. **Follow naming conventions**: `kebab-case` for handles
3. **Test responsive**: Check mobile, tablet, desktop
4. **Validate HTML**: Use proper semantic tags
5. **Optimize images**: Use appropriate sizes and formats

#### Debugging Tools
- **Shopify CLI**: `shopify theme dev --live-reload`
- **Browser DevTools**: Inspect elements and console
- **Theme Editor**: Visual testing in Shopify Admin
- **Liquid Debug**: `{% comment %} {{ variable | inspect }} {% endcomment %}`

## 🤝 Contributing

### Development Workflow
1. **Setup local environment** using Shopify CLI
2. **Create feature branch** for changes
3. **Test locally** with `shopify theme dev`
4. **Verify responsive design** on all devices
5. **Test navigation links** and functionality
6. **Review footer** and header components
7. **Push to development theme** for team review
8. **Deploy to live** after approval

### Code Standards
- Follow Liquid templating best practices
- Use semantic HTML5 elements
- Maintain consistent indentation (2 spaces)
- Add helpful comments for complex logic
- Use kebab-case for file names and handles
- Test all changes on multiple devices

## 📞 Support

### Theme Customization
- Navigation modifications
- Page content updates
- Styling adjustments
- Feature additions

### Common Issues
- **Navigation not updating**: Check menu configuration in Shopify admin
- **Images not loading**: Verify Shopify CDN URLs
- **Mobile issues**: Test responsive breakpoints
- **Policy links missing**: Check footer-group.json settings

## 📄 License

This theme is proprietary to Kali Dogwear and based on Shopify's Dawn theme framework.

---

**Kali Dogwear**  
*Sustainable pet accessories from Bali, Indonesia*  
🌍 [www.kalidogwear.com](https://www.kalidogwear.com)
