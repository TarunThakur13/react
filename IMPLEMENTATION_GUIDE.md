# AccessRide Implementation Guide

## Project Setup

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn
- Git

### Initial Setup
```bash
# Navigate to the React project directory
cd 07reactrouter

# Install additional dependencies
npm install @heroicons/react lucide-react framer-motion react-hook-form
npm install @headlessui/react @tailwindcss/forms
npm install react-hot-toast react-query
npm install leaflet react-leaflet
npm install @types/leaflet
```

## Project Structure

```
src/
├── components/
│   ├── common/
│   │   ├── Button.jsx
│   │   ├── Input.jsx
│   │   ├── Card.jsx
│   │   ├── Header.jsx
│   │   └── Footer.jsx
│   ├── chat/
│   │   ├── ChatWidget.jsx
│   │   ├── MessageBubble.jsx
│   │   ├── RouteCard.jsx
│   │   └── CabBookingPanel.jsx
│   ├── map/
│   │   ├── MapView.jsx
│   │   ├── CustomMarker.jsx
│   │   └── InfoPanel.jsx
│   ├── feedback/
│   │   ├── FeedbackForm.jsx
│   │   └── StarRating.jsx
│   └── profile/
│       ├── ProfileDashboard.jsx
│       ├── UserCard.jsx
│       └── HistoryCard.jsx
├── pages/
│   ├── HomePage.jsx
│   ├── ChatPage.jsx
│   ├── MapPage.jsx
│   ├── FeedbackPage.jsx
│   └── ProfilePage.jsx
├── hooks/
│   ├── useChat.js
│   ├── useMap.js
│   └── useAuth.js
├── utils/
│   ├── constants.js
│   ├── helpers.js
│   └── api.js
├── styles/
│   └── globals.css
└── App.jsx
```

## Design System Implementation

### Tailwind Configuration
```javascript
// tailwind.config.js
module.exports = {
  content: ["./src/**/*.{js,jsx,ts,tsx}"],
  theme: {
    extend: {
      colors: {
        primary: {
          50: '#eff6ff',
          500: '#2563eb',
          600: '#1d4ed8',
          700: '#1e40af',
        },
        secondary: {
          500: '#059669',
          600: '#047857',
        },
        accent: {
          500: '#f97316',
          600: '#ea580c',
        },
        neutral: {
          50: '#f9fafb',
          100: '#f3f4f6',
          200: '#e5e7eb',
          300: '#d1d5db',
          400: '#9ca3af',
          500: '#6b7280',
          600: '#4b5563',
          700: '#374151',
          800: '#1f2937',
          900: '#111827',
        }
      },
      fontFamily: {
        sans: ['Inter', 'system-ui', 'sans-serif'],
      },
      fontSize: {
        'h1': ['3rem', { lineHeight: '1.2', letterSpacing: '-0.025em' }],
        'h2': ['2.25rem', { lineHeight: '1.2', letterSpacing: '-0.025em' }],
        'h3': ['1.875rem', { lineHeight: '1.2', letterSpacing: '-0.025em' }],
        'h4': ['1.5rem', { lineHeight: '1.2', letterSpacing: '-0.025em' }],
        'body-lg': ['1.125rem', { lineHeight: '1.5' }],
        'body': ['1rem', { lineHeight: '1.5' }],
        'body-sm': ['0.875rem', { lineHeight: '1.5' }],
        'caption': ['0.75rem', { lineHeight: '1.4', letterSpacing: '0.025em' }],
      },
      spacing: {
        '18': '4.5rem',
        '88': '22rem',
      },
      borderRadius: {
        'xl': '12px',
        '2xl': '16px',
      },
      boxShadow: {
        'soft': '0 4px 6px rgba(0, 0, 0, 0.05)',
        'medium': '0 10px 25px rgba(0, 0, 0, 0.1)',
        'strong': '0 4px 12px rgba(0, 0, 0, 0.15)',
      },
      animation: {
        'fade-in': 'fadeIn 0.3s ease-in-out',
        'slide-up': 'slideUp 0.4s ease-in-out',
        'scale-in': 'scaleIn 0.2s ease-in-out',
      },
      keyframes: {
        fadeIn: {
          '0%': { opacity: '0' },
          '100%': { opacity: '1' },
        },
        slideUp: {
          '0%': { transform: 'translateY(20px)', opacity: '0' },
          '100%': { transform: 'translateY(0)', opacity: '1' },
        },
        scaleIn: {
          '0%': { transform: 'scale(0.95)', opacity: '0' },
          '100%': { transform: 'scale(1)', opacity: '1' },
        },
      },
    },
  },
  plugins: [
    require('@tailwindcss/forms'),
  ],
}
```

