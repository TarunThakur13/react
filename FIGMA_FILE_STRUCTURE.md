# AccessRide Figma File Structure

## Project Organization

### Main Frames

#### 1. 🎨 Design System
**Location**: Top of the file
**Size**: 1200x800
**Background**: #FFFFFF

**Sub-frames:**
- **Colors** (200x400)
- **Typography** (400x400)
- **Components** (600x400)
- **Spacing** (200x400)

#### 2. 🖥️ Desktop Screens
**Location**: Below Design System
**Size**: 1440x1024 each
**Background**: #FFFFFF

**Screens:**
- **Home Page** (0, 0)
- **Chat Interface** (1500, 0)
- **Map View** (3000, 0)
- **Feedback Page** (4500, 0)
- **Profile Dashboard** (6000, 0)

#### 3. 📱 Mobile Screens
**Location**: Below Desktop Screens
**Size**: 375x812 each
**Background**: #FFFFFF

**Screens:**
- **Home Page** (0, 1200)
- **Chat Interface** (400, 1200)
- **Map View** (800, 1200)
- **Feedback Page** (1200, 1200)
- **Profile Dashboard** (1600, 1200)

## Component Library Structure

### 🎨 Design System Components

#### Colors Frame
**Layout**: 4x3 grid
**Size**: 200x400

