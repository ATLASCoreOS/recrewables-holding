# Services Page Redesign Brief - ReCrewables Maritime Consultancy

**Project:** ReCrewables Maritime Consultancy Website  
**Pages:** Main Services Page + Individual Service Pages  
**Date:** June 26, 2025  
**Status:** Ready for Development - NEW STRUCTURE WITH PROJECT MANAGEMENT  

---

## 🎯 **Project Overview**

### Restructured Services Architecture
- **Main Services Page:** `/services` - Overview with basic information and navigation to detailed pages
- **Individual Service Pages:** Dedicated pages for each service with comprehensive details
- **Navigation Enhancement:** Dropdown menu under "Services" with direct service links
- **Contact Integration:** Service-specific preselection on contact forms

### Updated Service Portfolio (New Order)
1. **Crew Placement** - `/services/crew-placement` *(LEAD SERVICE - Featured prominently on homepage)*
2. **Regulatory Compliance & Safety** - `/services/regulatory-compliance`  
3. **New Build Management & Commissioning** - `/services/newbuild-management`
4. **Project Management** - `/services/project-management` *(NEW SERVICE)*

**Removed:** Strategic Consulting (eliminated from service offering)
**Updated:** Crew Placement positioned as lead service throughout website

---

## 🏗 **Main Services Page Structure**

### Page: `/services/page.tsx`

#### Section 1: Hero Section
**Purpose:** Professional services introduction with operational credibility  
**Height:** 60vh  
**Background:** `/images/hero/offshore-wind-installation.jpg` with gradient overlay

**Content Elements:**
- **Company Badge:** "Professional Maritime Consultancy" with online indicator
- **Main Headline:** "Expert Maritime Consultancy Services" (H1)
- **Subtitle:** "Specialized crew placement, regulatory compliance, new build management, and project management services backed by decades of offshore renewable energy experience."
- **Primary CTA:** "Discuss Your Needs" (leads to contact)
- **Breadcrumb:** Home > Services

#### Section 2: Services Overview Grid
**Purpose:** Service summaries with navigation to detailed pages  
**Layout:** 2x2 grid on desktop, single column on mobile  
**Background:** Gradient from maritime-950/50 to brand-background

##### Service Cards Content:

**1. Crew Placement** *(LEAD SERVICE)*
- **Link:** `/services/crew-placement`
- **Icon:** Users (Large - 12x12)
- **Gradient:** `from-maritime-500 to-maritime-600`
- **Summary:** "Qualified and vetted maritime professionals from our experienced network, personally known and verified by our team."
- **Priority:** Featured first in all service listings and prominently on homepage

**2. Regulatory Compliance & Safety**
- **Link:** `/services/regulatory-compliance`
- **Icon:** Shield (Large - 12x12)  
- **Gradient:** `from-brand-foreground to-maritime-400`
- **Summary:** "Comprehensive compliance solutions backed by extensive safety management systems and audit experience across multiple jurisdictions."

**3. New Build Management & Commissioning**
- **Link:** `/services/newbuild-management`
- **Icon:** Anchor (Large - 12x12)
- **Gradient:** `from-maritime-500 to-maritime-600`
- **Summary:** "Complete new build project management from concept through commissioning and delivery by former Masters and technical managers with proven track record."

**4. Project Management**
- **Link:** `/services/project-management`
- **Icon:** Clipboard (Large - 12x12)
- **Gradient:** `from-maritime-400 to-maritime-500` *(brand guideline colors)*
- **Summary:** "Marine project management services for contractors working within offshore renewables who need support managing mobilisation and utilisation of assets."

#### Card Design Specifications:
- **Title:** Clickable H3 linking to individual service page
- **Summary:** 1-2 sentences as specified
- **CTA:** "Learn More" button linking to individual service page
- **Hover Effects:** Card scales 1.02x, title color changes to maritime-300
- **Mobile:** Single column, full-width cards

---

## 📄 **Individual Service Pages Structure**

### Template Structure (All Service Pages)
Each service page follows the same template with service-specific content:

#### Section 1: Service Hero
- **Background:** Service-specific hero image
- **Content:** Service name (H1), detailed description, primary CTA
- **Breadcrumb:** Home > Services > [Service Name]

#### Section 2: Service Details
- **Features List:** Comprehensive bullet points
- **Key Benefits:** What clients achieve
- **Process Overview:** How the service is delivered

#### Section 3: Credibility Section
- **Experience Highlights:** Relevant team experience
- **Track Record:** Service-specific achievements
- **Certifications:** Relevant qualifications

