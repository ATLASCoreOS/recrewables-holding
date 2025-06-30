# Homepage Development Brief - ReCrewables Maritime Consultancy

**Project:** ReCrewables Maritime Consultancy Website  
**Page:** Homepage (`app/page.tsx`)  
**Date:** June 25, 2025  
**Status:** Ready for Development - UPDATED WITH ACCURATE BUSINESS DEFINITION  

---

## 🎯 **Page Objectives**

### Primary Goals
- **Establish credibility** as experienced maritime professionals (former Masters and fleet managers)
- **Showcase comprehensive capabilities** from vessel concept to operational optimization
- **Convert visitors** into qualified leads through compelling positioning
- **Differentiate from consultants** by emphasizing hands-on operational experience
- **Drive engagement** with clear call-to-action to consultation

### Success Metrics
- **Conversion Rate:** >3% contact form submissions
- **Engagement:** >60 seconds average time on page
- **Mobile Performance:** <3 second load time
- **SEO Score:** 90+ on PageSpeed Insights

---

## 🏗 **Page Structure & Layout**

### Section 1: Hero Section
**Purpose:** Immediate impact establishing expertise and credibility  
**Height:** Full viewport (100vh)  
**Background:** `/images/hero/offshore-wind-hero.jpg` with gradient overlay

#### Content Elements:
- **Company Badge:** "Professional Maritime Consultancy" with online indicator
- **Main Headline:** "Maritime Excellence Delivered by Experts" (H1)
- **Subtitle:** "Supporting vessel owners, wind farm operators, and offshore contractors with complete maritime project management and specialised resource provision."
- **Second Subtitle:** "Highly experienced and trusted maritime professionals from our global network."
- **Primary CTA:** "Discuss Your Requirements" (leads to contact)
- **Scroll Indicator:** Animated chevron with "Discover our expertise"

#### Animation Details:
- **Page Load:** Fade-in with 1s delay, translate-y from 30px
- **Floating Elements:** Subtle pulse animations on decorative dots
- **CTA Button:** Hover scale 1.05x with shadow enhancement
- **Scroll Indicator:** Gentle pulse animation

---

### Section 2: Services Overview
**Purpose:** Showcase four core service offerings with credible positioning  
**Layout:** CSS Grid - 3 columns desktop, 2 tablet, 1 mobile  
**Background:** Gradient from brand-background to maritime-950
**Section Title:** "Professional Maritime Services For The Renewables Sector"
**Section Subtitle:** "Led by our team with proven track record in crew placement and project delivery"

#### Service Cards Content:

##### 1. Crew Placement (Lead Service - Full Width)
- **Image:** `/images/services/crew-provision.jpg`
- **Icon:** Users (Lucide React)
- **Description:** "Qualified and vetted maritime professionals from our experienced network, personally known and verified by our team."
- **Features:** 4 bullet points with CheckCircle icons:
  - Master, senior Officer, engineer & deck placements
  - Comprehensive professional vetting
  - Skills verification, development and assessment
  - Network of experienced maritime professionals
- **Credibility Note:** "Only the best, no compromises."

##### 2. New Build Management & Commissioning
- **Image:** `/images/services/vessel-management.jpg`
- **Icon:** Anchor
- **Description:** "Complete new build project management from concept through commissioning and delivery by former Masters and technical managers with proven track record."
- **Features:** 4 bullet points:
  - Project oversight and shipyard liaison
  - Design and ergonomic assessments
  - Sea trials and commissioning support
  - Dry-docking and refit management
- **Credibility Note:** "From concept through delivery"

##### 3. Maritime Project Management
- **Image:** `/images/services/ctv-operations.jpg`
- **Icon:** Settings
- **Description:** "Comprehensive maritime project management and technical support delivered by experts with hands-on operational experience across the globe."
- **Features:** 4 bullet points:
  - Operational efficiency guidance
  - Mobilisation support
  - Asset utilisation and optimisation consulting
  - Tender preparation & pitch support
- **Credibility Note:** "Results that count, when it matters"

##### 4. SMS Design & Implementation
- **Image:** `/images/services/safety-training.jpg`
- **Icon:** Shield
- **Description:** "Safety Management System design and implementation, plus comprehensive regulatory compliance consulting from professionals who've operated under these systems."
- **Features:** 4 bullet points:
  - Safety Management System development
  - Regulatory compliance (class, flag, port state, client)
  - IMCA inspections and surveys
  - [Empty placeholder]
- **Credibility Note:** "Practical solutions to complex problems"