### Global Styles
```css
/* src/styles/globals.css */
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  html {
    font-family: 'Inter', system-ui, sans-serif;
  }
  
  body {
    @apply bg-neutral-50 text-neutral-800;
  }
  
  /* Focus styles for accessibility */
  *:focus {
    @apply outline-none ring-2 ring-primary-500 ring-offset-2;
  }
  
  /* High contrast focus for better accessibility */
  *:focus-visible {
    @apply ring-2 ring-primary-500 ring-offset-2;
  }
}

@layer components {
  /* Button components */
  .btn-primary {
    @apply bg-primary-500 text-white font-semibold py-3 px-6 rounded-lg 
           hover:bg-primary-600 focus:ring-2 focus:ring-primary-500 focus:ring-offset-2
           transition-colors duration-200;
  }
  
  .btn-secondary {
    @apply bg-transparent border-2 border-primary-500 text-primary-500 
           font-semibold py-3 px-6 rounded-lg hover:bg-neutral-100
           focus:ring-2 focus:ring-primary-500 focus:ring-offset-2
           transition-colors duration-200;
  }
  
  .btn-cta {
    @apply bg-accent-500 text-white font-semibold py-4 px-8 rounded-xl text-lg
           hover:bg-accent-600 focus:ring-2 focus:ring-accent-500 focus:ring-offset-2
           transition-all duration-200 shadow-lg hover:shadow-xl;
  }
  
  /* Card components */
  .card {
    @apply bg-white border border-neutral-200 rounded-xl p-5 shadow-soft
           hover:shadow-medium transition-shadow duration-200;
  }
  
  .card-hover {
    @apply hover:scale-[1.02] transition-transform duration-200;
  }
  
  /* Input components */
  .input-field {
    @apply w-full border-2 border-neutral-300 rounded-lg px-4 py-3 text-base
           focus:border-primary-500 focus:ring-2 focus:ring-primary-500 focus:ring-offset-2
           transition-colors duration-200;
  }
  
  .input-field:focus {
    @apply outline-none;
  }
  
  /* Chat message components */
  .message-user {
    @apply bg-primary-500 text-white rounded-2xl px-4 py-3 max-w-[80%] ml-auto;
  }
  
  .message-ai {
    @apply bg-neutral-100 text-neutral-800 rounded-2xl px-4 py-3 max-w-[80%];
  }
  
  /* Navigation components */
  .nav-link {
    @apply text-neutral-500 font-medium px-4 py-3 hover:text-primary-500
           transition-colors duration-200;
  }
  
  .nav-link-active {
    @apply text-primary-500 font-semibold;
  }
}

@layer utilities {
  /* Accessibility utilities */
  .sr-only {
    @apply absolute w-px h-px p-0 -m-px overflow-hidden whitespace-nowrap border-0;
  }
  
  /* Animation utilities */
  .animate-fade-in {
    animation: fadeIn 0.3s ease-in-out;
  }
  
  .animate-slide-up {
    animation: slideUp 0.4s ease-in-out;
  }
  
  .animate-scale-in {
    animation: scaleIn 0.2s ease-in-out;
  }
}
```

## Component Implementation

### Common Components

