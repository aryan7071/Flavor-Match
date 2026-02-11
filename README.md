# 🍜 FlavorMatch - Cyberpunk Food Matcher

<div align="center">

![FlavorMatch Banner](https://img.shields.io/badge/FlavorMatch-Cyberpunk%20Edition-00ffff?style=for-the-badge)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-f7df1e?style=for-the-badge&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)

**A Tinder-style food decision app with a stunning cyberpunk aesthetic**

[View Demo](#-features) • [How It Works](#-how-it-works) • [Tournament Submission](#-tournament-problem-statement)

</div>

---

## 📋 Tournament Problem Statement

### Problem #2: The "Tinder-Style" Food/Movie Matcher

**Feature Use-case:** Netflix recommendations or dating app swipe cards.

**Goal:** Build a decision making app for groups who cannot decide what to eat or watch.

**Core Logic Requirements:**
- ✅ Create a static JSON file like `movies.json` or `food.json`
- ✅ Each item should have tags such as `spicy`, `cheap`, `fast`
- ✅ If a user selected tag matches an item, treat it as a "match"

**Interface Requirements:**
- ✅ A card stack showing one item at a time
- ✅ Two buttons: "Nah" (red) and "Yeah" (green)
- ✅ Clicking a button removes the card and shows the next one

**Creativity Bonus:**
- ✅ Retro arcade style
- ✅ Hologram theme
- ✅ Sound effects for matches

---

## 🎯 Project Overview

FlavorMatch is a futuristic food decision-making application that helps users discover their perfect meal through an interactive swipe-based interface. Built with a cyberpunk aesthetic, it combines the familiar Tinder-style card swiping mechanism with advanced filtering and matching algorithms.

### 🎨 Design Philosophy

- **Cyberpunk Aesthetic**: Neon colors (cyan, magenta, yellow), grid backgrounds, and glowing effects
- **Retro-Futuristic**: Combines 80s arcade vibes with modern UI/UX principles
- **Immersive Experience**: Animated backgrounds, particles, scanline effects, and holographic elements

---

## ✨ Features

### 🎮 Core Functionality

1. **Preference Selection System**
   - **Vibe Selection**: Hangry, Fancy, Comfort, Adventure
   - **Budget Categories**: Budget ($5-$15), Moderate ($15-$30), Premium ($30+), Unlimited
   - **Tag Filters**: Spicy, Fast, Healthy, Comfort, Filling, Fresh, Shareable, Exotic

2. **Tinder-Style Card Swiping**
   - Swipe left (✗) to pass
   - Swipe right (♥) to match
   - Swipe up (⭐) for super like
   - Drag cards with mouse/touch
   - Keyboard controls (arrow keys)

3. **Real-Time Statistics**
   - Total swipes counter
   - Match count tracker
   - Combo multiplier
   - Remaining cards indicator

4. **Match System**
   - Visual match overlay with animations
   - Match celebration effects
   - Comprehensive results screen
   - Total cost calculator

### 🎨 Visual Effects

- **Animated Grid Background**: Perspective-based cyberpunk grid
- **Floating Particles**: 30+ animated particle effects
- **Glitch Text Effects**: Dynamic logo animations
- **Neon Glow**: Custom shadows and borders
- **Scanline Overlays**: Retro CRT monitor effects
- **Holographic Animations**: Floating and rotating elements
- **Sonar Pulse**: Button interaction feedback

### 🔊 Audio Features

- **Click Sounds**: Square wave synthesis for UI interactions
- **Match Sounds**: Ascending frequency for successful matches
- **Swipe Sounds**: Sawtooth wave for card movements
- **Web Audio API**: Dynamic sound generation

---

## 🏗️ Technical Architecture

### File Structure

```
flavormatch-cyberpunk.html
├── HTML Structure
│   ├── Welcome Screen
│   ├── Preference Selection (3 Steps)
│   ├── Game Screen (Card Swiper)
│   ├── Results Screen
│   └── Match Overlay
├── CSS Styling
│   ├── Cyberpunk Theme Variables
│   ├── Animations & Keyframes
│   ├── Responsive Design
│   └── Component Styles
└── JavaScript Logic
    ├── Food Database (JSON Array)
    ├── Game State Management
    ├── Filtering Algorithm
    ├── Swipe Detection
    ├── Audio Synthesis
    └── UI Controllers
```

### 📊 Data Structure

The food database is stored as a JSON array with the following schema:

```javascript
{
  id: Number,              // Unique identifier
  name: String,            // Display name (e.g., "RAMEN NEXUS")
  emoji: String,           // Visual representation
  description: String,     // Flavor description
  tags: Array<String>,     // ["spicy", "fast", "comfort", "cheap"]
  vibes: Array<String>,    // ["hangry", "comfort", "adventure"]
  price: Number,           // Price in dollars
  category: String         // Food category
}
```

**Example Entry:**
```javascript
{
  id: 1,
  name: "RAMEN NEXUS",
  emoji: "🍜",
  description: "Digital noodles in quantum broth",
  tags: ["spicy", "fast", "comfort", "cheap"],
  vibes: ["hangry", "comfort", "adventure"],
  price: 12,
  category: "asian"
}
```

### 🧮 Matching Algorithm

The app uses a multi-tier filtering system:

1. **Primary Filter**: Vibe matching (required)
2. **Secondary Filter**: Budget constraints
3. **Tertiary Sort**: Tag priority ranking
4. **Fallback Logic**: Ensures cards are always available

```javascript
// Pseudo-code
filteredDeck = foods.filter(food => {
  if (!vibeMatches) return false;
  if (!budgetMatches) return false;
  return true;
});

// Sort by tag matches
if (userHasTags) {
  sort by number of matching tags (descending);
} else {
  randomize order;
}
```

---

## 🎮 How It Works

### User Journey

```
┌─────────────────┐
│  Welcome Screen │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│   Step 1: Vibe  │  → Select mood (Hangry/Fancy/Comfort/Adventure)
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Step 2: Budget │  → Choose price range
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│   Step 3: Tags  │  → Optional: Select preferences
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│   Game Screen   │  → Swipe through filtered cards
│                 │     • Left = Pass (✗)
│                 │     • Right = Match (♥)
│                 │     • Up = Super Like (⭐)
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Results Screen  │  → View all matches
│                 │     • Total swipes
│                 │     • Match count
│                 │     • Total cost
└─────────────────┘
```

### Interaction Methods

| Method | Action | Result |
|--------|--------|--------|
| **Mouse Drag** | Drag card left/right | Swipe animation + card removal |
| **Touch Swipe** | Swipe on mobile | Same as mouse drag |
| **Button Click** | Click ✗ or ♥ buttons | Instant card removal |
| **Keyboard** | ← (left) → (right) ↑ (up) | Quick navigation |

---

## 💻 Code Highlights

### 1. Dynamic Card Rendering

```javascript
function showCard() {
  const food = currentDeck[currentIndex];
  const card = document.createElement('div');
  card.className = 'food-card';
  card.innerHTML = `
    <div class="swipe-indicator nope">NOPE</div>
    <div class="swipe-indicator like">LIKE</div>
    <div class="card-emoji">${food.emoji}</div>
    <div class="card-name">${food.name}</div>
    <div class="card-description">${food.description}</div>
    <div class="card-price">$${food.price}</div>
  `;
  cardArea.appendChild(card);
}
```

### 2. Swipe Detection Logic

```javascript
function drag(e) {
  const diff = currentX - startX;
  card.style.transform = `translateX(${diff}px) rotate(${diff * 0.1}deg)`;
  
  if (diff > 50) {
    card.classList.add('swiping-right');  // Show LIKE indicator
  } else if (diff < -50) {
    card.classList.add('swiping-left');   // Show NOPE indicator
  }
}
```

### 3. Web Audio Synthesis

```javascript
function playSound(type) {
  const oscillator = audioCtx.createOscillator();
  switch(type) {
    case 'match':
      oscillator.frequency.value = 800;
      oscillator.frequency.exponentialRampToValueAtTime(2000, audioCtx.currentTime + 0.4);
      break;
  }
  oscillator.start();
}
```

### 4. CSS Animations

```css
@keyframes neonFlow {
  0% { background-position: 0% center; }
  100% { background-position: 200% center; }
}

.logo {
  background: linear-gradient(90deg, var(--neon-cyan), var(--neon-magenta));
  animation: neonFlow 3s linear infinite;
}
```

---

## 🎨 Design System

### Color Palette

| Color | Hex Code | Usage |
|-------|----------|-------|
| **Neon Cyan** | `#00ffff` | Primary accent, borders, glows |
| **Neon Magenta** | `#ff00ff` | Secondary accent, matches |
| **Neon Yellow** | `#ffff00` | Super likes, highlights |
| **Neon Green** | `#00ff41` | Success states, like button |
| **Dark Background** | `#0a0a0f` | Main background |
| **Card Background** | `#1a1a2e` | Card containers |

### Typography

- **Heading Font**: Orbitron (900 weight) - Futuristic display
- **Body Font**: Rajdhani (300-700 weights) - Clean readability
- **Uppercase Styling**: Used throughout for cyberpunk aesthetic

### Spacing System

- Base unit: `10px`
- Card padding: `40px`
- Section gaps: `15px - 30px`
- Border radius: `15px - 30px` (rounded corners)

---

## 📱 Responsive Design

### Breakpoints

```css
/* Mobile Devices */
@media (max-width: 768px) {
  .logo { font-size: 42px; }
  .option-grid { grid-template-columns: 1fr; }
  .card-area { height: 450px; }
  .action-btn { width: 65px; height: 65px; }
}
```

### Mobile Optimizations

- Touch-friendly button sizes (65px minimum)
- Single-column preference grids
- Adjusted card heights for smaller screens
- Passive event listeners for smooth scrolling

---

## 🚀 Performance Optimizations

1. **CSS Animations**: Hardware-accelerated transforms
2. **Event Delegation**: Efficient event handling
3. **Lazy Rendering**: Cards created on-demand
4. **Audio Context**: Reused across interactions
5. **No External Dependencies**: Pure vanilla JavaScript

---

## 🎯 Tournament Compliance Checklist

### Core Requirements
- ✅ **Static JSON Data**: 15 food items with tags
- ✅ **Tag Matching Logic**: Multi-tier filtering algorithm
- ✅ **Card Stack Interface**: One card at a time
- ✅ **Red/Green Buttons**: ✗ (Nah) and ♥ (Yeah)
- ✅ **Card Removal**: Smooth animation on button click

### Creativity Bonuses
- ✅ **Retro Arcade Style**: Neon colors, pixel-perfect design
- ✅ **Hologram Theme**: Floating animations, scanlines, glitch effects
- ✅ **Sound Effects**: Web Audio API synthesis for all interactions

### Beginner Hints Implemented
- ✅ **querySelector**: Used throughout for DOM manipulation
- ✅ **Array Storage**: `currentDeck` array stores cards
- ✅ **CSS display:none**: Screen management system

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| **HTML5** | Semantic structure, accessibility |
| **CSS3** | Animations, gradients, transforms |
| **JavaScript ES6+** | Logic, interactivity, state management |
| **Web Audio API** | Dynamic sound synthesis |
| **CSS Grid & Flexbox** | Responsive layouts |
| **CSS Animations** | Keyframe animations, transitions |

---

## 🎮 Usage Instructions

### Getting Started

1. **Open the HTML file** in any modern web browser
2. **Click "INITIALIZE"** on the welcome screen
3. **Select your preferences**:
   - Choose a vibe (required)
   - Select a budget (required)
   - Add optional tags
4. **Click "ENGAGE 🚀"** to start swiping
5. **Swipe through cards**:
   - Drag left/right with mouse or touch
   - Click ✗ or ♥ buttons
   - Use arrow keys on keyboard
6. **View your matches** at the end

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `←` | Swipe left (Pass) |
| `→` | Swipe right (Match) |
| `↑` | Super like |

---

## 🏆 Unique Selling Points

### What Makes This Stand Out

1. **Cohesive Theme**: Every element reinforces the cyberpunk aesthetic
2. **Smooth Animations**: Professional-grade transitions and effects
3. **Multiple Interaction Methods**: Mouse, touch, keyboard support
4. **Smart Filtering**: Intelligent fallback logic ensures cards always display
5. **Audio Feedback**: Dynamic sound synthesis adds arcade feel
6. **Attention to Detail**: Custom scrollbars, glitch effects, particle systems

### Innovation Beyond Requirements

- **Super Like Feature**: Third interaction option (⭐)
- **Combo System**: Tracks consecutive matches
- **Remaining Counter**: Shows progress through deck
- **Results Analytics**: Comprehensive match statistics
- **Animated Backgrounds**: Multiple layered visual effects

---

## 📊 Statistics & Metrics

### Food Database Stats

- **Total Items**: 15 unique food options
- **Categories**: 9 (Asian, American, Italian, Mexican, etc.)
- **Price Range**: $8 - $85
- **Tag Variety**: 12 different tags
- **Vibe Options**: 4 mood categories

### Performance Metrics

- **Load Time**: Instant (no external dependencies)
- **File Size**: ~25KB (single HTML file)
- **Animations**: 60fps smooth transitions
- **Browser Support**: Chrome, Firefox, Safari, Edge

---

## 🎨 Visual Examples

### Screen Progression

```
Welcome Screen          Preference Selection       Game Screen
┌─────────────┐        ┌─────────────┐          ┌─────────────┐
│  FLAVOR     │        │ SELECT VIBE │          │   STATS     │
│  MATCH      │   →    │             │    →     │ ┌─────────┐ │
│             │        │ [Hangry]    │          │ │  CARD   │ │
│ [START] ─── │        │ [Fancy]     │          │ │  STACK  │ │
└─────────────┘        └─────────────┘          │ └─────────┘ │
                                                 │   ✗ ⭐ ♥   │
                                                 └─────────────┘
```

---

## 🔮 Future Enhancements

Potential features for version 2.0:

- [ ] User accounts and saved preferences
- [ ] Restaurant location integration
- [ ] Group voting mode (multiplayer)
- [ ] AI-powered recommendations
- [ ] Social sharing of matches
- [ ] Custom food database upload
- [ ] Dark/light theme toggle
- [ ] Achievement system

---

## 🐛 Known Issues & Limitations

- Audio requires user interaction to start (browser security)
- No persistent storage (refreshing resets state)
- Static food database (no external API)
- Limited to single-player mode

---

## 📝 License & Credits

### Created For
Tournament Submission - Problem #2: Tinder-Style Food Matcher

### Technologies
- Pure HTML5, CSS3, JavaScript (ES6+)
- Web Audio API
- No external libraries or frameworks

### Fonts
- Orbitron (Google Fonts)
- Rajdhani (Google Fonts)

---

## 🎓 Learning Outcomes

This project demonstrates:

- ✅ Advanced CSS animations and effects
- ✅ Event-driven programming
- ✅ State management in vanilla JS
- ✅ Responsive design principles
- ✅ Web Audio API usage
- ✅ User experience design
- ✅ Algorithm implementation (filtering/sorting)

---

## 📞 Contact & Support

For questions, suggestions, or issues:

- Check the inline code comments for detailed explanations
- Review the console logs for debugging information
- Inspect the browser DevTools for visual debugging

---

<div align="center">

**Built with 💙 for the Tournament**

*Swipe into the future of food decisions* 🚀

</div>