#### Card Specifications:
```css
/* Card Styling */
.service-card {
  background: gradient from maritime-900/50 to maritime-950/80;
  backdrop-filter: blur(8px);
  border: 1px solid maritime-700/30;
  border-radius: 24px;
  padding: 8px;
  box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
}

/* Hover Effects */
.service-card:hover {
  transform: scale(1.02);
  box-shadow: 0 25px 50px -12px rgba(8, 145, 178, 0.2);
}
```

#### Interactive Behavior:
- **Hover State:** Card scales 1.02x, image scales 1.1x
- **Active Service:** State management for highlighting
- **Image Optimization:** WebP format with JPG fallback
- **Loading States:** Skeleton animations during image load

---

### Section 3: Capabilities Highlight  
**Purpose:** Reinforce competitive advantages and operational credibility  
**Layout:** 3-column grid with centered icons  
**Background:** Gradient maritime-950 to brand-background
**Section Title:** "Why Choose Recrewables?"
**Section Subtitle:** "Decades of maritime expertise bridging onshore strategy with offshore reality"

#### Capability Items:
1. **Hands-On Experience**
   - Icon: Award (12x12 size)
   - Title: "Experienced Maritime Professionals"
   - Description: "30+ years combined experience as former Masters, technical managers, and operations specialists - we've done the jobs we consult on and place people for."

2. **Proven Delivery**
   - Icon: Anchor
   - Title: "Proven Delivery Track Record"
   - Description: "Successful management of 15+ new build projects from concept to commissioning with hands-on experience and technical oversight in shipyards across the globe."

3. **Qualified Masters Network**
   - Icon: Users
   - Title: "Extensive industry Network"
   - Description: "Highly experienced and vetted professionals, personally known by our team, providing trusted, vetted and qualified placements only."

#### Animation Pattern:
- **Icon Containers:** Hover scale 1.1x with rotation
- **Gradient Backgrounds:** From maritime-500 to brand-foreground
- **Stagger Effect:** Icons animate in sequence on scroll

---

### Section 4: Final CTA
**Purpose:** Convert visitors to leads emphasizing consultation value  
**Background:** Gradient from maritime-500 via brand-foreground  
**Layout:** Centered content with single CTA

#### Content Elements:
- **Headline:** "Ready to Discuss Your Requirements?"
- **Description:** "Connect with our network of highly experienced and vetted maritime professionals. Get solutions driven services to solve your problems."
- **Primary CTA:** "Get In Touch" (leads to contact page)

---

## 📱 **Responsive Design Requirements**

### Breakpoint Behavior:
- **Mobile (< 768px):** Single column, larger touch targets
- **Tablet (768px - 1024px):** 2-column services grid
- **Desktop (> 1024px):** 3-column services grid for first 3, single row for 4th
- **Large (> 1280px):** Maximum content width with centered layout

### Mobile Optimizations:
- **Hero Text:** Smaller font sizes with maintained hierarchy
- **CTA Button:** Full-width on mobile, inline on desktop
- **Service Cards:** Simplified layout with condensed features
- **Touch Targets:** Minimum 44px for all interactive elements

---

## 🚀 **Performance Requirements**

### Image Optimization:
- All images must use Next.js Image component
- Descriptive alt text for accessibility
- Proper sizing with responsive breakpoints
- Quality setting of 85%
- Priority loading only for hero image

### Loading States:
- **Skeleton animations** for service cards during load
- **Progressive image loading** with blur placeholders
- **Smooth transitions** between loading and loaded states

### Animation Performance:
- **GPU acceleration** for transform operations
- **will-change** property for animated elements
- **Reduced motion** support for accessibility

---

## 🔧 **Implementation Details**

### Required Dependencies:
```json
{
  "next": "^14.0.0",
  "react": "^18.0.0",
  "lucide-react": "^0.263.1",
  "tailwindcss": "^3.0.0"
}
```

### State Management:
```typescript
// Required React hooks
import { useState, useEffect } from 'react'

// State for animations and interactions
const [isLoaded, setIsLoaded] = useState(false)
const [activeService, setActiveService] = useState(0)
```

### Component Structure:
```typescript
// File: app/page.tsx
'use client'

export default function HomePage() {
  // Component logic
  return (
    <main className="min-h-screen bg-brand-background overflow-hidden">
      {/* Sections as defined above */}
    </main>
  )
}
```

---

## ♿ **Accessibility Requirements**

### Semantic HTML:
- **Proper heading hierarchy** (H1 → H2 → H3)
- **Meaningful alt text** for all images
- **Focus management** for interactive elements
- **ARIA labels** for complex interactions

