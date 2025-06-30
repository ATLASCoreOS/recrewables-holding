# ReCrewables Brand Guidelines

*Professional Maritime Consultancy for Renewable Energy*

---

## 🎨 **Brand Colors**

### Primary Color Palette

| Color | Hex Code | Usage | CSS Variable |
|-------|----------|-------|--------------|
| **Background** | `#111729` | Primary background, dark sections | `--brand-background` |
| **Foreground** | `#58bac8` | Primary brand color, text, accents | `--brand-foreground` |
| **Accent 1** | `#4c9fae` | Secondary accents, hover states | `--brand-accent-1` |
| **Accent 2** | `#408493` | Tertiary accents, borders | `--brand-accent-2` |
| **Accent 3** | `#356979` | Subtle accents, depth | `--brand-accent-3` |

### Extended Maritime Palette

```css
/* Available in Tailwind as maritime-50 through maritime-950 */
maritime-50:  #f0f9fa    /* Lightest tint */
maritime-100: #daf2f4
maritime-200: #b8e6ea
maritime-300: #58bac8    /* Brand foreground */
maritime-400: #4c9fae    /* Brand accent 1 */
maritime-500: #408493    /* Brand accent 2 */
maritime-600: #356979    /* Brand accent 3 */
maritime-700: #2d5664
maritime-800: #274654
maritime-900: #243b47
maritime-950: #111729    /* Brand background */
```

---

## ✍️ **Typography**

### Primary Fonts

#### Headings
- **Font**: Montserrat Light Alt1
- **Weight**: 300 (Light)
- **Style**: Normal
- **Usage**: All page titles, section headings, hero text
- **CSS**: `font-family: 'Montserrat', system-ui, sans-serif;`

#### Subtitles
- **Font**: Brandmark Sans 7
- **Weight**: 300 (Light)  
- **Style**: Normal
- **Usage**: Taglines, section subtitles, descriptions
- **CSS**: `font-family: 'Brandmark Sans 7', system-ui, sans-serif;`

#### Body Text
- **Font**: Inter
- **Weight**: 400 (Regular)
- **Usage**: Paragraphs, navigation, general content
- **CSS**: `font-family: 'Inter', system-ui, sans-serif;`

### Typography Scale

| Class | Size | Line Height | Weight | Usage |
|-------|------|-------------|---------|-------|
| `text-display` | 4xl-7xl | 1.1 | 300 | Hero titles |
| `text-heading` | 2xl-4xl | 1.2 | 300 | Section headings |
| `text-subtitle` | lg-xl | 1.3 | 300 | Subtitles |
| `text-body` | base-lg | 1.6 | 400 | Body text |

---

## 🖼️ **Logo Usage**

### Your ReCrewables Logo Assets

Based on your provided files, you have 5 logo variations:

| Logo File | Usage Context | Background | Description |
|-----------|---------------|------------|-------------|
| `Icon.png` | Icons, favicons, navigation | Any | R symbol for compact spaces |
| `LogoBW.png` | Professional documents | Light/white | Black & white version |
| `LogoColourDark.png` | Dark backgrounds | Dark/navy | Colored version for dark themes |
| `LogoColourLight.png` | Light backgrounds | White/light | Colored version for light themes |
| `LogoTransparent.png` | Overlays, flexible use | Any | Transparent background version |

### Logo Files Location
Save your logo files in these exact locations:

```
public/
└── images/
    └── logo/
        ├── Icon.png                 # R symbol for navigation & icons
        ├── LogoBW.png              # Black & white version
        ├── LogoColourDark.png      # Colored version for dark backgrounds  
        ├── LogoColourLight.png     # Colored version for light backgrounds
        └── LogoTransparent.png     # Transparent background version
```

### Implementation Guide

**Navigation & Headers:**
- Use `Icon.png` for the icon + "ReCrewables" text
- Use `LogoColourDark.png` for dark navigation backgrounds

**Footer:**  
- Use `Icon.png` + text on dark footer backgrounds

**Documents & Print:**
- Use `LogoBW.png` for maximum legibility and cost-effective printing

**Flexible Sections:**
- Use `LogoTransparent.png` when overlaying on images or varied backgrounds
- Use `LogoColourLight.png` on white/light sections
- Use `LogoColourDark.png` on dark sections

