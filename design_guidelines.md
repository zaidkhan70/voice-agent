# Design Guidelines: Futuristic Voice Agent Interface

## Design Approach
**Aesthetic Direction**: Sci-fi assistant screen with futuristic, high-tech visual language
**Primary Influences**: Sci-fi UI/UX from films like Iron Man's JARVIS, Her, Minority Report
**Core Principle**: Create an immersive, state-driven interface where every visual element responds to the conversation flow

## Layout Structure

### Fullscreen Canvas
- Single-page fullscreen layout (100vh)
- Dark gradient background: Navy → Deep Purple → Teal highlights
- Subtle radial or diagonal gradient flow
- Optional: Very light animated noise texture for depth (performance-conscious)

### Center Stage: Voice Orb
**Primary focal point** - Large circular orb occupying central viewport
- Size: ~300-400px diameter on desktop, ~250px on mobile
- Glowing neon border (cyan/blue/purple spectrum)
- Inner visualization: Vertical bars OR waveform lines that animate with voice
- State-based animations:
  - **Idle**: Slow, subtle pulse (breathing effect)
  - **Listening**: Active pulsing with moderate intensity
  - **Speaking**: Smooth, stronger wave animations

### Ambient Ring/Halo
Surrounding the orb: expanding concentric rings or blobby waveform
- Gentle scale and fade animations
- Changes intensity based on state (subtle when idle, prominent when active)

### Top Bar
Semi-transparent overlay bar
- **Left**: Logo or "Voice Agent" text
- **Right**: Connection status pill
  - Disconnected: Red/gray with icon
  - Connecting: Amber with spinner animation
  - Live: Green with pulsing dot

### Bottom Controls
Centered control cluster
- **Primary**: Large circular mic button with pulsing ring when active
- **Secondary**: Small icon buttons (Settings gear, End Session)
- Tooltips on hover for clarity

### Side Transcript Panel
Glassmorphism panel (left or right side)
- **Style**: Frosted glass effect with subtle blur and border glow
- **Content**: Conversation history with chat bubbles
  - User messages: Aligned to one side
  - Assistant messages: Aligned to opposite side
  - Each message: Rounded card with timestamp and role label
- **Live indicator**: Streaming partial STT text with animated ellipsis "..."
- Auto-scroll to latest message

## Typography
- **Primary Font**: Clean, modern sans-serif (Inter, Outfit, or Space Grotesk for futuristic feel)
- **State Labels**: Medium weight, 14-16px, uppercase tracking for emphasis
- **Transcript Text**: Regular weight, 14px for readability
- **Status Indicators**: Small, 12px, medium weight

## Spacing System
Use Tailwind units: **2, 4, 8, 12, 16** for consistent rhythm
- Component padding: p-4 to p-8
- Orb margins: Ample breathing room (m-16 or more)
- Panel padding: p-6 for transcript cards
- Button spacing: gap-4 between controls

## Component Library

### Voice Orb
- Circular container with border-gradient
- Inner waveform/bar visualization canvas
- Framer Motion: scale, opacity, and glow animations

### Status Indicators
- Pill-shaped badges with icons
- Color-coded (red, amber, green)
- Smooth transitions between states

### Transcript Bubbles
- Rounded rectangles (rounded-2xl)
- Semi-transparent background
- Subtle border glow matching theme
- Timestamp in smaller, muted text

### Control Buttons
- Circular buttons for primary actions
- Icon-based for minimal footprint
- Larger hit targets (48px minimum)
- Glowing hover states

## State Machine Visual Feedback
Display current state prominently near orb:
- **Idle**: "Tap to talk" with breathing glow
- **Connecting**: "Connecting..." with spinner
- **Listening**: "Listening..." with active pulse
- **Thinking**: "Thinking..." with subtle shimmer
- **Speaking**: "Speaking..." with wave animation

Text should be clearly visible, medium size (16-18px), centered below orb

## Animation Strategy (Framer Motion)
- **Orb Pulsing**: Scale 1 → 1.05 → 1, duration 2s, infinite loop
- **Ring Expansion**: Scale 1 → 1.3, opacity 1 → 0, staggered timing
- **State Transitions**: Smooth 300ms ease-in-out between all states
- **Transcript Entry**: Fade-in + slide-up animation (200ms)
- Performance: Use `transform` and `opacity` only for GPU acceleration

## Color Palette Philosophy
- **Backgrounds**: Dark navy to deep purple gradients (#0a0e27 → #1a0b2e)
- **Neon Accents**: Cyan (#00d4ff), Electric Blue (#0080ff), Purple (#a855f7)
- **Text**: White/off-white for primary, muted gray for secondary
- **States**: Green (#10b981) for active, Red (#ef4444) for error, Amber (#f59e0b) for processing
- **Glassmorphism**: rgba(255, 255, 255, 0.05) with backdrop-blur

## Responsive Considerations
- **Desktop**: Full layout with side panel visible
- **Tablet**: Consider stacking transcript panel below or making it toggleable
- **Mobile**: Vertical stack, smaller orb, collapsible transcript

## Accessibility
- Clear state announcements for screen readers
- High contrast for status indicators
- Keyboard navigation for all controls
- Focus indicators on interactive elements

This design creates an engaging, immersive experience that makes the AI conversation feel tangible through rich visual feedback and smooth state transitions.