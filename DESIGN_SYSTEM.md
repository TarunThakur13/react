# AccessRide Design System

## Project Overview
**AccessRide** - AI Accessible Transport Finder
A web application designed to help wheelchair users and mobility-challenged individuals find accessible public transport and ride-sharing options through an AI-powered chat assistant.

## Design Principles
- **Accessibility First (WCAG AA compliant)**
- **High Contrast** for readability
- **Large, Legible Fonts** for clarity
- **Spacious Layout** with ample touch targets
- **Clear Visual Hierarchy** for intuitive navigation
- **Modern, Clean, Trustworthy** aesthetic

## Color Palette

### Primary Colors
- **Primary Blue**: `#2563EB` (Trust, calm, professional)
- **Secondary Green**: `#059669` (Accessibility, nature, positive)
- **Accent Orange**: `#F97316` (High contrast, attention-grabbing)

### Neutral Colors
- **Dark Gray**: `#1F2937` (Text, headings)
- **Medium Gray**: `#6B7280` (Secondary text)
- **Light Gray**: `#F3F4F6` (Backgrounds, borders)
- **White**: `#FFFFFF` (Primary background)

### Semantic Colors
- **Success**: `#10B981` (Green)
- **Warning**: `#F59E0B` (Yellow)
- **Error**: `#EF4444` (Red)
- **Info**: `#3B82F6` (Blue)

## Typography

### Font Family
- **Primary**: Inter (Clean, modern, highly readable)
- **Fallback**: system-ui, -apple-system, sans-serif

### Font Sizes
- **Heading 1**: 3rem (48px) - Main page titles
- **Heading 2**: 2.25rem (36px) - Section headers
- **Heading 3**: 1.875rem (30px) - Subsection headers
- **Heading 4**: 1.5rem (24px) - Card titles
- **Body Large**: 1.125rem (18px) - Important text
- **Body**: 1rem (16px) - Regular text
- **Body Small**: 0.875rem (14px) - Secondary text
- **Caption**: 0.75rem (12px) - Labels, metadata

### Font Weights
- **Light**: 300
- **Regular**: 400
- **Medium**: 500
- **Semibold**: 600
- **Bold**: 700

## Component Library

### Buttons

#### Primary Button
- Background: `#2563EB`
- Text: White
- Padding: 12px 24px
- Border radius: 8px
- Hover: `#1D4ED8`
- Focus: 2px outline `#3B82F6`

#### Secondary Button
- Background: Transparent
- Border: 2px `#2563EB`
- Text: `#2563EB`
- Padding: 12px 24px
- Border radius: 8px
- Hover: `#F3F4F6`

#### CTA Button (Start Chat)
- Background: `#F97316`
- Text: White
- Padding: 16px 32px
- Border radius: 12px
- Font size: 1.125rem
- Font weight: 600
- Hover: `#EA580C`

### Form Elements

#### Input Fields
- Border: 2px `#D1D5DB`
- Border radius: 8px
- Padding: 12px 16px
- Focus: Border `#2563EB`, outline `#3B82F6`
- Background: White
- Font size: 1rem

#### Text Areas
- Same styling as inputs
- Min height: 100px
- Resize: vertical only

### Cards

#### Route Suggestion Card
- Background: White
- Border: 1px `#E5E7EB`
- Border radius: 12px
- Padding: 20px
- Shadow: 0 4px 6px rgba(0, 0, 0, 0.05)
- Hover: Shadow 0 10px 15px rgba(0, 0, 0, 0.1)

#### Chat Message Card
- User messages: Right-aligned, `#2563EB` background
- AI messages: Left-aligned, `#F3F4F6` background
- Border radius: 16px
- Padding: 12px 16px
- Max width: 80%

### Navigation

#### Header
- Background: White
- Border bottom: 1px `#E5E7EB`
- Padding: 16px 24px
- Logo: Left-aligned
- Navigation: Right-aligned

#### Footer
- Background: `#1F2937`
- Text: White
- Padding: 32px 24px
- Links: `#9CA3AF`

## Accessibility Guidelines

### Color Contrast
- All text must have minimum 4.5:1 contrast ratio
- Large text (18px+) must have minimum 3:1 contrast ratio
- Interactive elements must have clear focus indicators

### Touch Targets
- Minimum 44px height for all interactive elements
- Minimum 8px spacing between touch targets
- Clear visual feedback on hover/focus

### Keyboard Navigation
- All interactive elements must be keyboard accessible
- Clear focus indicators (2px outline)
- Logical tab order

### Screen Reader Support
- Semantic HTML structure
- Proper ARIA labels
- Alt text for images
- Descriptive link text

## Layout Guidelines

### Grid System
- 12-column grid for desktop
- 4-column grid for mobile
- Consistent gutters: 24px desktop, 16px mobile

### Spacing Scale
- 4px, 8px, 12px, 16px, 20px, 24px, 32px, 48px, 64px

### Breakpoints
- Mobile: 320px - 767px
- Tablet: 768px - 1023px
- Desktop: 1024px+

## Icon System

### Transportation Icons
- 🚇 Metro/Subway
- 🚌 Bus
- 🚊 Train
- 🚕 Taxi
- ♿ Wheelchair accessible
- 🎯 Location pin

### UI Icons
- 💬 Chat
- 🗺️ Map
- ⭐ Star rating
- 📝 Feedback
- 👤 Profile
- 🔍 Search
- ❌ Close
- ✅ Check

## Animation Guidelines

### Transitions
- Duration: 200ms for micro-interactions
- Duration: 300ms for page transitions
- Easing: ease-in-out

### Hover Effects
- Subtle scale (1.02) for cards
- Color transitions for buttons
- Opacity changes for links

## Responsive Design

### Mobile-First Approach
- Start with mobile layout
- Progressive enhancement for larger screens
- Touch-friendly interactions

### Content Prioritization
- Most important content first
- Collapsible navigation on mobile
- Simplified layouts for small screens