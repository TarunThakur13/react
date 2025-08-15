# AccessRide - Figma Design Specification

## Project Structure

### Frames & Artboards

#### 1. Design System (Frame: "Design System")
- **Colors**: Primary palette, semantic colors, gradients
- **Typography**: All font styles and sizes
- **Components**: Buttons, inputs, cards, icons
- **Spacing**: Grid system and spacing scale

#### 2. Desktop Screens (Frame: "Desktop")
- Home Page (1440x1024)
- Chat Interface (1440x1024)
- Map View (1440x1024)
- Feedback Page (1440x1024)
- Profile Dashboard (1440x1024)

#### 3. Mobile Screens (Frame: "Mobile")
- Home Page (375x812)
- Chat Interface (375x812)
- Map View (375x812)
- Feedback Page (375x812)
- Profile Dashboard (375x812)

## Detailed Screen Specifications

### A. Home Page (index.html)

#### Desktop Layout (1440x1024)
**Header Section (0-80px)**
- Logo: "AccessRide" in primary blue (#2563EB), font-weight: 700, font-size: 24px
- Navigation: Right-aligned, horizontal menu
  - Home (active state)
  - Map View
  - Feedback
  - Profile
- Background: White, border-bottom: 1px #E5E7EB

**Hero Section (80-600px)**
- Background: Linear gradient (135deg, #2563EB 0%, #1D4ED8 100%)
- Content: Centered, max-width: 800px
- Heading: "Find Accessible Transport with AI" (white, 48px, font-weight: 700)
- Subheading: "Get real-time, accessible transport options tailored for wheelchair users and mobility-challenged individuals" (white, 18px, font-weight: 400, opacity: 0.9)
- CTA Button: "Start Chat" (orange #F97316, white text, 18px, padding: 16px 32px, border-radius: 12px)
- Decorative elements: Subtle geometric shapes in background

**Features Section (600-900px)**
- 3-column grid layout
- Feature cards with icons and descriptions:
  1. "AI-Powered Chat" (💬 icon)
  2. "Real-time Updates" (🔄 icon)
  3. "Accessibility Focused" (♿ icon)

**Footer Section (900-1024px)**
- Background: #1F2937
- Content: Copyright, links, social media
- Text: White, secondary text: #9CA3AF

#### Mobile Layout (375x812)
**Header Section (0-60px)**
- Hamburger menu icon (left)
- Logo: "AccessRide" (center)
- Profile icon (right)

**Hero Section (60-400px)**
- Same content as desktop but stacked vertically
- Heading: 32px (smaller for mobile)
- CTA Button: Full width with 16px margins

**Features Section (400-600px)**
- Single column layout
- Cards stacked vertically

**Footer Section (600-812px)**
- Simplified layout
- Stacked links

### B. AI Chat Widget (Core Experience)

#### Desktop Chat Interface (1440x1024)
**Chat Container (Right side, 400px width)**
- Background: White
- Border: 1px #E5E7EB
- Border-radius: 12px
- Shadow: 0 10px 25px rgba(0, 0, 0, 0.1)

**Chat Header (0-60px)**
- Title: "AI Assistant" (left)
- Minimize/Close buttons (right)
- Background: #F3F4F6
- Border-bottom: 1px #E5E7EB

**Chat Messages Area (60-800px)**
- Scrollable area
- Welcome message from AI
- User message bubbles (right-aligned, blue background)
- AI response bubbles (left-aligned, gray background)

**Message Types:**
1. **Text Response**: Simple gray bubble
2. **Route Suggestion Card**: White card with:
   - Route icon (🚇, 🚌, etc.)
   - Route name and duration
   - Accessibility info (♿ icon)
   - "View Details" button
3. **Map Preview**: Small embedded map (200x150px)
4. **Cab Booking Panel**: Orange card with:
   - Uber/Ola logo
   - ETA and fare
   - "Book Now" button
5. **Error Message**: Red-tinted card with helpful text

**Input Area (800-1024px)**
- Text input field (full width)
- Send button (right-aligned)
- Background: #F9FAFB
- Border-top: 1px #E5E7EB

#### Mobile Chat Interface (375x812)
**Full-screen chat experience**
- Header: Back button, "AI Assistant" title, close button
- Messages area: Full height minus header and input
- Input area: Fixed bottom, full width

### C. Map View Page (map.html)

#### Desktop Layout (1440x1024)
**Header Section (0-80px)**
- Same as home page
- Active state: "Map View"

**Map Container (80-1024px)**
- Full-screen map (Google Maps or similar)
- Custom markers for accessible stations:
  - Wheelchair icon (♿) in green circle
  - Regular station icon (●) in blue circle
- Search bar overlay (top-left, 300px width)
- Filter panel (top-right, 250px width):
  - Transport type checkboxes
  - Accessibility level filter
  - "Show My Location" button

**Info Panel (Right side, 350px width)**
- Slides in when marker is clicked
- Station name and accessibility details
- Route suggestions
- "Get Directions" button

#### Mobile Layout (375x812)
**Header Section (0-60px)**
- Back button, "Map View" title, filter icon

**Map Container (60-812px)**
- Full-screen map
- Floating action button (bottom-right):
  - My location
  - Search
  - Filters
- Bottom sheet for station info (slides up from bottom)

### D. Feedback & Review Page (feedback.html)

#### Desktop Layout (1440x1024)
**Header Section (0-80px)**
- Same as other pages
- Active state: "Feedback"

**Content Area (80-1024px)**
- Centered form, max-width: 600px
- Title: "Help Us Improve AccessRide" (36px, primary blue)
- Subtitle: "Your feedback helps us make transport more accessible" (18px, gray)

**Feedback Form:**
1. **Rating Section**:
   - "How would you rate your experience?" (24px)
   - 5-star rating component (large, accessible)
   - Stars: 24px size, gold color when selected

2. **Transport Type**:
   - Radio buttons for transport types
   - Icons for each type (🚇, 🚌, 🚕, etc.)

3. **Accessibility Rating**:
   - "How accessible was this route?" (24px)
   - 5-star rating component

4. **Comments Section**:
   - Large text area (min-height: 120px)
   - Placeholder: "Tell us about your experience..."

5. **Submit Button**:
   - Primary blue button
   - "Submit Feedback" text
   - Loading state

#### Mobile Layout (375x812)
**Header Section (0-60px)**
- Back button, "Feedback" title

**Content Area (60-812px)**
- Same form elements but full-width
- Larger touch targets
- Stacked layout

### E. Profile / History Dashboard (profile.html)

#### Desktop Layout (1440x1024)
**Header Section (0-80px)**
- Same as other pages
- Active state: "Profile"

**Dashboard Content (80-1024px)**
- 2-column layout

**Left Column (400px width):**
- User profile card:
  - Avatar placeholder (80px circle)
  - Name: "John Doe" (24px, bold)
  - Email: "john@example.com" (16px, gray)
  - "Edit Profile" button

**Right Column (800px width):**
- Tabs: "Saved Routes", "Recent Trips", "Feedback History"
- Content area with cards for each section

**Saved Routes Tab:**
- Route cards with:
  - Route name and destination
  - Transport type icons
  - Accessibility rating
  - "Use Route" button

**Recent Trips Tab:**
- Trip history cards with:
  - Date and time
  - Route details
  - Duration and cost
  - "Repeat Trip" button

**Feedback History Tab:**
- Feedback cards with:
  - Date submitted
  - Rating stars
  - Transport type
  - Brief comment preview

#### Mobile Layout (375x812)
**Header Section (0-60px)**
- Back button, "Profile" title

**Dashboard Content (60-812px)**
- Single column layout
- Profile card at top
- Tab navigation (horizontal scrollable)
- Cards stacked vertically

## Component Specifications

### Buttons
1. **Primary Button**:
   - Background: #2563EB
   - Text: White, 16px, font-weight: 600
   - Padding: 12px 24px
   - Border-radius: 8px
   - Hover: #1D4ED8

2. **Secondary Button**:
   - Background: Transparent
   - Border: 2px #2563EB
   - Text: #2563EB, 16px, font-weight: 600
   - Padding: 12px 24px
   - Border-radius: 8px

3. **CTA Button**:
   - Background: #F97316
   - Text: White, 18px, font-weight: 600
   - Padding: 16px 32px
   - Border-radius: 12px
   - Hover: #EA580C

### Cards
1. **Route Card**:
   - Background: White
   - Border: 1px #E5E7EB
   - Border-radius: 12px
   - Padding: 20px
   - Shadow: 0 4px 6px rgba(0, 0, 0, 0.05)

2. **Chat Message Card**:
   - User: Right-aligned, #2563EB background, white text
   - AI: Left-aligned, #F3F4F6 background, dark text
   - Border-radius: 16px
   - Padding: 12px 16px
   - Max-width: 80%

### Form Elements
1. **Input Field**:
   - Border: 2px #D1D5DB
   - Border-radius: 8px
   - Padding: 12px 16px
   - Font-size: 16px
   - Focus: Border #2563EB, outline #3B82F6

2. **Star Rating**:
   - Star size: 24px
   - Color: #F59E0B (gold)
   - Hover: Scale 1.1
   - Accessible: Proper ARIA labels

### Icons
- **Transport Icons**: 24px size, consistent style
- **UI Icons**: 20px size, stroke width: 2px
- **Accessibility Icons**: 20px size, green color (#059669)

## Accessibility Features

### Visual Design
- High contrast color combinations
- Large, readable fonts (minimum 16px)
- Clear visual hierarchy
- Consistent spacing and alignment

### Interactive Elements
- Minimum 44px touch targets
- Clear focus indicators
- Hover and active states
- Keyboard navigation support

### Content
- Semantic HTML structure
- Proper heading hierarchy
- Alt text for images
- Descriptive link text
- ARIA labels where needed

## Responsive Behavior

### Breakpoints
- Mobile: 320px - 767px
- Tablet: 768px - 1023px
- Desktop: 1024px+

### Mobile Adaptations
- Stacked layouts
- Full-width elements
- Larger touch targets
- Simplified navigation
- Bottom sheets for additional content

### Tablet Adaptations
- Hybrid layouts
- Side-by-side content where appropriate
- Touch-optimized interactions

## Animation Guidelines

### Micro-interactions
- Button hover: 200ms ease-in-out
- Card hover: Scale 1.02, 200ms ease-in-out
- Focus transitions: 150ms ease-in-out

### Page Transitions
- Fade in/out: 300ms ease-in-out
- Slide animations: 400ms ease-in-out

### Loading States
- Skeleton screens for content loading
- Spinner animations for actions
- Progress indicators for multi-step processes

## Implementation Notes

### CSS Framework
- Tailwind CSS for utility classes
- Custom CSS for complex components
- CSS Grid and Flexbox for layouts

### JavaScript Framework
- React for component structure
- React Router for navigation
- State management for chat and user data

### External Integrations
- Google Maps API for map functionality
- Chat API for AI assistant
- Transport APIs for real-time data

### Performance Considerations
- Lazy loading for images and components
- Optimized bundle sizes
- Efficient re-rendering
- Progressive enhancement