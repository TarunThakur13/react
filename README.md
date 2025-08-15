# AccessRide - AI Accessible Transport Finder

A modern, accessibility-first web application that helps wheelchair users and mobility-challenged individuals find accessible public transport and ride-sharing options through an AI-powered chat assistant.

![AccessRide Logo](https://img.shields.io/badge/AccessRide-Accessibility%20First-blue?style=for-the-badge&logo=wheelchair)

## 🌟 Features

### Core Functionality
- **AI-Powered Chat Assistant**: Intelligent conversational interface that understands accessibility needs
- **Interactive Map View**: Real-time accessible transport stations with detailed accessibility information
- **Route Planning**: Comprehensive route suggestions with accessibility details and alternatives
- **Feedback System**: Multi-category rating system to continuously improve the service
- **User Profile & History**: Personal dashboard with saved routes, frequent destinations, and travel history

### Accessibility Features (WCAG AA Compliant)
- **High Contrast Design**: Carefully selected color palette ensuring readability
- **Large Touch Targets**: Minimum 48px touch targets for easy interaction
- **Keyboard Navigation**: Full keyboard accessibility with visible focus indicators
- **Screen Reader Support**: Semantic HTML with proper ARIA labels and roles
- **Voice Input**: Speech recognition for hands-free interaction
- **Reduced Motion Support**: Respects user's motion preferences
- **Skip Links**: Quick navigation for screen reader users

### Technical Highlights
- **Responsive Design**: Optimized for desktop, tablet, and mobile devices
- **Progressive Enhancement**: Works without JavaScript, enhanced with it
- **Modern CSS**: CSS Custom Properties, Grid, and Flexbox for flexible layouts
- **Interactive Components**: Star ratings, toggle switches, and dynamic content
- **Performance Optimized**: Minimal dependencies, efficient loading

## 🎨 Design System

### Color Palette
- **Primary Blue**: `#0066CC` - Trust and reliability
- **Primary Green**: `#16A085` - Accessibility and go
- **Accent Yellow**: `#F39C12` - Call-to-action and highlights
- **Accent Orange**: `#E67E22` - Secondary actions
- **Neutral Grays**: Semantic color scale for text and backgrounds

### Typography
- **Primary Font**: Inter - Clean, readable sans-serif
- **Heading Font**: Poppins - Friendly, approachable headings
- **Font Sizes**: Scalable system from 14px to 48px
- **Minimum Size**: 16px for body text (accessibility requirement)

### Spacing System
- **Base Unit**: 16px (1rem)
- **Scale**: 4px, 8px, 12px, 16px, 20px, 24px, 32px, 40px, 48px, 64px, 80px
- **Consistent Rhythm**: Maintains visual hierarchy and breathing room

## 📱 Pages & Components

### 1. Home Page (`index.html`)
- **Hero Section**: Compelling introduction with primary CTA
- **Features Overview**: Key benefits and value propositions
- **How It Works**: Step-by-step process explanation
- **Call-to-Action**: Multiple entry points to the chat assistant

### 2. AI Chat Assistant (`chat.html`)
- **Interactive Chat Interface**: Real-time conversation with AI
- **Quick Action Buttons**: Common requests for faster interaction
- **Voice Input**: Speech-to-text capability
- **Response Cards**: Rich displays for routes and ride options
  - Route suggestion cards with accessibility details
  - Cab booking cards with service integrations
  - Error handling with helpful suggestions

### 3. Map View (`map.html`)
- **Interactive Map**: Real-time transport station locations
- **Accessibility Filters**: Filter by accessibility level and transport type
- **Station Details**: Comprehensive accessibility information
- **Custom Markers**: Color-coded by accessibility level
- **Sidebar Navigation**: Searchable station list

### 4. Feedback & Reviews (`feedback.html`)
- **Quick Feedback**: Emoji-based initial feedback
- **Detailed Ratings**: Multi-category star rating system
  - Overall experience
  - Accessibility features
  - AI assistant helpfulness
  - Route information accuracy
- **Written Feedback**: Structured form with character counters
- **Recent Reviews**: Social proof from other users

### 5. Profile & History (`profile.html`)
- **User Dashboard**: Personal stats and quick overview
- **Saved Routes**: Manage frequently used routes
- **Frequent Destinations**: Quick access to common locations
- **Travel History**: Past journeys with completion status
- **Settings**: Accessibility preferences and account management

## 🚀 Getting Started

### Prerequisites
- Modern web browser (Chrome 90+, Firefox 88+, Safari 14+, Edge 90+)
- Local web server (for development)

### Installation

1. **Clone or Download**
   ```bash
   git clone <repository-url>
   cd accessride
   ```

2. **Install Dependencies** (Optional - for development server)
   ```bash
   npm install
   ```

3. **Start Development Server**
   ```bash
   npm run dev
   ```
   Or use any local server:
   ```bash
   python -m http.server 3000
   # or
   live-server --port=3000
   ```

4. **Open in Browser**
   Navigate to `http://localhost:3000`

### File Structure
```
accessride/
├── index.html          # Home page
├── chat.html           # AI chat assistant
├── map.html           # Interactive map view
├── feedback.html      # Feedback and reviews
├── profile.html       # User profile dashboard
├── styles.css         # Main stylesheet with design system
├── package.json       # Project configuration
└── README.md          # This file
```

## 🎯 Design Principles

### 1. Accessibility First
Every design decision prioritizes accessibility, ensuring the application is usable by people with diverse abilities and assistive technologies.

### 2. Progressive Enhancement
Core functionality works without JavaScript, with enhanced experiences when available.

### 3. Mobile-First Responsive
Designed primarily for mobile use with enhanced desktop experiences.

### 4. Performance-Conscious
Minimal dependencies, efficient CSS, and optimized assets for fast loading.

### 5. User-Centered Design
Iterative design based on user feedback and accessibility testing.

## 🔧 Technical Architecture

### Frontend Technologies
- **HTML5**: Semantic markup with accessibility attributes
- **CSS3**: Modern features including Grid, Flexbox, and Custom Properties
- **Vanilla JavaScript**: No framework dependencies for maximum compatibility
- **Progressive Web App Ready**: Structured for PWA conversion

### External Dependencies
- **Font Awesome**: Icons and visual elements
- **Google Fonts**: Typography (Inter and Poppins)
- **Leaflet.js**: Interactive maps (map view only)

### API Integration Points
- **Transportation APIs**: Real-time transit data
- **Mapping Services**: Location and routing data
- **Ride-sharing APIs**: Uber, Lyft integration
- **Speech Recognition**: Browser native or cloud services

## 🎨 Figma Design Reference

This codebase serves as a reference implementation for Figma designs. Key design elements include:

### Components Library
- **Buttons**: Primary, secondary, accent, outline, ghost variants
- **Form Elements**: Inputs, textareas, selects with focus states
- **Cards**: Route cards, destination cards, feedback cards
- **Navigation**: Header, tabs, breadcrumbs
- **Feedback**: Star ratings, toggle switches, progress indicators

### Layout Patterns
- **Hero Sections**: Gradient backgrounds with centered content
- **Dashboard Grids**: Responsive card layouts
- **Sidebar Layouts**: Collapsible navigation panels
- **Modal Patterns**: Overlays and focused interactions

### Accessibility Features
- **Focus Indicators**: High-contrast outlines
- **Color Contrast**: WCAG AA compliant ratios
- **Touch Targets**: Minimum 48px interactive areas
- **Typography Scale**: Clear hierarchy with readable sizes

## 🧪 Testing & Validation

### Accessibility Testing
- **Screen Reader**: NVDA, JAWS, VoiceOver compatibility
- **Keyboard Navigation**: Full functionality without mouse
- **Color Contrast**: WCAG AA compliance verification
- **ARIA Labels**: Proper semantic markup validation

### Cross-Browser Testing
- **Modern Browsers**: Chrome, Firefox, Safari, Edge
- **Mobile Browsers**: iOS Safari, Chrome Mobile
- **Responsive Design**: Multiple device sizes and orientations

### Performance Testing
- **Core Web Vitals**: Loading, interactivity, visual stability
- **Accessibility Performance**: Screen reader compatibility
- **Network Conditions**: Slow 3G and offline scenarios

## 🚀 Deployment

### Static Hosting Options
- **Netlify**: Drag and drop deployment
- **Vercel**: Git-based deployment
- **GitHub Pages**: Free hosting for public repositories
- **AWS S3**: Scalable static hosting

### Production Checklist
- [ ] Optimize images and assets
- [ ] Minify CSS and JavaScript
- [ ] Configure proper caching headers
- [ ] Set up HTTPS redirects
- [ ] Test accessibility compliance
- [ ] Validate HTML and CSS

## 🤝 Contributing

### Development Guidelines
1. **Accessibility First**: Every feature must be accessible
2. **Mobile-First**: Design for mobile, enhance for desktop
3. **Semantic HTML**: Use proper HTML elements and ARIA attributes
4. **Progressive Enhancement**: Core functionality without JavaScript
5. **Performance**: Minimize dependencies and optimize assets

### Code Standards
- **CSS**: Use CSS custom properties and modern features
- **JavaScript**: ES6+ with progressive enhancement
- **HTML**: Semantic markup with accessibility attributes
- **Comments**: Document complex interactions and accessibility features

## 📊 Browser Support

- **Chrome**: 90+ (full support)
- **Firefox**: 88+ (full support)
- **Safari**: 14+ (full support)
- **Edge**: 90+ (full support)
- **Mobile**: iOS 14+, Android 8+ (optimized)

## 📄 License

This project is created for demonstration and educational purposes. Design patterns and accessibility implementations can be freely adapted for similar projects.

## 🙏 Acknowledgments

- **Web Content Accessibility Guidelines (WCAG)**: Accessibility standards
- **MDN Web Docs**: Technical documentation and best practices
- **A11Y Project**: Accessibility resources and community
- **Font Awesome**: Icon library
- **Google Fonts**: Typography resources

---

**Built with ♿ accessibility in mind for everyone.**

For questions, suggestions, or accessibility feedback, please reach out to the development team.