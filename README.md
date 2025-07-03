3D Solar System Simulation
Overview
This is a web-based 3D solar system simulation built with vanilla JavaScript and Three.js (r134). It visualizes the Sun, eight planets (Mercury to Neptune) with realistic orbits, Saturn’s rings, and a dynamic starfield with moving and twinkling stars. Interactive controls allow speed adjustments, pausing, theme switching, and camera zooming, with a responsive design for mobile devices.
Features

3D Scene:
Sun: Yellow sphere (radius 4) with glowing corona and pulsing effect.
Planets: Eight planets with NASA 2k textures (or fallback colors), increased sizes (e.g., Earth radius 2.0).
Saturn’s Rings: Semi-transparent ring (inner radius 5.5, outer radius 8).


Background:
15,000 distant stars and 2,000 bright stars in layered cubes (2000x2000x2000 and 1500x1500x1500).
Stars twinkle (size pulses 80-100% of base size: 0.8 for distant, 1.5 for bright) and move slowly (0.1-0.5 units/second) with random velocities, wrapping within cubes.
Five shooting stars with trails, resetting after 50-150 frames.


Controls:
Sliders for per-planet speed (0-0.1 for visual mode, 0-10 for realistic mode).
Buttons: Pause/resume, dark/light mode toggle, realistic/visual speeds toggle.
Responsive control panel (90-95% width on mobile).


Interactivity:
Tooltips: Hover over planets, Sun, or rings to show names.
Camera: Click planets/rings to zoom; click Sun to reset view.
Labels: 2D labels follow planets on-screen.


Speed Modes:
Visual: Adjustable speeds (e.g., Mercury: 0.02 radians/second).
Realistic: Orbital periods (e.g., Mercury: 0.241 years) scaled 1000x.



Setups to run

Download: Save index.html from the project repository.
Host:Use any web server  or an IDE extension like VS Code’s Live Server.

Open: Navigate to http://localhost:8000/index.html in a modern browser (Chrome, Firefox, Safari).
Dependencies: Three.js is loaded via CDN (https://cdnjs.cloudflare.com/ajax/libs/three.js/r134/three.min.js). Ensure internet access for textures.

Usage

View: The simulation loads with orbiting planets, twinkling and moving stars, and shooting stars.
Interact:
Sliders: Adjust planet speeds in the control panel.
Buttons:
Pause/resume: Toggle animation.
Dark/light mode: Switch background (dark: #000, light: #f0f0f0).
Realistic/visual speeds: Toggle speed modes.


Hover: Show tooltips for planets, Sun, or rings.
Click: Zoom to planets/rings; reset view on Sun.


Mobile: Controls scale for smaller screens.

Implementation Details

Code: Single index.html with embedded CSS and JavaScript.
Starfield:
Movement: Stars update via position += velocity * deltaTime, wrapping at cube edges.
Twinkling: Sizes adjust with baseSize * (0.8 + 0.2 * sin(elapsedTime * 2 + twinkleOffset)).
Uses BufferAttribute for positions, sizes, velocities.


Animation: requestAnimationFrame and THREE.Clock for smooth updates; paused when isPaused is true.
Planets: Orbit via x = distance * cos(angle), z = distance * sin(angle).
Interactivity: THREE.Raycaster for hover/click; vanilla JavaScript for events.
Responsive CSS: Media queries for mobile screens (< 600px, < 400px).