**Primary Colors:**
- Primary Blue (#2563EB)
- Secondary Green (#059669)
- Accent Orange (#F97316)

**Neutral Colors:**
- Dark Gray (#1F2937)
- Medium Gray (#6B7280)
- Light Gray (#F3F4F6)
- White (#FFFFFF)

**Semantic Colors:**
- Success (#10B981)
- Warning (#F59E0B)
- Error (#EF4444)
- Info (#3B82F6)

#### Typography Frame
**Layout**: Vertical stack
**Size**: 400x400

**Text Styles:**
- H1 - 48px, Bold, #1F2937
- H2 - 36px, Bold, #1F2937
- H3 - 30px, Semibold, #1F2937
- H4 - 24px, Semibold, #1F2937
- Body Large - 18px, Regular, #1F2937
- Body - 16px, Regular, #1F2937
- Body Small - 14px, Regular, #6B7280
- Caption - 12px, Regular, #6B7280

#### Components Frame
**Layout**: 3x4 grid
**Size**: 600x400

**Buttons:**
- Primary Button (200x48)
- Secondary Button (200x48)
- CTA Button (200x56)

**Form Elements:**
- Input Field (200x48)
- Text Area (200x120)
- Star Rating (200x32)

**Cards:**
- Route Card (200x160)
- Chat Message (200x80)
- Profile Card (200x120)

**Navigation:**
- Header (400x80)
- Mobile Menu (200x400)

#### Spacing Frame
**Layout**: Vertical stack
**Size**: 200x400

**Spacing Scale:**
- 4px, 8px, 12px, 16px, 20px, 24px, 32px, 48px, 64px

## Detailed Screen Layouts

### 🏠 Home Page (Desktop)

#### Header Section (0-80px)
**Components:**
- Logo: "AccessRide" (left, 24px, #2563EB)
- Navigation: Home, Map View, Feedback, Profile (right)
- Background: White
- Border: 1px #E5E7EB (bottom)

#### Hero Section (80-600px)
**Background**: Linear gradient (135deg, #2563EB 0%, #1D4ED8 100%)
**Content**: Centered, max-width: 800px
**Elements:**
- Heading: "Find Accessible Transport with AI" (48px, white, bold)
- Subheading: Descriptive text (18px, white, opacity: 0.9)
- CTA Button: "Start Chat" (orange, 18px, padding: 16px 32px)
- Decorative icons: 🚇 🚌 ♿ 🎯 (floating, opacity: 0.3)

#### Features Section (600-900px)
**Layout**: 3-column grid
**Cards**: 3 feature cards with icons and descriptions
- AI-Powered Chat (💬)
- Real-time Updates (🔄)
- Accessibility Focused (♿)

#### Footer Section (900-1024px)
**Background**: #1F2937
**Content**: Copyright, links, social media
**Text**: White, secondary: #9CA3AF

### 💬 Chat Interface (Desktop)

#### Chat Container (Right side, 400px width)
**Background**: White
**Border**: 1px #E5E7EB
**Border-radius**: 12px
**Shadow**: 0 10px 25px rgba(0, 0, 0, 0.1)

#### Chat Header (0-60px)
**Background**: #F3F4F6
**Border**: 1px #E5E7EB (bottom)
**Content**: "AI Assistant" (left), minimize/close buttons (right)

#### Chat Messages Area (60-800px)
**Scrollable area** with:
- Welcome message from AI
- User message bubbles (right, blue background)
- AI response bubbles (left, gray background)
- Route suggestion cards
- Map previews
- Cab booking panels

#### Input Area (800-1024px)
**Background**: #F9FAFB
**Border**: 1px #E5E7EB (top)
**Content**: Text input field (full width), send button (right)

### 🗺️ Map View (Desktop)

#### Header Section (0-80px)
**Same as home page** with "Map View" active

#### Map Container (80-1024px)
**Full-screen map** with:
- Custom markers for accessible stations (♿ in green circles)
- Regular station markers (● in blue circles)
- Search bar overlay (top-left, 300px)
- Filter panel (top-right, 250px)

#### Info Panel (Right side, 350px width)
**Slides in** when marker is clicked
**Content**: Station details, route suggestions, "Get Directions" button

### 📝 Feedback Page (Desktop)

#### Header Section (0-80px)
**Same as other pages** with "Feedback" active

#### Content Area (80-1024px)
**Centered form**, max-width: 600px
**Elements:**
- Title: "Help Us Improve AccessRide" (36px, blue)
- Subtitle: Descriptive text (18px, gray)
- Rating section with 5-star component
- Transport type selection with radio buttons
- Accessibility rating section
- Comments text area
- Submit button

### 👤 Profile Dashboard (Desktop)

#### Header Section (0-80px)
**Same as other pages** with "Profile" active

#### Dashboard Content (80-1024px)
**2-column layout**:
- **Left Column (400px)**: User profile card with avatar, name, email
- **Right Column (800px)**: Tabs for "Saved Routes", "Recent Trips", "Feedback History"

## Mobile Screen Adaptations

### 📱 Mobile Layouts

#### Header Section (0-60px)
**Simplified navigation**:
- Hamburger menu icon (left)
- Logo: "AccessRide" (center)
- Profile icon (right)

#### Content Areas
**Stacked layouts** instead of side-by-side
**Full-width elements** for better touch interaction
**Larger touch targets** (minimum 44px height)

#### Mobile-Specific Components
- **Bottom sheets** for additional content
- **Floating action buttons** for quick actions
- **Horizontal scrollable tabs** for navigation
- **Simplified forms** with larger inputs

## Component Specifications

### 🔘 Buttons

#### Primary Button
**Size**: 200x48px
**Background**: #2563EB
**Text**: White, 16px, font-weight: 600
**Border-radius**: 8px
**Padding**: 12px 24px
**Hover**: #1D4ED8
**Focus**: 2px outline #3B82F6

#### Secondary Button
**Size**: 200x48px
**Background**: Transparent
**Border**: 2px #2563EB
**Text**: #2563EB, 16px, font-weight: 600
**Border-radius**: 8px
**Padding**: 12px 24px
**Hover**: #F3F4F6

#### CTA Button
**Size**: 200x56px
**Background**: #F97316
**Text**: White, 18px, font-weight: 600
**Border-radius**: 12px
**Padding**: 16px 32px
**Hover**: #EA580C
**Shadow**: 0 4px 12px rgba(249, 115, 22, 0.3)

### 📝 Form Elements

#### Input Field
**Size**: 200x48px
**Border**: 2px #D1D5DB
**Border-radius**: 8px
**Padding**: 12px 16px
**Font-size**: 16px
**Focus**: Border #2563EB, outline #3B82F6

#### Text Area
**Size**: 200x120px
**Border**: 2px #D1D5DB
**Border-radius**: 8px
**Padding**: 16px
**Min-height**: 120px
**Focus**: Border #2563EB, outline #3B82F6

#### Star Rating
**Size**: 200x32px
**Star size**: 24px
**Color**: #F59E0B (gold)
**Spacing**: 4px between stars
**Hover**: Scale 1.1

### 🃏 Cards

#### Route Card
**Size**: 200x160px
**Background**: White
**Border**: 1px #E5E7EB
**Border-radius**: 12px
**Padding**: 20px
**Shadow**: 0 4px 6px rgba(0, 0, 0, 0.05)
**Hover**: Scale 1.02, shadow increase

#### Chat Message
**Size**: 200x80px
**User**: Right-aligned, #2563EB background, white text
**AI**: Left-aligned, #F3F4F6 background, dark text
**Border-radius**: 16px
**Padding**: 12px 16px
**Max-width**: 80%

#### Profile Card
**Size**: 200x120px
**Background**: White
**Border**: 1px #E5E7EB
**Border-radius**: 12px
**Padding**: 20px
**Content**: Avatar (80px circle), name, email, edit button

### 🧭 Navigation

#### Header
**Size**: 400x80px
**Background**: White
**Border**: 1px #E5E7EB (bottom)
**Content**: Logo (left), navigation links (right)
**Padding**: 16px 24px

#### Mobile Menu
**Size**: 200x400px
**Background**: White
**Shadow**: 0 4px 12px rgba(0, 0, 0, 0.15)
**Content**: Stacked navigation links
**Padding**: 16px

## Asset Organization

### 🎨 Icons
**Location**: Separate frame or component library
**Categories**:
- Transportation icons (🚇, 🚌, 🚕, ♿)
- UI icons (💬, 🗺️, ⭐, 📝, 👤, 🔍, ❌, ✅)
- Navigation icons (hamburger, back, close)

### 🖼️ Images
**Location**: Assets frame
**Types**:
- Logo variations
- Avatar placeholders
- Map placeholders
- Decorative elements

### 📐 Spacing & Grid
**Location**: Design System frame
**Elements**:
- 8px grid system
- Spacing scale (4px, 8px, 12px, 16px, 20px, 24px, 32px, 48px, 64px)
- Breakpoint indicators
- Layout guides

## Prototyping Setup

### 🔗 Interactions
**Page Transitions**:
- Fade in/out: 300ms ease-in-out
- Slide animations: 400ms ease-in-out

**Component Interactions**:
- Button hover: 200ms ease-in-out
- Card hover: Scale 1.02, 200ms ease-in-out
- Focus transitions: 150ms ease-in-out

### 📱 Responsive Behavior
**Breakpoints**:
- Mobile: 320px - 767px
- Tablet: 768px - 1023px
- Desktop: 1024px+

**Adaptations**:
- Stacked layouts on mobile
- Side-by-side on desktop
- Touch-friendly interactions
- Simplified navigation

## Export Settings

### 📤 Export Specifications
**Formats**: PNG, SVG, PDF
**Scales**: 1x, 2x, 3x
**Background**: Transparent where appropriate

### 🎯 Component Export
**Individual components** exported as separate files
**Icon sets** exported as SVG sprites
**Color palettes** exported as CSS variables

## Collaboration Features

### 👥 Team Access
**Viewer permissions** for stakeholders
**Editor permissions** for design team
**Comment system** for feedback and iterations

### 📋 Version Control
**Auto-save** enabled
**Version history** for major changes
**Branching** for experimental features

### 🔄 Handoff Preparation
**Inspect mode** enabled for developers
**CSS export** for styling
**Asset export** for implementation
**Prototype links** for user testing