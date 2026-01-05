# Requirements Document: Color Ball Merge Mobile Game

## 1. Project Overview
The goal is to develop a hyper-casual mobile game named "Color Ball Merge" using React JS. The game follows the "Suika Game" or "2048" mechanics where balls of the same color/size merge into a larger, different-colored ball when they collide.

## 2. Core Game Mechanics
### 2.1 Ball Dropping
- Players can move the current ball horizontally at the top of the screen.
- Players tap or release to drop the ball into the play area.
- Physics-based gravity pulls the ball down.

### 2.2 Merging Logic
- When two balls of the **same color and size** collide, they merge.
- Merging produces a single ball of the **next size and color** in the progression sequence.
- The new ball appears at the midpoint of the collision.
- Merging awards points to the player.

### 2.3 Game Board
- A rectangular container with a fixed width and height (optimized for mobile screens).
- A "Game Over" line at the top. If balls remain above this line for a certain duration (e.g., 3 seconds), the game ends.

### 2.4 Progression Sequence
Balls follow a specific size and color hierarchy:
1. Small - White
2. Medium-Small - Yellow
3. Medium - Green
4. Medium-Large - Blue
5. Large - Red
6. Extra Large - Purple
7. Giant - Rainbow (Final Form)

## 3. UI/UX Requirements
### 3.1 Main Game Screen
- **Score Display:** Real-time update of the current score.
- **Next Ball Preview:** Shows the color/size of the ball that will be available after the current one is dropped.
- **Reset Button:** Allows the player to restart the game.

### 3.2 Animations
- Smooth ball dropping animation.
- Visual effect (e.g., subtle pop or glow) when two balls merge.
- Shaking effect when a ball hits the "Game Over" threshold.

### 3.3 Mobile Optimization
- Responsive layout that fits various screen sizes.
- Touch controls (drag to move, release to drop).

## 4. Technical Requirements
- **Framework:** React JS.
- **Styling:** CSS3 (Flexbox/Grid for layout, Transitions/Animations for effects).
- **Physics Engine:** Optional (Matter.js or custom lightweight circular collision logic).
- **State Management:** React Hooks (`useState`, `useReducer`, `useContext`).

## 5. Scoring System
- Points are awarded based on the level of the merged balls.
- Example:
  - White + White = 2 points
  - Yellow + Yellow = 4 points
  - ...up to Rainbow merge = 100 points.

## 6. Functional Requirements
- **Requirement 1:** The system shall accurately detect collisions between circular objects.
- **Requirement 2:** The system shall prevent balls from clipping through the walls or floor.
- **Requirement 3:** The system shall manage the "Next Ball" queue randomly but potentially weighted towards smaller sizes.
- **Requirement 4:** The system shall save the high score locally using `localStorage`.

## 7. Non-Functional Requirements
- **Performance:** Maintain 60 FPS for smooth physics and animations.
- **Accessibility:** High contrast between ball colors for better visibility.
- **Size:** Optimized bundle size for fast loading on mobile devices.