#### Section 4: Contact CTA
- **Preselected Service:** Contact form opens with service preselected
- **Direct Contact:** Phone/email options
- **Consultation Booking:** Schedule discussion link

---

## 🔄 **Navigation Enhancement**

### Dropdown Menu Implementation
**Location:** Main navigation under "Services"  
**Component:** `components/layout/Navigation.tsx`

#### Dropdown Structure:
```typescript
const servicesDropdown = [
  { name: "Crew Placement", href: "/services/crew-placement" },
  { name: "Regulatory Compliance & Safety", href: "/services/regulatory-compliance" },
  { name: "New Build Management & Commissioning", href: "/services/newbuild-management" },
  { name: "Project Management", href: "/services/project-management" }
]
```

#### Interactive Behavior:
- **Hover/Focus:** Dropdown appears with fade-in animation
- **Click on "Services":** Links to main services overview page
- **Keyboard Navigation:** Arrow keys navigate dropdown items
- **Mobile:** Collapsible accordion in mobile menu

---

## 📋 **Individual Service Page Specifications**

### 1. Crew Placement (`/services/crew-placement`)

**Hero Image:** `/images/services/crew-provision.jpg`  
**Full Description:** "Qualified and vetted maritime professionals from our experienced network, personally known and verified by our team. We provide comprehensive professional vetting, skills verification, development and assessment, and access to a network of experienced maritime professionals with proven track records."

**Features:**
- Master, senior officer, engineer & deck placements
- Comprehensive professional vetting  
- Skills verification, development and assessment
- Network of experienced maritime professionals
- References and background checks
- Certification verification and validation

**Benefits:**
- Access to vetted, qualified professionals
- Reduced recruitment time and costs
- Confidence in professional competency
- Ongoing support and relationship management

**Stats Badge:** "Vetted Network" / "Qualified professionals verified"

---

### 2. Regulatory Compliance & Safety (`/services/regulatory-compliance`)

**Hero Image:** `/images/services/regulatory-compliance.jpg`  
**Full Description:** "Comprehensive compliance solutions backed by extensive safety management systems and audit experience across multiple jurisdictions. We provide practical SMS implementation from operational experience."

**Features:**
- Safety management systems (SMS) design and implementation
- ISM and ISPS code compliance consulting
- Internal and external auditing services
- Risk assessment and management protocols
- Multi-flag compliance expertise and guidance
- Regulatory documentation and reporting support

**Benefits:**
- Extensive SMS implementation and audit experience
- Multi-jurisdictional compliance expertise across Europe
- Proven track record across European offshore operations
- Comprehensive risk mitigation strategies and protocols

**Stats Badge:** "100% Safety Record" / "Uncompromising standards maintained"

---

### 3. New Build Management & Commissioning (`/services/newbuild-management`)

**Hero Image:** `/images/services/vessel-management.jpg`  
**Full Description:** "Complete new build project management from concept through commissioning and delivery by former Masters and technical managers with proven track record. Hands-on experience and technical oversight in shipyards across the globe."

**Features:**
- Project oversight and shipyard liaison
- Design and ergonomic assessments
- Sea trials and commissioning support
- Dry-docking and refit management
- Technical supervision and quality control
- Delivery management and handover

**Benefits:**
- From concept through delivery expertise
- 15+ new build projects successfully managed
- Hands-on experience in shipyards globally
- Proven track record with technical oversight

**Stats Badge:** "15+ New Build Projects" / "From concept through delivery"

---

### 4. Project Management (`/services/project-management`) **NEW**

**Hero Image:** `/images/services/project-management.jpg` *(use provided wind turbine construction image)*  
**Full Description:** "Marine project management services for contractors working within offshore renewables who may not have experience with the sector or need support managing mobilisation and utilisation of assets. We provide comprehensive project oversight from planning through execution."

**Features:**
- Marine project planning and execution
- Asset mobilisation and deployment coordination
- Contractor support for offshore renewable projects
- Resource utilisation optimization
- Timeline and milestone management
- Stakeholder coordination and communication

**Benefits:**
- Sector-specific expertise in offshore renewables
- Reduced project risk through experienced oversight
- Optimized asset utilisation and cost efficiency
- Seamless coordination between marine and construction teams

**No Stats Badge** *(as specified)*

---

## 📞 **Contact Form Integration**

### Updated Service Options
**File:** `app/contact/page.tsx`

#### New Services Array:
```typescript
const services = [
  "Crew Placement",
  "Regulatory Compliance & Safety", 
  "New Build Management & Commissioning",
  "Project Management",
  "General Inquiry"
]
```