### Color Contrast:
- **Text on background:** Minimum 4.5:1 ratio
- **Interactive elements:** Clear focus indicators
- **Status indicators:** Multiple signifiers beyond color

### Keyboard Navigation:
- **Tab order** follows logical content flow
- **Skip links** for main content areas
- **Focus trapping** in modals (if implemented)

---

## 📊 **SEO Optimization**

### Meta Information:
```typescript
// File: app/layout.tsx or page.tsx
export const metadata = {
  title: "Maritime Consultancy by Former Masters & Fleet Managers | ReCrewables",
  description: "Professional maritime consultancy from experienced Masters and fleet managers. Vessel management, newbuild supervision, SMS implementation, and officer placement for offshore renewable energy.",
  keywords: "maritime consultancy, vessel management, newbuild management, masters placement, offshore wind, former masters, fleet managers",
  openGraph: {
    title: "ReCrewables - Maritime Excellence Delivered by Experts",
    description: "Maritime consultancy by former Masters and fleet managers with 30 years combined experience",
    images: ["/images/hero/offshore-wind-hero.jpg"]
  }
}
```

### Structured Data:
```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "ReCrewables",
  "description": "Maritime Consultancy by Former Masters and Fleet Managers",
  "url": "https://recrewables.com",
  "logo": "/images/branding/logo.svg",
  "contactPoint": {
    "@type": "ContactPoint",
    "telephone": "+44-XXX-XXX-XXXX",
    "contactType": "Customer Service"
  },
  "expertise": [
    "Vessel Management",
    "Newbuild Supervision", 
    "Safety Management Systems",
    "Officer Placement"
  ]
}
```

---

## 🧪 **Testing Requirements**

### Performance Testing:
- **Core Web Vitals:** LCP < 2.5s, FID < 100ms, CLS < 0.1
- **Lighthouse Score:** 90+ for Performance, Accessibility, SEO
- **Mobile Performance:** 3G network simulation testing

### Cross-Browser Testing:
- **Chrome/Edge:** Primary browser support
- **Firefox:** Secondary browser support
- **Safari:** Mobile and desktop compatibility
- **Mobile Browsers:** iOS Safari, Android Chrome

### User Experience Testing:
- **Navigation flow** from hero to contact
- **Service card interactions** and hover states
- **Credibility perception** of messaging
- **Loading state** user experience

---

## 📝 **Content Guidelines**

### Voice & Tone:
- **Professional Authority:** Former Masters and fleet managers
- **Operational Credibility:** We've done the jobs we consult on
- **Practical Solutions:** Hands-on experience, not just theory
- **Approachable Expertise:** Experienced professionals you can trust

### Key Messaging:
- **Primary:** "Maritime Excellence Delivered by Experts"
- **Secondary:** "Supporting vessel owners, wind farm operators, and offshore contractors"
- **Proof Points:** "30+ years combined experience", "15+ new build projects", "Extensive professional network"
- **Differentiators:** Only the best no compromises, proven delivery track record, global expertise

---

## 🚦 **Implementation Checklist**

### Development Phase:
- [ ] Set up Next.js 14 project structure
- [ ] Configure Tailwind with maritime color palette
- [ ] Implement responsive grid system for 4 services
- [ ] Add all required images to public/images/
- [ ] Create reusable component library
- [ ] Implement state management for interactions

### Content Phase:
- [ ] Apply accurate service descriptions based on real capabilities
- [ ] Implement credibility-focused messaging
- [ ] Add operational experience proof points
- [ ] Ensure consistent positioning throughout
- [ ] Optimize content for maritime industry SEO

### Design Phase:
- [ ] Apply brand typography system
- [ ] Implement gradient backgrounds
- [ ] Add hover and animation effects
- [ ] Test responsive breakpoints
- [ ] Optimize image loading and performance
- [ ] Implement accessibility features

### Testing Phase:
- [ ] Validate credibility perception with target audience
- [ ] Cross-browser compatibility testing
- [ ] Mobile device testing
- [ ] Performance benchmarking
- [ ] SEO audit and optimization
- [ ] Accessibility compliance verification

### Launch Phase:
- [ ] Final content accuracy review
- [ ] Performance optimization
- [ ] Analytics implementation
- [ ] Social media meta tags
- [ ] Sitemap generation
- [ ] Contact form integration testing

---

*This updated brief accurately represents ReCrewables as a maritime consultancy staffed by former Masters and fleet managers, emphasizing operational credibility and proven delivery capability while maintaining professional positioning in the offshore renewable energy sector.*