#### Button Component
```jsx
// src/components/common/Button.jsx
import React from 'react';
import { motion } from 'framer-motion';

const Button = ({ 
  children, 
  variant = 'primary', 
  size = 'md', 
  disabled = false,
  onClick,
  className = '',
  type = 'button',
  ...props 
}) => {
  const baseClasses = 'font-semibold rounded-lg transition-all duration-200 focus:ring-2 focus:ring-offset-2 disabled:opacity-50 disabled:cursor-not-allowed';
  
  const variants = {
    primary: 'bg-primary-500 text-white hover:bg-primary-600 focus:ring-primary-500',
    secondary: 'bg-transparent border-2 border-primary-500 text-primary-500 hover:bg-neutral-100 focus:ring-primary-500',
    cta: 'bg-accent-500 text-white hover:bg-accent-600 focus:ring-accent-500 shadow-lg hover:shadow-xl',
    ghost: 'bg-transparent text-neutral-600 hover:text-neutral-800 focus:ring-neutral-500',
  };
  
  const sizes = {
    sm: 'px-4 py-2 text-sm',
    md: 'px-6 py-3 text-base',
    lg: 'px-8 py-4 text-lg',
  };
  
  const classes = `${baseClasses} ${variants[variant]} ${sizes[size]} ${className}`;
  
  return (
    <motion.button
      className={classes}
      onClick={onClick}
      disabled={disabled}
      type={type}
      whileHover={{ scale: disabled ? 1 : 1.02 }}
      whileTap={{ scale: disabled ? 1 : 0.98 }}
      {...props}
    >
      {children}
    </motion.button>
  );
};

export default Button;
```

#### Header Component
```jsx
// src/components/common/Header.jsx
import React, { useState } from 'react';
import { Link, useLocation } from 'react-router-dom';
import { motion, AnimatePresence } from 'framer-motion';
import { Menu, X, User } from 'lucide-react';

const Header = () => {
  const [isMobileMenuOpen, setIsMobileMenuOpen] = useState(false);
  const location = useLocation();
  
  const navigation = [
    { name: 'Home', path: '/' },
    { name: 'Map View', path: '/map' },
    { name: 'Feedback', path: '/feedback' },
    { name: 'Profile', path: '/profile' },
  ];
  
  const isActive = (path) => location.pathname === path;
  
  return (
    <header className="bg-white border-b border-neutral-200 sticky top-0 z-50">
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="flex justify-between items-center h-20">
          {/* Logo */}
          <Link to="/" className="flex items-center">
            <motion.div
              className="text-2xl font-bold text-primary-500"
              whileHover={{ scale: 1.05 }}
            >
              AccessRide
            </motion.div>
          </Link>
          
          {/* Desktop Navigation */}
          <nav className="hidden md:flex space-x-8">
            {navigation.map((item) => (
              <Link
                key={item.name}
                to={item.path}
                className={`nav-link ${isActive(item.path) ? 'nav-link-active' : ''}`}
              >
                {item.name}
              </Link>
            ))}
          </nav>
          
          {/* Mobile menu button */}
          <div className="md:hidden">
            <button
              onClick={() => setIsMobileMenuOpen(!isMobileMenuOpen)}
              className="p-2 rounded-md text-neutral-600 hover:text-neutral-800 focus:ring-2 focus:ring-primary-500"
            >
              {isMobileMenuOpen ? <X size={24} /> : <Menu size={24} />}
            </button>
          </div>
        </div>
      </div>
      
      {/* Mobile Navigation */}
      <AnimatePresence>
        {isMobileMenuOpen && (
          <motion.div
            initial={{ opacity: 0, height: 0 }}
            animate={{ opacity: 1, height: 'auto' }}
            exit={{ opacity: 0, height: 0 }}
            className="md:hidden bg-white border-t border-neutral-200"
          >
            <div className="px-4 py-6 space-y-4">
              {navigation.map((item) => (
                <Link
                  key={item.name}
                  to={item.path}
                  className={`block px-4 py-3 text-base font-medium rounded-lg transition-colors duration-200 ${
                    isActive(item.path)
                      ? 'text-primary-500 bg-primary-50'
                      : 'text-neutral-600 hover:text-neutral-800 hover:bg-neutral-50'
                  }`}
                  onClick={() => setIsMobileMenuOpen(false)}
                >
                  {item.name}
                </Link>
              ))}
            </div>
          </motion.div>
        )}
      </AnimatePresence>
    </header>
  );
};

export default Header;
```

