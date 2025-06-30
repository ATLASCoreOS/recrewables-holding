# Contact Page Development Brief - ReCrewables Maritime Consultancy

**Project:** ReCrewables Maritime Consultancy Website  
**Page:** Contact Page (`app/contact/page.tsx`)  
**Date:** June 26, 2025  
**Status:** Ready for Development - UPDATED WITH ACCURATE BUSINESS REQUIREMENTS  
**Design System:** Modern maritime aesthetic with Silicon Valley polish  

---

## 🎯 **Page Objectives**

### Primary Goals
- **Convert visitors to qualified leads** through streamlined contact process
- **Establish multiple contact pathways** for different communication preferences
- **Build trust through professional presentation** and response expectations
- **Capture service-specific inquiries** aligned with four core offerings
- **Provide clear project initiation pathway** for potential clients

### Success Metrics
- **Conversion Rate:** >3% contact form submissions from contact page
- **Engagement:** >90 seconds average time on page
- **Form Completion Rate:** >85% of started forms completed
- **Service-Specific Inquiries:** Track distribution across four service categories

---

## 🏗 **Page Structure & Layout**

### Section 1: Hero Section
**Purpose:** Professional introduction to contact capabilities  
**Height:** 50vh  
**Background:** `/images/hero/offshore-consultation.jpg` with maritime gradient overlay

#### Content Elements:
- **Company Badge:** "Professional Maritime Consultancy" with response indicator
- **Main Headline:** "Start Your Maritime Project" (H1)
- **Subtitle:** "Connect with experienced maritime professionals and fleet managers for expert maritime consultancy. We respond to all inquiries within 24 hours."
- **Breadcrumb:** Home > Contact

#### Animation Details:
- **Page Load:** Fade-in with translate-y from 20px
- **Background:** Subtle parallax effect on scroll

---

### Section 2: Contact Methods Grid
**Purpose:** Multiple contact options for different preferences  
**Layout:** 2-column grid (desktop), single column (mobile)  
**Background:** Gradient from maritime-950/50 to brand-background

#### Contact Cards:

##### 1. Email Contact
- **Icon:** Mail (Lucide React - maritime-500)
- **Title:** "Email Inquiry"
- **Primary:** `enquiry@recrewables.com`
- **Description:** "Detailed project discussions and document sharing"
- **CTA:** "Send Email" (mailto link)

##### 2. Phone Contact
- **Icon:** Phone (Lucide React - maritime-500)
- **Title:** "Direct Contact"
- **Primary:** `07721065268`
- **Description:** "Immediate consultation and urgent project needs"
- **CTA:** "Call Now" (tel link)

#### Card Design:
```css
.contact-card {
  background: rgba(var(--maritime-900), 0.40);
  backdrop-filter: blur(12px);
  border: 1px solid rgba(var(--maritime-700), 0.30);
  border-radius: 16px;
  padding: 2rem;
  transition: all 0.3s ease;
}

.contact-card:hover {
  transform: translateY(-4px);
  border-color: rgba(var(--maritime-500), 0.50);
}
```

---

### Section 3: Contact Form
**Purpose:** Primary lead capture with service-specific routing  
**Layout:** Single column form with grouped fields  
**Background:** Card with maritime glass effect

#### Form Structure:

##### Required Fields (with validation):
1. **Full Name** (required)
   - Type: text input
   - Validation: Required, min 2 characters
   - Placeholder: "Your full name"

2. **Email Address** (required)
   - Type: email input
   - Validation: Required, valid email format
   - Placeholder: "your@company.com"

3. **Phone Number** (required)
   - Type: tel input
   - Validation: Required, phone format
   - Placeholder: "+44 7XXX XXXXXX"

4. **Project Details** (required)
   - Type: textarea (6 rows)
   - Validation: Required, min 10 characters
   - Placeholder: "Please describe your project requirements, timeline, and any specific challenges you're facing..."

##### Optional Fields:
5. **Company**
   - Type: text input
   - Placeholder: "Your company name"

6. **Service Interest**
   - Type: select dropdown
   - Options aligned with four core services:
     - "General Inquiry"
     - "Vessel & Newbuild Management"
     - "Regulatory Compliance & Flag State"
     - "Strategic Maritime Consulting"
     - "Crew Provision & Training"

7. **Project Timeline**
   - Type: select dropdown
   - Options:
     - "Planning phase (6+ months)"
     - "Near-term (3-6 months)"
     - "Immediate (1-3 months)"
     - "Urgent (Within 1 month)"

#### Form Design Specifications:
```css
.form-input {
  background: rgba(var(--maritime-900), 0.30);
  border: 1px solid rgba(var(--maritime-600), 0.30);
  border-radius: 12px;
  padding: 0.75rem 1rem;
  color: white;
  transition: all 0.3s ease;
}

.form-input:focus {
  outline: none;
  border-color: var(--maritime-400);
  box-shadow: 0 0 0 3px rgba(var(--maritime-400), 0.20);
}

.submit-button {
  background: linear-gradient(135deg, var(--maritime-500), var(--maritime-600));
  border-radius: 12px;
  padding: 1rem 2rem;
  font-weight: 600;
  transition: all 0.3s ease;
}

.submit-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(var(--maritime-500), 0.25);
}
```