#### Preselection Logic:
```typescript
// URL parameter handling for service preselection
const searchParams = useSearchParams()
const preselectedService = searchParams.get('service')

// Form initialization with preselected service
const [formData, setFormData] = useState({
  service: preselectedService || '',
  // ... other fields
})
```

#### Service Page CTAs:
Each service page CTA links to: `/contact?service=[service-name]`

---

## 🎨 **Design System Compliance**

### Brand Guidelines Adherence
- **Color Palette:** All gradients and colors follow established maritime color system
- **Typography:** Montserrat font family for headings, consistent hierarchy
- **Card Design:** Existing card-depth class and hover effects
- **Icons:** Lucide React icons, 12x12 size for service icons
- **Spacing:** Section-padding and section-container classes maintained

### Project Management Service Styling
- **Gradient:** `from-maritime-400 to-maritime-500` (brand compliant)
- **Icon:** Clipboard from Lucide React
- **Card Treatment:** Same card-depth and hover effects as other services

---

## 📱 **Responsive Design Requirements**

### Main Services Page
- **Mobile (< 768px):** Single column, stacked service cards
- **Tablet (768px - 1024px):** 2-column grid, maintains card proportions
- **Desktop (> 1024px):** 2x2 grid layout, optimal card sizing
- **Large (> 1280px):** Maximum content width with enhanced spacing

### Individual Service Pages  
- **Mobile:** Single column, condensed hero height, simplified navigation
- **Tablet:** Maintained readability, adapted grid layouts
- **Desktop:** Full layout with side-by-side content sections
- **Navigation:** Responsive dropdown that becomes accordion on mobile

---

## 🔧 **Technical Implementation**

### Required File Updates
1. **Main Services Page:** Update `app/services/page.tsx` with new 4-service structure
2. **Navigation Component:** Update `components/layout/Navigation.tsx` with dropdown
3. **Contact Form:** Update `app/contact/page.tsx` with new services array
4. **New Service Pages:** Create 4 individual service page files
5. **Image Assets:** Add project management hero image to `/images/services/`

### New Page Files to Create:
- `app/services/crew-provision/page.tsx`
- `app/services/regulatory-compliance/page.tsx`  
- `app/services/vessel-newbuild-management/page.tsx`
- `app/services/project-management/page.tsx`

### Navigation Dropdown Implementation:
```typescript
// Enhanced navigation with services dropdown
const [isServicesOpen, setIsServicesOpen] = useState(false)

// Dropdown menu component
<div className="relative group">
  <Link 
    href="/services"
    className="nav-link"
    onMouseEnter={() => setIsServicesOpen(true)}
    onMouseLeave={() => setIsServicesOpen(false)}
  >
    Services
  </Link>
  
  {isServicesOpen && (
    <div className="absolute top-full left-0 bg-maritime-900 rounded-lg shadow-xl border border-maritime-700/30 min-w-64 py-2">
      {servicesDropdown.map((service) => (
        <Link
          key={service.href}
          href={service.href}
          className="block px-4 py-3 text-white/80 hover:text-white hover:bg-maritime-800/50 transition-colors"
        >
          {service.name}
        </Link>
      ))}
    </div>
  )}
</div>
```

---

## 🧪 **Testing Requirements**

### Navigation Testing
- **Dropdown Functionality:** Hover states, keyboard navigation, mobile accordion
- **Service Links:** All service page links function correctly
- **Breadcrumb Navigation:** Proper hierarchy and back-navigation
- **Contact Preselection:** Service preselection works from all service pages

### Content Testing  
- **Service Descriptions:** Accurate representation of capabilities
- **Call-to-Action Flow:** Smooth transition from service pages to contact
- **Mobile Experience:** Touch-friendly navigation and readable content
- **Load Performance:** Individual service pages load efficiently

### User Experience Testing
- **Service Discovery:** Users can easily find specific services
- **Information Hierarchy:** Clear progression from overview to detailed pages
- **Contact Conversion:** Service-specific leads are properly captured
- **Professional Positioning:** Maintains credibility and expertise messaging

---

## 📊 **SEO Optimization**

### URL Structure
- **Main Page:** `/services` - "Maritime Consultancy Services | ReCrewables"
- **Individual Pages:** `/services/[service-name]` - "[Service Name] | Maritime Consultancy | ReCrewables"

### Meta Descriptions
- **Crew Provision:** "Professional maritime crew placement and vetting services..."
- **Regulatory Compliance:** "Comprehensive maritime safety and compliance consulting..."
- **Vessel Management:** "Expert vessel and newbuild management services..."
- **Project Management:** "Marine project management for offshore renewable contractors..."

### Structured Data
```json
{
  "@context": "https://schema.org",
  "@type":