### Home Page Implementation
```jsx
// src/pages/HomePage.jsx
import React from 'react';
import { motion } from 'framer-motion';
import { Link } from 'react-router-dom';
import { MessageCircle, RefreshCw, Wheelchair } from 'lucide-react';
import Button from '../components/common/Button';
import Header from '../components/common/Header';
import Footer from '../components/common/Footer';

const HomePage = () => {
  const features = [
    {
      icon: MessageCircle,
      title: 'AI-Powered Chat',
      description: 'Get personalized transport recommendations through our intelligent chat assistant.',
      color: 'bg-primary-500',
    },
    {
      icon: RefreshCw,
      title: 'Real-time Updates',
      description: 'Stay informed with live updates on routes, delays, and accessibility status.',
      color: 'bg-secondary-500',
    },
    {
      icon: Wheelchair,
      title: 'Accessibility Focused',
      description: 'Designed specifically for wheelchair users and mobility-challenged individuals.',
      color: 'bg-accent-500',
    },
  ];
  
  const containerVariants = {
    hidden: { opacity: 0 },
    visible: {
      opacity: 1,
      transition: {
        staggerChildren: 0.2,
      },
    },
  };
  
  const itemVariants = {
    hidden: { opacity: 0, y: 20 },
    visible: {
      opacity: 1,
      y: 0,
      transition: {
        duration: 0.5,
      },
    },
  };
  
  return (
    <div className="min-h-screen bg-white">
      <Header />
      
      {/* Hero Section */}
      <section className="relative bg-gradient-to-br from-primary-500 to-primary-600 text-white overflow-hidden">
        {/* Decorative background elements */}
        <div className="absolute inset-0 opacity-10">
          <div className="absolute top-20 left-20 text-6xl">🚇</div>
          <div className="absolute top-40 right-20 text-6xl">🚌</div>
          <div className="absolute bottom-40 left-40 text-6xl">♿</div>
          <div className="absolute bottom-20 right-40 text-6xl">🎯</div>
        </div>
        
        <div className="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-24">
          <motion.div
            className="text-center max-w-4xl mx-auto"
            variants={containerVariants}
            initial="hidden"
            animate="visible"
          >
            <motion.h1
              className="text-5xl md:text-6xl font-bold mb-6"
              variants={itemVariants}
            >
              Find Accessible Transport with AI
            </motion.h1>
            
            <motion.p
              className="text-xl md:text-2xl mb-8 opacity-90"
              variants={itemVariants}
            >
              Get real-time, accessible transport options tailored for wheelchair users and mobility-challenged individuals
            </motion.p>
            
            <motion.div variants={itemVariants}>
              <Link to="/chat">
                <Button variant="cta" size="lg">
                  Start Chat
                </Button>
              </Link>
            </motion.div>
          </motion.div>
        </div>
      </section>
      
      {/* Features Section */}
      <section className="py-24 bg-neutral-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <motion.div
            className="text-center mb-16"
            initial={{ opacity: 0, y: 20 }}
            whileInView={{ opacity: 1, y: 0 }}
            viewport={{ once: true }}
            transition={{ duration: 0.5 }}
          >
            <h2 className="text-4xl font-bold text-neutral-800 mb-4">
              Why Choose AccessRide?
            </h2>
            <p className="text-xl text-neutral-600 max-w-3xl mx-auto">
              Our platform is built with accessibility in mind, providing you with the tools you need for seamless travel.
            </p>
          </motion.div>
          
          <div className="grid md:grid-cols-3 gap-8">
            {features.map((feature, index) => (
              <motion.div
                key={feature.title}
                className="card card-hover"
                initial={{ opacity: 0, y: 20 }}
                whileInView={{ opacity: 1, y: 0 }}
                viewport={{ once: true }}
                transition={{ duration: 0.5, delay: index * 0.1 }}
              >
                <div className={`w-12 h-12 ${feature.color} rounded-full flex items-center justify-center mb-6`}>
                  <feature.icon className="w-6 h-6 text-white" />
                </div>
                <h3 className="text-2xl font-semibold text-neutral-800 mb-4">
                  {feature.title}
                </h3>
                <p className="text-neutral-600 leading-relaxed">
                  {feature.description}
                </p>
              </motion.div>
            ))}
          </div>
        </div>
      </section>
      
      <Footer />
    </div>
  );
};

export default HomePage;
```