#### Submit Button:
- **Text:** "Send Inquiry"
- **Loading State:** "Sending..." with spinner
- **Success State:** "Message Sent!" with checkmark
- **Full width on mobile, auto width on desktop**

---

## 🔧 **Technical Requirements**

### Form Validation Rules:
```typescript
interface ContactFormData {
  name: string;          // Required, min 2 chars
  email: string;         // Required, valid email
  phone: string;         // Required, phone format
  company?: string;      // Optional
  service?: string;      // Optional, default "General Inquiry"
  timeline?: string;     // Optional
  message: string;       // Required, min 10 chars
}

const validationRules = {
  name: { required: true, minLength: 2 },
  email: { required: true, pattern: /^[^\s@]+@[^\s@]+\.[^\s@]+$/ },
  phone: { required: true, pattern: /^[\+]?[1-9][\d]{0,15}$/ },
  message: { required: true, minLength: 10 }
};
```

### Error Handling:
- **Field-level validation:** Real-time validation on blur
- **Form-level validation:** On submit attempt
- **Error styling:** Red border + error message below field
- **Success feedback:** Green checkmark + success message

### Accessibility:
- **ARIA labels:** All form fields properly labeled
- **Error announcements:** Screen reader compatible
- **Keyboard navigation:** Full tab order support
- **Focus management:** Clear focus indicators

---

## 📱 **Responsive Design**

### Desktop (1024px+):
- **Layout:** 2-column contact methods, single column form
- **Form:** 2-column grid for name/email and company/phone
- **Spacing:** Generous padding and margins

### Tablet (768px - 1023px):
- **Layout:** Single column throughout
- **Form:** 2-column grid maintained for smaller fields
- **Touch targets:** Minimum 44px height

### Mobile (320px - 767px):
- **Layout:** Single column, stacked elements
- **Form:** Single column for all fields
- **Typography:** Larger base font size (16px minimum)

---

## 🎨 **Visual Design Elements**

### Color Scheme:
- **Primary:** Maritime blue gradients (maritime-500 to maritime-600)
- **Background:** Dark maritime theme with transparency effects
- **Text:** White primary, maritime-foreground/70 secondary
- **Borders:** maritime-600/30 with maritime-400 focus states

### Typography:
- **Headlines:** Montserrat font family, font-light
- **Body text:** Default system font stack
- **Form labels:** Medium weight, white color
- **Placeholders:** maritime-foreground/50

### Effects:
- **Glass morphism:** Backdrop blur with transparency
- **Subtle animations:** Hover states and micro-interactions
- **Focus states:** Maritime blue glow effects
- **Loading states:** Smooth transitions and spinners

---

## 📊 **Analytics & Tracking**

### Conversion Tracking:
- **Form submissions:** Track completion rate by field
- **Service interest:** Analyze most requested services
- **Drop-off points:** Identify form abandonment patterns
- **Contact method usage:** Track email vs phone preferences

### Success Events:
- **Form start:** User focuses on first field
- **Form completion:** Successful submission
- **Contact link clicks:** Email and phone link engagement
- **Page engagement:** Time on page and scroll depth

---

## 🚀 **Implementation Checklist**

### Development Phase:
- [ ] Implement responsive layout structure
- [ ] Build contact methods cards with hover effects
- [ ] Create contact form with required field validation
- [ ] Add form submission handling and loading states
- [ ] Implement error handling and success feedback
- [ ] Test form validation across all required fields

### Content Phase:
- [ ] Verify contact information accuracy (enquiry@recrewables.com, 07721065268)
- [ ] Align service dropdown options with core offerings
- [ ] Test email integration and form delivery
- [ ] Ensure response time messaging is accurate

### Design Phase:
- [ ] Apply maritime design system consistently
- [ ] Implement glass morphism effects
- [ ] Add hover animations and micro-interactions
- [ ] Test responsive breakpoints across devices
- [ ] Optimize form field spacing and typography

### Testing Phase:
- [ ] Validate form submission functionality
- [ ] Test required field validation
- [ ] Cross-browser compatibility testing
- [ ] Mobile device form usability testing
- [ ] Accessibility compliance verification
- [ ] Email delivery testing

### Launch Phase:
- [ ] Analytics implementation and tracking setup
- [ ] Contact information verification
- [ ] Form submission monitoring
- [ ] Response time tracking
- [ ] Lead quality assessment

---

*This brief establishes the contact page as the primary conversion point for ReCrewables Maritime Consultancy, emphasizing professional presentation while maintaining the operational credibility established throughout the site.*