### Logo Specifications

| Version | Minimum Size | Recommended Size | Clear Space |
|---------|-------------|------------------|-------------|
| Icon.png | 24x24px | 48x48px | 12px all sides |
| Full Text Logos | 120x32px | 240x64px | Logo height on all sides |
| Large Display | 240x64px | 480x128px | 1.5x logo height all sides |

---

## 🎭 **Design Principles**

### Visual Style
- **Modern & Clean**: Silicon Valley tech aesthetics
- **Maritime Heritage**: Ocean-inspired gradients and flows
- **Professional**: Trustworthy and expert positioning
- **Accessible**: High contrast, readable typography

### Key Design Elements
- **Glass Morphism**: Subtle transparency effects
- **Gradient Overlays**: Maritime-themed color transitions  
- **Smooth Animations**: Gentle hover and transition effects
- **Geometric Precision**: Clean lines and structured layouts

---

## 🧩 **Component Standards**

### Buttons

```css
/* Primary Action */
.btn-primary {
  background: #58bac8;
  color: #111729;
  hover: #4c9fae;
}

/* Secondary Action */
.btn-secondary {
  border: 1px solid #58bac8;
  color: #58bac8;
  hover: background #58bac8, color #111729;
}
```

### Cards

```css
/* Standard Content Cards */
.card-maritime {
  background: rgba(36, 59, 71, 0.5);
  border: rgba(88, 186, 200, 0.2);
  backdrop-blur: 12px;
}
```

---

## 📱 **Responsive Guidelines**

### Breakpoints
- **Mobile**: 0-640px
- **Tablet**: 640-1024px  
- **Desktop**: 1024px+
- **Large**: 1280px+

### Mobile-First Approach
- Start with mobile design
- Progressive enhancement for larger screens
- Touch-friendly 44px minimum targets
- Readable 16px+ font sizes

---

## ♿ **Accessibility Standards**

### Color Contrast
- **Text on Background**: 4.5:1 minimum ratio
- **Brand Colors**: All combinations tested for WCAG AA
- **Focus States**: Clear 2px brand-colored outlines

### Typography Accessibility
- **Minimum Size**: 16px for body text
- **Line Height**: 1.6 for body, 1.2 for headings
- **Font Weight**: Minimum 300 for readability

---

## 🚀 **Implementation Guidelines**

### CSS Variables Usage
```css
/* Use brand variables consistently */
background-color: var(--brand-background);
color: var(--brand-foreground);
border-color: var(--brand-accent-1);
```

### Tailwind Classes
```html
<!-- Preferred approach -->
<div class="bg-brand-background text-brand-foreground">
<h1 class="font-montserrat font-light text-display">
<p class="font-brandmark font-light text-subtitle">
```

### Animation Standards
- **Duration**: 300ms for interactions, 500ms for transitions
- **Easing**: `ease-out` for entrances, `ease-in-out` for transitions
- **Respect Motion Preferences**: Reduced motion support included

---

## 📋 **Brand Voice & Messaging**

### Tone of Voice
- **Professional**: Expert knowledge and authority
- **Approachable**: Friendly and consultative  
- **Confident**: Proven track record and capabilities
- **Forward-Thinking**: Innovation in renewable energy

### Key Messages
- "Navigating the Future of Renewable Energy"
- "Professional Maritime Consultancy"
- "Expert Guidance for Offshore Wind Projects"
- "Proven Excellence in CTV Operations"

---

## ✅ **Brand Compliance Checklist**

### Before Publishing
- [ ] Brand colors used consistently
- [ ] Montserrat Light for all headings
- [ ] Brandmark Sans 7 for subtitles
- [ ] Logo placement follows guidelines
- [ ] Accessibility standards met
- [ ] Mobile responsiveness tested
- [ ] Animation performance optimized

### Quality Assurance
- [ ] All text readable on backgrounds
- [ ] Interactive elements have clear hover states
- [ ] Forms use consistent styling
- [ ] Loading states implemented
- [ ] Error messages follow brand voice

---

*This document serves as the authoritative guide for maintaining ReCrewables' brand consistency across all digital touchpoints.*