### Chat Interface Implementation
```jsx
// src/components/chat/ChatWidget.jsx
import React, { useState, useRef, useEffect } from 'react';
import { motion, AnimatePresence } from 'framer-motion';
import { Send, Minimize2, X, MessageCircle } from 'lucide-react';
import MessageBubble from './MessageBubble';
import RouteCard from './RouteCard';
import CabBookingPanel from './CabBookingPanel';

const ChatWidget = ({ isOpen, onClose, onMinimize }) => {
  const [messages, setMessages] = useState([
    {
      id: 1,
      type: 'ai',
      content: 'Hello! I\'m your AI assistant. I can help you find accessible transport options. Where would you like to go today?',
      timestamp: new Date(),
    },
  ]);
  const [inputValue, setInputValue] = useState('');
  const [isTyping, setIsTyping] = useState(false);
  const messagesEndRef = useRef(null);
  
  const scrollToBottom = () => {
    messagesEndRef.current?.scrollIntoView({ behavior: 'smooth' });
  };
  
  useEffect(() => {
    scrollToBottom();
  }, [messages]);
  
  const handleSendMessage = async () => {
    if (!inputValue.trim()) return;
    
    const userMessage = {
      id: Date.now(),
      type: 'user',
      content: inputValue,
      timestamp: new Date(),
    };
    
    setMessages(prev => [...prev, userMessage]);
    setInputValue('');
    setIsTyping(true);
    
    // Simulate AI response
    setTimeout(() => {
      const aiResponse = generateAIResponse(inputValue);
      setMessages(prev => [...prev, aiResponse]);
      setIsTyping(false);
    }, 1500);
  };
  
  const generateAIResponse = (userInput) => {
    // This would be replaced with actual AI integration
    const responses = [
      {
        type: 'text',
        content: 'I found several accessible transport options for you. Let me show you the best routes.',
      },
      {
        type: 'route',
        content: {
          name: 'Metro Line A',
          duration: '15 min',
          accessibility: 'Fully accessible',
          icon: '🚇',
        },
      },
      {
        type: 'cab',
        content: {
          provider: 'Uber',
          eta: '5 min',
          fare: '$12-15',
        },
      },
    ];
    
    return {
      id: Date.now() + 1,
      type: 'ai',
      content: responses[Math.floor(Math.random() * responses.length)],
      timestamp: new Date(),
    };
  };
  
  const handleKeyPress = (e) => {
    if (e.key === 'Enter' && !e.shiftKey) {
      e.preventDefault();
      handleSendMessage();
    }
  };
  
  if (!isOpen) {
    return (
      <motion.button
        className="fixed bottom-6 right-6 w-14 h-14 bg-accent-500 text-white rounded-full shadow-lg hover:shadow-xl flex items-center justify-center"
        whileHover={{ scale: 1.1 }}
        whileTap={{ scale: 0.9 }}
        onClick={() => onClose(false)}
      >
        <MessageCircle size={24} />
      </motion.button>
    );
  }
  
  return (
    <motion.div
      className="fixed bottom-6 right-6 w-96 h-[600px] bg-white rounded-xl shadow-strong border border-neutral-200 flex flex-col"
      initial={{ opacity: 0, scale: 0.8, y: 20 }}
      animate={{ opacity: 1, scale: 1, y: 0 }}
      exit={{ opacity: 0, scale: 0.8, y: 20 }}
    >
      {/* Chat Header */}
      <div className="bg-neutral-100 px-4 py-3 rounded-t-xl border-b border-neutral-200 flex items-center justify-between">
        <h3 className="font-semibold text-neutral-800">AI Assistant</h3>
        <div className="flex space-x-2">
          <button
            onClick={onMinimize}
            className="p-1 rounded hover:bg-neutral-200 transition-colors"
          >
            <Minimize2 size={16} />
          </button>
          <button
            onClick={() => onClose(false)}
            className="p-1 rounded hover:bg-neutral-200 transition-colors"
          >
            <X size={16} />
          </button>
        </div>
      </div>
      
      {/* Messages Area */}
      <div className="flex-1 overflow-y-auto p-4 space-y-4">
        <AnimatePresence>
          {messages.map((message) => (
            <motion.div
              key={message.id}
              initial={{ opacity: 0, y: 10 }}
              animate={{ opacity: 1, y: 0 }}
              exit={{ opacity: 0, y: -10 }}
            >
              {message.content.type === 'route' ? (
                <RouteCard route={message.content} />
              ) : message.content.type === 'cab' ? (
                <CabBookingPanel booking={message.content} />
              ) : (
                <MessageBubble message={message} />
              )}
            </motion.div>
          ))}
        </AnimatePresence>
        
        {isTyping && (
          <motion.div
            className="flex items-center space-x-2 text-neutral-500"
            initial={{ opacity: 0 }}
            animate={{ opacity: 1 }}
          >
            <div className="flex space-x-1">
              <div className="w-2 h-2 bg-neutral-400 rounded-full animate-bounce"></div>
              <div className="w-2 h-2 bg-neutral-400 rounded-full animate-bounce" style={{ animationDelay: '0.1s' }}></div>
              <div className="w-2 h-2 bg-neutral-400 rounded-full animate-bounce" style={{ animationDelay: '0.2s' }}></div>
            </div>
            <span className="text-sm">AI is typing...</span>
          </motion.div>
        )}
        
        <div ref={messagesEndRef} />
      </div>
      
      {/* Input Area */}
      <div className="p-4 border-t border-neutral-200">
        <div className="flex space-x-2">
          <input
            type="text"
            value={inputValue}
            onChange={(e) => setInputValue(e.target.value)}
            onKeyPress={handleKeyPress}
            placeholder="Type your message..."
            className="flex-1 input-field"
            disabled={isTyping}
          />
          <button
            onClick={handleSendMessage}
            disabled={!inputValue.trim() || isTyping}
            className="p-3 bg-primary-500 text-white rounded-lg hover:bg-primary-600 disabled:opacity-50 disabled:cursor-not-allowed transition-colors"
          >
            <Send size={20} />
          </button>
        </div>
      </div>
    </motion.div>
  );
};

export default ChatWidget;
```

