# Planning Guide

A playful Valentine's Day application that asks "Will you be my valentine?" with a mischievous twist - the "No" button playfully evades the cursor while the "Yes" button remains easy to click, creating a delightful interaction that inevitably leads to acceptance.

**Experience Qualities**:
1. **Playful** - The interface should feel like a lighthearted game with charming, unexpected interactions
2. **Romantic** - Soft colors, hearts, and Valentine's aesthetics create a sweet, loving atmosphere
3. **Delightful** - Surprising button behaviors and celebratory reactions reward user interaction

**Complexity Level**: Micro Tool (single-purpose application)
- This is a focused, single-interaction experience designed purely for Valentine's Day fun with one core mechanic

## Essential Features

### Evasive "No" Button
- **Functionality**: The "No" button moves away when the user tries to hover or click it
- **Purpose**: Creates a playful, impossible challenge that gently guides users toward "Yes"
- **Trigger**: Mouse hover over the "No" button
- **Progression**: User sees question → Attempts to click "No" → Button moves to random position → User chases button → Eventually clicks "Yes"
- **Success criteria**: Button successfully evades cursor and relocates to random positions on screen

### Accepting "Yes" Button
- **Functionality**: A stable, clickable button that triggers a celebration
- **Purpose**: Provides the intended outcome with satisfying feedback
- **Trigger**: Click on "Yes" button
- **Progression**: User clicks "Yes" → Celebratory animation plays → Hearts/confetti appear → Success message displays
- **Success criteria**: Click registers reliably and triggers visible celebration

### Valentine's Question Display
- **Functionality**: Central question text asking "Will you be my valentine?"
- **Purpose**: Sets the romantic context for the interaction
- **Trigger**: Page load
- **Progression**: Page loads → Question appears with gentle animation
- **Success criteria**: Text is clearly readable and visually appealing

## Edge Case Handling

- **Mobile Touch**: On touch devices, "No" button moves on touch start instead of hover
- **Small Screens**: Button repositioning ensures buttons stay within viewport bounds
- **Rapid Clicking**: Multiple rapid clicks on "Yes" only trigger celebration once
- **Button Boundary**: "No" button never moves off-screen or overlaps with "Yes" button

## Design Direction

The design should evoke feelings of joy, warmth, and romantic playfulness - like receiving a handmade valentine card with a sweet surprise inside. Think soft pastels, gentle animations, and charming typography that feels personal and heartfelt.

## Color Selection

A romantic Valentine's palette with soft pinks, warm reds, and gentle purples against a dreamy background.

- **Primary Color**: Deep romantic pink `oklch(0.65 0.19 350)` - represents love and warmth, used for the "Yes" button
- **Secondary Colors**: Soft blush `oklch(0.95 0.05 350)` for backgrounds and gentle accents; light cream `oklch(0.98 0.02 60)` for cards
- **Accent Color**: Vibrant red `oklch(0.60 0.22 25)` - attention-grabbing for hearts and celebratory elements
- **Foreground/Background Pairings**: 
  - Background (Soft gradient pink `oklch(0.95 0.05 350)` to lavender `oklch(0.92 0.08 310)`): Deep text `oklch(0.30 0.05 350)` - Ratio 11.2:1 ✓
  - Primary Pink Button `oklch(0.65 0.19 350)`: White text `oklch(1 0 0)` - Ratio 5.1:1 ✓
  - Card `oklch(0.98 0.02 60)`: Deep text `oklch(0.30 0.05 350)` - Ratio 14.5:1 ✓

## Font Selection

Typefaces should feel romantic yet modern - combining a playful display font for the question with clean, readable text for buttons.

- **Typographic Hierarchy**:
  - H1 (Main Question): Pacifico 48px/tight - cursive, romantic feel
  - Buttons: DM Sans 18px/medium weight - clean, modern, highly readable
  - Success Message: Pacifico 32px/relaxed - celebratory and warm

## Animations

Animations should feel light and bouncy, like floating hearts - gentle entrance animations for the question, smooth elastic motion for the evading button, and celebratory burst effects when "Yes" is clicked with floating hearts and scale animations.

## Component Selection

- **Components**: 
  - Card component for the main container with soft shadows
  - Button components with custom hover states (Yes: scale up, No: escape animation)
  - Custom heart icons from Phosphor Icons for decorative elements
- **Customizations**: 
  - Custom moving button logic with absolute positioning and random coordinate generation
  - Celebratory confetti/hearts animation using framer-motion
  - Gradient background with repeating heart pattern
- **States**: 
  - Buttons: Yes (default, hover with scale, clicked with celebration), No (default, fleeing on hover, impossible to click)
  - Application: Initial state, Celebrating state (after Yes clicked)
- **Icon Selection**: Heart icon (filled and regular) from Phosphor Icons
- **Spacing**: Generous padding (p-8 to p-12) for card, gap-6 between elements, comfortable touch targets (min 48px)
- **Mobile**: Stack elements vertically, reduce font sizes slightly, ensure "No" button movement stays within safe viewport bounds with larger margins