## Routing Setup

```jsx
// src/App.jsx
import React from 'react';
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';
import { Toaster } from 'react-hot-toast';
import HomePage from './pages/HomePage';
import ChatPage from './pages/ChatPage';
import MapPage from './pages/MapPage';
import FeedbackPage from './pages/FeedbackPage';
import ProfilePage from './pages/ProfilePage';

function App() {
  return (
    <Router>
      <div className="App">
        <Routes>
          <Route path="/" element={<HomePage />} />
          <Route path="/chat" element={<ChatPage />} />
          <Route path="/map" element={<MapPage />} />
          <Route path="/feedback" element={<FeedbackPage />} />
          <Route path="/profile" element={<ProfilePage />} />
        </Routes>
        
        <Toaster
          position="top-right"
          toastOptions={{
            duration: 4000,
            style: {
              background: '#363636',
              color: '#fff',
            },
            success: {
              duration: 3000,
              iconTheme: {
                primary: '#10B981',
                secondary: '#fff',
              },
            },
            error: {
              duration: 5000,
              iconTheme: {
                primary: '#EF4444',
                secondary: '#fff',
              },
            },
          }}
        />
      </div>
    </Router>
  );
}

export default App;
```

## Accessibility Implementation

### ARIA Labels and Roles
```jsx
// Example of accessible form implementation
const FeedbackForm = () => {
  return (
    <form role="form" aria-labelledby="feedback-title">
      <h2 id="feedback-title">Help Us Improve AccessRide</h2>
      
      <fieldset>
        <legend>How would you rate your experience?</legend>
        <div role="radiogroup" aria-label="Experience rating">
          {[1, 2, 3, 4, 5].map((rating) => (
            <input
              key={rating}
              type="radio"
              id={`rating-${rating}`}
              name="rating"
              value={rating}
              aria-label={`${rating} star rating`}
            />
          ))}
        </div>
      </fieldset>
      
      <label htmlFor="comments">Additional comments:</label>
      <textarea
        id="comments"
        name="comments"
        aria-describedby="comments-help"
        placeholder="Tell us about your experience..."
      />
      <p id="comments-help">Share your thoughts to help us improve our service.</p>
    </form>
  );
};
```

### Keyboard Navigation
```jsx
// Example of keyboard-accessible component
const AccessibleButton = ({ children, onClick, ...props }) => {
  const handleKeyDown = (e) => {
    if (e.key === 'Enter' || e.key === ' ') {
      e.preventDefault();
      onClick();
    }
  };
  
  return (
    <button
      onClick={onClick}
      onKeyDown={handleKeyDown}
      role="button"
      tabIndex={0}
      {...props}
    >
      {children}
    </button>
  );
};
```

## Performance Optimization

### Lazy Loading
```jsx
import React, { Suspense, lazy } from 'react';

const MapPage = lazy(() => import('./pages/MapPage'));
const ProfilePage = lazy(() => import('./pages/ProfilePage'));

// In your router
<Suspense fallback={<div>Loading...</div>}>
  <Route path="/map" element={<MapPage />} />
  <Route path="/profile" element={<ProfilePage />} />
</Suspense>
```

### Memoization
```jsx
import React, { memo, useMemo, useCallback } from 'react';

const ExpensiveComponent = memo(({ data, onUpdate }) => {
  const processedData = useMemo(() => {
    return data.map(item => ({ ...item, processed: true }));
  }, [data]);
  
  const handleClick = useCallback(() => {
    onUpdate(processedData);
  }, [processedData, onUpdate]);
  
  return (
    <div onClick={handleClick}>
      {/* Component content */}
    </div>
  );
});
```

## Testing Setup

### Unit Tests
```jsx
// src/components/__tests__/Button.test.jsx
import { render, screen, fireEvent } from '@testing-library/react';
import Button from '../common/Button';

describe('Button Component', () => {
  test('renders with correct text', () => {
    render(<Button>Click me</Button>);
    expect(screen.getByText('Click me')).toBeInTheDocument();
  });
  
  test('calls onClick when clicked', () => {
    const handleClick = jest.fn();
    render(<Button onClick={handleClick}>Click me</Button>);
    
    fireEvent.click(screen.getByText('Click me'));
    expect(handleClick).toHaveBeenCalledTimes(1);
  });
  
  test('applies correct variant styles', () => {
    render(<Button variant="cta">CTA Button</Button>);
    const button = screen.getByText('CTA Button');
    expect(button).toHaveClass('bg-accent-500');
  });
});
```

### Integration Tests
```jsx
// src/pages/__tests__/HomePage.test.jsx
import { render, screen } from '@testing-library/react';
import { BrowserRouter } from 'react-router-dom';
import HomePage from '../HomePage';

const renderWithRouter = (component) => {
  return render(
    <BrowserRouter>
      {component}
    </BrowserRouter>
  );
};

describe('HomePage', () => {
  test('renders hero section', () => {
    renderWithRouter(<HomePage />);
    expect(screen.getByText('Find Accessible Transport with AI')).toBeInTheDocument();
  });
  
  test('renders features section', () => {
    renderWithRouter(<HomePage />);
    expect(screen.getByText('AI-Powered Chat')).toBeInTheDocument();
    expect(screen.getByText('Real-time Updates')).toBeInTheDocument();
    expect(screen.getByText('Accessibility Focused')).toBeInTheDocument();
  });
  
  test('has accessible navigation', () => {
    renderWithRouter(<HomePage />);
    expect(screen.getByRole('navigation')).toBeInTheDocument();
  });
});
```

## Deployment

### Build Configuration
```json
// package.json scripts
{
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "test": "vitest",
    "test:coverage": "vitest --coverage",
    "lint": "eslint . --ext js,jsx --report-unused-disable-directives --max-warnings 0",
    "lint:fix": "eslint . --ext js,jsx --fix"
  }
}
```

### Environment Variables
```env
# .env.production
VITE_API_URL=https://api.accessride.com
VITE_GOOGLE_MAPS_API_KEY=your_google_maps_api_key
VITE_CHAT_API_URL=https://chat.accessride.com
```

### Docker Configuration
```dockerfile
# Dockerfile
FROM node:18-alpine as build

WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production

COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

This implementation guide provides a comprehensive foundation for building the AccessRide web application with modern React practices, accessibility features, and performance optimizations. The design system is fully implemented with Tailwind CSS, and all components follow the Figma specifications while maintaining high accessibility standards.