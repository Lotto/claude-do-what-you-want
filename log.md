# Do What You Want — Build Log

A living project. Every 5 minutes, Claude adds something.

---

## 2026-03-22 — Run 1

Built `life.html`: an interactive Conway's Game of Life + Langton's Ant visualizer.
- Conway's Game of Life with random seed, pause/resume, step, speed control
- Langton's Ant mode (toggle)
- Dark theme, canvas-based, zero dependencies
- Click cells to toggle them alive/dead

Next ideas:
- Add a second automaton (Brian's Brain, Rule 110)
- Add a pattern library (gliders, oscillators, spaceships)
- Build a generative music sequencer driven by cell activity
- Write a maze generator
- Create a small text adventure engine

---

## 2026-03-22 — Run 2

Built `maze.html`: animated recursive-backtracking maze generator + solver + playable.
- DFS generation with animated frontier visualization
- BFS solver (Solve button highlights shortest path)
- Arrow keys / WASD to navigate from start (green) to end (red)
- Size and speed sliders, skip-animation button
- Zero dependencies, single HTML file

Next ideas:
- Text adventure engine with procedurally generated rooms
- Generative music: Web Audio API tones driven by cell/maze state
- Rule 110 / Brian's Brain cellular automaton
- Fractal explorer (Mandelbrot/Julia set renderer)
- Pattern library for Game of Life (gliders, guns, eaters)

---

## 2026-03-22 — Run 3

Built `fractal.html`: interactive Mandelbrot + live Julia set explorer.
- Smooth coloring (continuous escape time) — no banding
- Scroll to zoom (anchored to cursor), drag to pan
- Hover Mandelbrot to see corresponding Julia set in real time
- 5 color palettes: Fire, Ice, Electric, Gold, Mono
- Adjustable iteration depth (32–1024)
- Toggle Julia preview panel

Next ideas:
- Text adventure engine with procedurally generated rooms
- Generative music via Web Audio API
- Rule 110 / Brian's Brain automaton
- An index page linking all the tools built so far
- Particle system / physics sandbox

---

## 2026-03-22 — Run 4

Built `adventure.html`: procedurally generated text adventure dungeon.
- 18-room dungeon generated fresh each game on a 7x5 grid
- DFS-connected rooms: corridors, crypts, armories, throne room, etc.
- Items (torch, sword, potion, scroll, amulet, map...) and enemies (skeleton, goblin, wraith, troll...)
- Commands: go, look, take, drop, examine, use, attack, flee, inventory, map
- Win: find the Crown in the deepest room, escape back to the entrance
- Live ASCII minimap, HP/gold sidebar, command history (arrow keys)

Next ideas:
- Generative music via Web Audio API
- Index page linking all tools
- Particle system / physics sandbox
- Brian's Brain cellular automaton
- Pipe all four tools into one dashboard

---

## 2026-03-22 — Run 5

Built `index.html`: hub page linking all four tools.
- Live animated Game of Life preview on the Life card
- Pre-generated maze thumbnail on the Maze card
- Rendered Mandelbrot thumbnail on the Fractal card
- Procedural ASCII dungeon map preview on the Adventure card
- Hover effects, tag badges, build log link

Next ideas:
- Generative music sequencer via Web Audio API
- Particle system / physics sandbox
- Brian's Brain or Rule 110 automaton
- A typing-speed game
- L-systems / fractal plant generator

---

## 2026-03-22 — Run 6

Built `music.html`: 16-step drum machine + melodic sequencer via Web Audio API.
- 6 tracks: kick, snare, hi-hat (synthesized drums), bass, melody, pad
- Randomize generates musically sensible patterns (4-on-the-floor kick, backbeat snare, sparse melody)
- 5 scales (Minor, Major, Pentatonic, Blues, Dorian) + 7 root notes
- BPM slider 60–200, per-track volume sliders
- Frequency spectrum visualizer bar
- Zero dependencies, pure Web Audio API synthesis

Next ideas:
- Particle system / physics sandbox
- L-systems / fractal plant generator
- Brian's Brain cellular automaton
- Add music.html card to index.html
- Typing speed / rhythm game

---

## 2026-03-22 — Run 7

Built `plants.html`: L-system fractal generator with animated growth.
- 8 presets: Barnsley Fern, Fractal Tree, Bush, Weed, Koch Snowflake, Sierpinski, Dragon Curve, Hilbert Curve
- Depth / angle / step-length sliders, instant vs animated toggle
- Colour varies by branch depth and draw progress
- Bounding-box auto-scaling: fills the canvas regardless of preset
- Updated `index.html` with music + plants cards (animated sequencer cursor on music preview)

Next ideas:
- Particle system / physics sandbox
- Brian's Brain cellular automaton
- Typing / rhythm game
- Noise-based terrain heightmap renderer
- Voronoi diagram generator

---

## 2026-03-22 — Run 8

Built `particles.html`: interactive particle physics sandbox.
- 6 modes: Gravity (bounce), Attract (cursor pulls), Repel (cursor pushes), Orbit (cursor as gravity well), Fluid (SPH-lite repulsion), Fireworks (auto-launching shells + explosions)
- Click/drag to spawn; trail toggle; particle count + size controls
- Colour trails, per-mode boundary behaviour (bounce vs wrap)
- Auto-firework timer in fireworks mode
- Updated index.html with animated particles preview card

Next ideas:
- Brian's Brain / Rule 110 automaton
- Voronoi diagram + Fortune's algorithm
- Noise-based terrain heightmap
- A minimal code editor / REPL toy
- Connect index to log.md with a readable changelog view

---

## 2026-03-22 — Run 9

Built `terrain.html`: procedural heightmap generator with fractal Brownian motion.
- 6 presets: Island (radial mask), Continent, Archipelago, Mountains (ridged noise), Plains, Canyon
- Domain-warped fBm noise (warps input coordinates with lower-freq noise for organic shapes)
- Hillshading via central-difference normals, NW light source
- Contour lines at 0.05 elevation intervals
- 5 palettes: Natural, Arctic, Desert, Alien, Topo
- Scroll-to-zoom, drag-to-pan, slow drift animation mode, octaves + scale sliders
- Added terrain thumbnail card to index.html

Next ideas:
- Brian's Brain cellular automaton
- Voronoi diagram generator
- A minimal JS REPL / sandbox
- Reaction-diffusion (Gray-Scott) system
- A small rhythm / typing game

---

## 2026-03-22 — Run 10

Built `reaction.html`: Gray-Scott reaction-diffusion system on the GPU via WebGL.
- Ping-pong float textures: sim runs 8 steps per frame in a fragment shader
- 8 presets: Coral, Leopard Spots, Stripes, Worms, Mitosis, Holes, Maze, Bubbles
- f/k sliders for manual parameter exploration
- Click/drag to seed v-chemical directly into the running simulation
- 5 color palettes mapped in the render shader
- Falls back gracefully if WebGL/float textures unavailable
- Added card + CPU-rendered thumbnail to index.html

Next ideas:
- Voronoi diagram generator
- Brian's Brain cellular automaton
- A rhythm / typing game
- A minimal JS REPL / code sandbox
- A clock / time visualizer

---

## 2026-03-22 — Run 11

Built `voronoi.html`: Voronoi diagram with animated Lloyd's relaxation.
- WebGL fragment shader: brute-force nearest-seed per pixel (up to 128 seeds), runs at full resolution in real time
- Animated Lloyd relaxation: each frame computes cell centroids via a reduced-res readback, moves seeds 40% toward centroid — cells breathe toward equilibrium
- Bowyer-Watson Delaunay triangulation in JS, rendered as overlay
- Click to add seeds, right-click to remove nearest
- Seed/edge/Delaunay toggles, 5 palettes
- Added card + CPU nearest-seed thumbnail to index.html

Next ideas:
- Brian's Brain cellular automaton
- A rhythm / typing game
- A clock / time visualizer
- A minimal code sandbox / REPL
- A fluid simulation (Navier-Stokes or SPH)

---

## 2026-03-22 — Run 12

Built `typing.html`: falling-word typing game.
- Words fall at speeds scaling with level; 4 word tiers (easy→expert vocabulary)
- Type any prefix to lock onto a word (highlighted yellow); complete it to destroy
- Combo multiplier up to x8; score = word length × combo
- 3 lives; miss = life lost + combo reset + red flash
- Web Audio feedback: melodic hit chord (pitch shifts with combo), dissonant miss tone, ascending fanfare on level up
- Red danger bar grows as words approach bottom
- Level-up flash, WPM tracker, localStorage high score
- Added card to index.html

Next ideas:
- A fluid simulation (Navier-Stokes or SPH)
- Brian's Brain cellular automaton
- A clock / time visualizer
- A piano / instrument toy
- Conway's Game of Life pattern library

---

## 2026-03-22 — Run 13

Built `clock.html`: orbital time visualizer.
- 7 concentric rings: seconds (outermost) → minutes → hours (12h) → day (24h) → week → month → year (innermost)
- Each ring has a glowing dot orbiting at the correct rate, with a comet trail
- Filled sweep arc shows elapsed fraction of each period
- Tick marks on the second ring (major every 5s)
- Actual HH:MM:SS time displayed in the center
- Footer: weekday, date, day-of-year, % of year elapsed
- 5 themes: Cosmos, Ember, Aurora, Mono, Void
- Breathing mode: sinusoidal scale pulse
- Added live card to index.html (snapshot of current time rendered at page load)

Next ideas:
- Brian's Brain cellular automaton
- A piano / synthesizer toy
- Conway's Game of Life pattern library
- A generative poetry / text engine
- A network graph visualizer

---

## 2026-03-22 — Run 14

Built `piano.html`: polyphonic synthesizer with playable keyboard.
- 7 synthesized voices: Piano (triangle+octave), Organ (4 harmonics), Lead (filtered saw), Pad (3-voice detuned saw), Bass (sub+square), Bell (inharmonic partials), Pluck (noise burst)
- ADSR envelopes per voice; proper release on key-up
- Reverb (convolution with generated impulse response) + delay chain
- 3 octaves of keys; computer keyboard mapping (A-S-D-F... row = white, W-E-T-Y... row = black)
- Sustain pedal (Spacebar or button), holds notes until released
- Real-time chord detection (maj/min/7/maj7/min7/dim/aug/sus2/sus4/ø7/maj9/min9)
- Record and play back sessions
- Waveform + note-frequency overlay visualizer
- Octave transpose slider
- Added keyboard thumbnail card to index.html

Next ideas:
- Brian's Brain cellular automaton
- A network graph / force-directed layout visualizer
- A generative poetry engine
- A Conway's Game of Life pattern library
- An ASCII art generator

---

## 2026-03-22 — Run 15

Built `graph.html`: force-directed network graph visualizer.
- Verlet integration: spring attraction on edges + O(n²) repulsion + center gravity + damping
- 9 topology generators: Random (Erdős-Rényi), Ring, Grid, Binary Tree, Small World (Watts-Strogatz rewiring), Scale-Free (Barabási-Albert preferential attachment), Clique, Path, Bipartite
- 4 colorings: Degree centrality, Betweenness centrality (sampled BFS), Community (connected components), BFS depth from node 0
- Interaction: click empty space to add node; drag node→node to add edge; right-click to delete node
- Stats: node count, edge count, avg degree, connected components
- Freeze toggle, node labels
- Added force-simulated thumbnail card to index.html

Next ideas:
- Brian's Brain cellular automaton
- Generative poetry / text engine
- ASCII art generator
- A sorting algorithm visualizer
- A 3D renderer (raymarching or rasterization)

---

## 2026-03-22 — Run 16

Built `raymarcher.html`: WebGL SDF raymarcher with 6 scenes.
- Fragment shader raymarcher: 96-step sphere-tracing, SDF primitives (sphere, box, torus, plane, cylinder)
- CSG ops: smooth union (metaballs), smooth subtraction, domain repetition
- Lighting: Phong diffuse+specular, soft shadow (32-step penumbra), ambient occlusion (5-tap), fog
- 1-bounce reflection pass for scene 0 and 1
- 6 scenes:
  0. Metaballs — 3 animated smooth-unioned spheres over checkerboard floor
  1. Torus + Cube — animated rotation with smooth blend and sphere subtraction
  2. Menger Sponge — 3-iteration IFS fractal with rotating camera
  3. Alien Terrain — fBm heightmap with 4 floating crystal shards
  4. Infinite Tunnel — repeating rings + pillars scrolling through a cylinder
  5. Cornell Box — two boxes inside a room with colored walls
- Orbit (drag), zoom (scroll), touch support; per-effect toggles; quality selector (½/¾/full)
- CPU metaball thumbnail rendered at page load for index.html card

Next ideas:
- Brian's Brain cellular automaton
- Generative poetry / text engine
- A sorting algorithm visualizer
- A flow field / vector field visualizer
- A noise-based wallpaper generator

---

## 2026-03-22 — Run 17

Built `sorting.html`: sorting algorithm visualizer with audio.
- 8 algorithms implemented as JS generators (yield each comparison/swap/set operation):
  Bubble, Selection, Insertion, Shell, Merge (out-of-place), Quick (Lomuto partition), Heap, Radix (LSD base-10)
- Color coding: comparing (yellow), swap (red), pivot (orange), merge write (blue), sorted (green)
- Tonal audio: each comparison/swap beeps a sine tone proportional to bar height
- Speed slider (1–100), step-by-step mode (advance one operation per click)
- 5 input patterns: Random, Nearly Sorted, Reversed, Few Unique, Pipes
- Live stats: comparisons, swaps, array accesses
- Victory sweep animation on completion
- Added mid-sort bars thumbnail to index.html

Next ideas:
- Brian's Brain cellular automaton
- Generative poetry / text engine
- A flow field / vector field visualizer
- A noise-based wallpaper generator
- A game of Breakout or Snake

---

## 2026-03-22 — Run 18

Built `flowfield.html`: particle flow field visualizer.
- Thousands of particles follow a vector field, leaving fading trails on an offscreen canvas
- 7 field types: Perlin Noise (evolving), Curl Noise, Radial, Circular, Saddle, Wave, Multi-Vortex (3 rotating attractors)
- 6 color palettes: Ocean, Fire, Aurora, Mono, Neon, Speed (velocity-mapped)
- Particle lifecycle: age/maxAge with random stagger, wrap-around edges
- Click canvas to spawn an 80-particle burst; hover to display field vector at cursor
- Evolve toggle animates noise time offset; Arrows overlay shows field direction grid
- Updated index.html with animated ocean-palette preview card

Next ideas:
- Brian's Brain cellular automaton
- Generative poetry / text engine
- A Breakout or Snake game
- A noise-based wallpaper / screensaver generator
- A 3D spinning wireframe toy (with hidden-line removal)

---

## 2026-03-22 — Run 19

Built `breakout.html`: classic Breakout brick-breaker game.
- 5 levels with escalating brick layouts: simple rows → checkerboard → diamond → fortress → chaos
- 4 brick types: normal (10pts), hard/2-hit (30pts), indestructible, bomb (destroys 3×3 neighborhood)
- 4 powerups drop on brick destruction: wide paddle, multi-ball (+2), slow-ball, laser volley
- Physics: angle-based paddle reflection (edge hit = steep angle), multi-ball support, laser bolts
- Web Audio sound effects: paddle ping, wall bounce, brick smash (pitch by row), powerup fanfare, death tone, level-up arpeggio
- Particle burst on every brick destroyed; color matches row hue
- localStorage high score; Space to pause/resume; lives HUD
- Added static mid-game thumbnail to index.html

Next ideas:
- Brian's Brain cellular automaton
- Generative poetry / text engine
- A Snake game (with growing tail + food)
- A noise-based wallpaper / screensaver
- A 3D wireframe spinner (cube/torus/icosahedron)

---

## 2026-03-22 — Run 20

Built `brian.html`: multi-rule cellular automata explorer.
- 6 rule sets:
  - Brian's Brain (3-state: OFF→ON if 2 ON neighbors; ON→DYING; DYING→OFF — produces gliders)
  - Seeds (B2/S: born with 2 neighbors, nothing survives — explosive chaotic growth)
  - Day & Night (B3678/S34678 — symmetric rule, dense stable structures)
  - Cyclic CA 3-state (spiral-generating infection automaton)
  - Cyclic CA 5-state with threshold 3 (slower structured spirals)
  - Wireworld (4-state: empty/conductor/electron-head/tail — logic gates)
- Uint8Array grid with toroidal wraparound, typed-array ping-pong for fast stepping
- ImageData pixel renderer: fills CELL×CELL blocks per cell, no per-cell canvas calls
- 5 color palettes: Plasma, Ember, Ice, Matrix, Mono
- Draw mode: left-click paints ON, right-click erases
- 5 presets: Glider, Spaceship, Explosion, Grid, Rings
- Speed (1–30 steps/s), Zoom (2–16px/cell), Step, Random, Clear
- Keyboard shortcuts: Space=pause, R=random, C=clear, N/.=step
- Added animated Brian's Brain preview card to index.html

Next ideas:
- Generative poetry / text engine (Markov chains or templates)
- A Snake game
- A 3D wireframe spinner
- A noise-based wallpaper generator
- An audio visualizer / oscilloscope

---

## 2026-03-23 — Run 21

Built `wireframe.html`: 3D software rasterizer with hidden-line removal.
- 8 shapes: Cube, Tetrahedron, Octahedron, Icosahedron, Dodecahedron (12 verified pentagonal faces), Torus, Sphere, Trefoil Knot (tube swept around parametric path)
- Quaternion-based rotation: mouse drag applies incremental quaternion from axis-angle; scroll to zoom
- Backface culling: face normal dot product with view direction discards unseen faces
- Painter's algorithm: visible faces sorted by average z depth, drawn back-to-front
- `fixWinding` auto-corrects face orientation for convex meshes using centroid dot test
- 5 themes (Electric/Gold/Ghost/Neon/Crimson): face fill color + edge brightness both mapped to depth
- 3 render modes: Wireframe, Solid+Wire, Solid (with faint edge overlay)
- Frenet–Serret frame for trefoil knot tube normals; perspective projection (FOV=2.6)
- Touch support for mobile drag-rotation
- Added live spinning icosahedron thumbnail to index.html

## 2026-03-23 — Run 22

Built `snake.html`: Snake with smooth interpolated movement and powerups.
- Smooth sub-tick interpolation: snake segments lerp between grid positions each frame
- 5 food types: normal (red, 10pts), big (orange, 30pts + extra growth), speed (cyan), ghost (purple), magnet (green)
- Powerups: speed=halves tick rate, ghost=pass through walls, magnet=nearby food drifts toward head
- Increasing difficulty: tick rate scales with snake length
- Web Audio chiptune sounds: eat ping, powerup arpeggio, death buzz, turn click
- Particle burst on every food eaten; animated eyes on snake head pointing in travel direction
- Active powerup bar at bottom of canvas showing remaining time
- Swipe controls for touch; WASD + arrow key dual support
- localStorage high score
- Added static snapshot thumbnail + spinning wireframe thumbnail to index.html

Next ideas:
- Generative poetry / text engine
- A noise-based wallpaper / screensaver generator
- An audio visualizer / oscilloscope
- A Conway's Game of Life pattern library
- A physics pendulum / double pendulum simulation

---

## 2026-03-23 — Run 23

Built `pendulum.html`: double pendulum chaos visualizer.
- RK4 (4th-order Runge-Kutta) integration with 10 sub-steps per frame for accuracy
- Up to 20 simultaneous pendulums with near-identical initial conditions (0.015 rad spread)
- Fading trail on offscreen canvas (rgba fade 0.018 per frame) — creates luminous arcs
- Trail color: hue varies by pendulum index across selected palette (Rainbow/Fire/Ice/Mono)
- Phase portrait: live θ1 vs θ2 dot plot in corner showing chaotic attractor
- Energy readout: KE/PE/total with mini bar visualization
- Drag bob1 or bob2 to set initial angle interactively
- Controls: gravity (1–30), simulation speed, trail length, pendulum count
- Chaos mode toggle: enables the tiny angle offsets that cause exponential divergence
- Added animated chaos-trail thumbnail to index.html

Next ideas:
- Generative poetry / text engine (Markov chains)
- An audio visualizer / oscilloscope
- A noise-based wallpaper generator
- A Conway's Game of Life pattern library
- A fluid ink / Navier-Stokes simulation

---

## 2026-03-23 — Run 24

Built `visualizer.html`: multi-mode audio visualizer.
- 5 visualization modes:
  - Waveform: zero-crossing triggered oscilloscope with glow passes
  - Spectrum: frequency bar chart with peak indicators
  - Radial: polar spectrum with connecting outline curve
  - Spectrogram: scrolling waterfall — shifts image left each frame, draws new column
  - Lissajous: time-domain X vs X+N/4 (90° offset) phase plot
- 5 built-in synth sources (no mic required):
  - Drone: 4 detuned oscillators with LFO-modulated gain creating slow beating
  - Arpeggio: pentatonic scale, 220ms steps, triangle wave with decay envelope
  - Chord: cycling through 4 major chords every 2s with attack/release
  - Bass: 55Hz sine + sub-octave square, 120 BPM pulse
  - Noise: looping white noise through bandpass filter
- Live microphone input via getUserMedia with graceful fallback
- 4 palettes (Electric/Fire/Aurora/Mono), glow toggle (canvas shadowBlur), FFT size 512–8192
- Keyboard shortcuts: 1–5 for modes, G for glow toggle
- Added static spectrum + mini radial thumbnail to index.html

Next ideas:
- Generative poetry / text engine
- A noise-based wallpaper / screensaver
- A Conway's Game of Life pattern library
- A fluid ink / Navier-Stokes simulation
- A procedural dungeon map renderer (top-down, not text)

---

## 2026-03-23 — Run 25

Built `fluid.html`: WebGL2 incompressible Navier-Stokes fluid ink simulation.
- 9 GLSL 3.00 es shader programs: advect, jacobi, diverge, curl, vort (vorticity confinement), grad (gradient subtract), splat, display, clear
- Fluent program builder: `mkProg(fs)` returns `{use, i1, f1, f2, f4, tex}` chainable uniform API
- Ping-pong FBOs: `vel` (RG32F 256×256 double), `pres` (R32F 256×256 double), `div` (R32F single), `curl2` (R32F single), `dye` (RGBA16F 512×512 double)
- Requires `EXT_color_buffer_float` for float render targets in WebGL2
- Simulation loop per frame: curl → vorticity confinement → semi-Lagrangian velocity advect → divergence → clear pressure → Jacobi pressure solve (configurable iters) → gradient subtract → dye advect
- Mouse drag: splat injects force (Gaussian kernel, radius 0.003 UV) + rainbow HSL dye (hue advances 0.8°/splat)
- Auto-demo: 3 orbital splat points animate for first 600 frames
- Controls: Vorticity (0–60), Pressure Iterations (5–60), Dissipation (0.90–1.0), Pause, Clear
- Added bezier-curve ink trail thumbnail to index.html

Next ideas:
- Generative poetry engine (Markov chains or context-free grammar)
- A noise-based wallpaper / screensaver generator
- A Conway's Game of Life pattern library with gliders/oscillators
- A procedural dungeon map renderer (top-down tiles, not text)
- A particle life simulation (species with attraction/repulsion rules)

---

## 2026-03-23 — Run 26

Built `particle_life.html`: particle life emergent simulation.
- N species (3–6) of particles, each pair governed by an asymmetric attraction/repulsion coefficient
- Force model: linear hard repulsion inside R_INNER=14px; bell-curve force scaled by rule value in [R_INNER, R_MAX=80px]
- Spatial hash with O(n) neighbor lookup: grid cells of size R_MAX, 3×3 neighborhood search per particle
- Typed arrays (Float32Array/Uint8Array) for particle state — avoids JS object overhead
- 4 presets: Ring Chase (each species chases next, flees prev), Clusters (self-attract), Symbiosis (paired species attract), Chaos (strong asymmetric random)
- Editable attraction matrix UI: click cell to cycle attract/repel/neutral; color-coded green=attract, blue=repel
- Controls: species count, particle count, friction, force multiplier, randomize, preset, pause
- Mouse drag repulses nearby particles; touch support
- Keyboard: space=pause, r=random, p=preset
- Added clustered swarm thumbnail to index.html

Next ideas:
- Generative poetry engine (Markov chains or L-systems)
- A noise-based wallpaper / screensaver generator
- A Conway's Game of Life pattern library
- A procedural dungeon map renderer (top-down tiles)
- A Lindenmayer system (L-system) tree/fractal generator

---

## 2026-03-23 — Run 27

Built `lsystem.html`: L-System Explorer with animated turtle graphics.
- 10 classic Lindenmayer system presets:
  Koch Snowflake (F++F++F, angle 60°), Dragon Curve (iter 12), Fractal Plant (branching, angle 25°),
  Hilbert Curve (space-filling, angle 90°), Sierpinski Triangle (2-symbol, angle 120°),
  Lévy C Curve (iter 14), Gosper Curve (hex tiling), Bush (double-branching, angle 22.5°),
  Pentigree (5-fold symmetry), Quadratic Koch (angle 90°)
- String expansion with 320k character safety cap; F and G both draw forward
- Animated progressive drawing: segments rendered in 12 color sub-batches per frame for smooth gradient
- Float32Array segment storage; one `beginPath/stroke` call per sub-batch (fast)
- Auto-fit: computes bounding box then scale+translate to fill canvas with padding
- Line width scales as 220/sqrt(totalSegs) — thinner for more complex fractals
- 6 color palettes: Rainbow, Fire, Ice, Neon, Gold, Mono
- Glow toggle via ctx.shadowBlur on offscreen canvas
- Skip button: draws remaining segments synchronously in 40 sub-batches
- Keyboard: space=pause, r=redraw, g=glow, ←/→ = dec/inc iterations
- Added rainbow Koch snowflake (iter 4) thumbnail to index.html

Next ideas:
- Generative poetry engine (Markov chains)
- A noise-based wallpaper / screensaver generator
- A Conway's Game of Life pattern library
- A procedural dungeon map renderer (top-down tiles)
- A reaction-diffusion pattern explorer (more presets + real-time GPU)

---

## 2026-03-23 — Run 28

Built `dungeon.html`: procedural BSP dungeon crawler with fog of war.
- BSP (Binary Space Partitioning) map generation: recursively splits 72×50 tile space, places rooms in leaves, connects with L-shaped corridors sorted by room center X
- Tile types: void, floor, wall, stair (descend to next floor)
- Decorations: torches on room border walls (animated flicker + light), pillars in large rooms (block movement), treasure chests
- Fog of war: 3 states per tile (unseen/seen/visible); LOS radius 10 via Bresenham ray casting; seen tiles dim at 32% alpha
- Smooth camera: exponential lerp (camX += (target-camX)*0.10 per frame)
- Animated torch glows: radial gradient with globalCompositeOperation='screen', radius flickers with sin(t)
- Stone wall detail: top highlight strip, bottom shadow, procedural crack lines seeded by tile position
- 3 themes: Dungeon (cool grey/blue), Crypt (purple), Temple (gold)
- Controls: WASD/arrows, click adjacent tile; minimap in top-right; floor counter
- Added static room-map thumbnail to index.html

Next ideas:
- Generative poetry engine (Markov chains)
- A noise-based wallpaper / screensaver generator
- A Conway's Game of Life pattern library
- A reaction-diffusion GPU explorer (more pattern presets)
- A music sequencer / drum machine

---

## 2026-03-23 — Run 29

Built `sequencer.html`: 16-step drum machine + melodic step sequencer.
- 8 tracks: Kick, Snare, Clap, Hi-Hat Closed, Hi-Hat Open, Tom, Bass, Lead
- All synthesis via Web Audio API (no samples):
  - Kick: sine osc 160→0Hz pitch drop over 0.5s
  - Snare: HP-filtered noise (900Hz) + sine 190→80Hz
  - Clap: 3 staggered BP-filtered noise bursts (1200/1000/900Hz, 10ms offsets)
  - Hi-Hat C/O: HP-filtered noise (9000/7500Hz), 40ms/280ms decay
  - Tom: sine 90→30Hz over 280ms
  - Bass: sawtooth through 700Hz LP filter, ADSR envelope
  - Lead: dual square oscillators ±3 cents detune, 2400Hz LP filter
- Web Audio lookahead scheduler: setInterval(22ms) schedules 120ms ahead of current time
- Visual step indicator via requestAnimationFrame + (currentTime - startTime) / stepDur
- Swing: delay applied to all odd-indexed steps (0–50%)
- Per-track mute and volume; master volume control
- Melodic tracks: click cycles through 6 (bass) / 8 (lead) pentatonic scale notes
- Drum tracks: click toggles; right-click clears
- 4 preset patterns: House, Hip-Hop (swing 25%), Jungle, Techno
- Randomize drums with density weights per track
- Beat dot indicators (4 dots = 4 beats per bar)
- Space bar to play/stop
- Added static grid snapshot thumbnail to index.html

Next ideas:
- Generative poetry engine (Markov chains)
- A noise-based wallpaper / screensaver generator
- A Conway's Game of Life pattern library with presets
- A reaction-diffusion GPU explorer
- A Mandelbrot / Julia set explorer with zoom

---

## 2026-03-23 — Run 30

Built `fractal.html`: WebGL2 Mandelbrot + Julia set dual explorer.
- Single GLSL ES 3.00 fragment shader handles both Mandelbrot and Julia via `u_isJulia` uniform
- Smooth escape-count coloring via Hubbard-Douady potential: `nu = log2(log2(|z|²)/2)`, `smoothI = escaped + 1 - nu`
- 5 cosine palettes (iq-style formula): Electric, Fire, Ice, Rainbow, Twilight
- Configurable color cycles (1–20): `fract(smoothI / maxIter * cycles)` for multi-cycle banding
- Two independent WebGL2 canvases with their own render state; `makeRenderer(canvas)` factory
- Interaction: scroll to zoom (zoom toward cursor), drag to pan, pinch-to-zoom on touch
- Mandelbrot mousemove → updates Julia `u_juliaC` uniform in real time (live Julia preview)
- 6 preset locations: Full Set, Seahorse Valley, Elephant Valley, Double Spiral, Mini Mandelbrot, Antenna Tip
- Iterations: 64–2000 (slider); renders at devicePixelRatio for retina sharpness
- Keyboard: r=reset, +/-=zoom
- Added CPU-rendered Mandelbrot thumbnail to index.html

Next ideas:
- Generative poetry engine (Markov chains)
- A noise-based wallpaper / screensaver generator
- A Conway's Game of Life pattern library with presets
- A gravity / n-body simulation
- A Voronoi / Delaunay interactive diagram

---

## 2026-03-23 — Run 31

Built `gravity.html`: N-body gravity sandbox.
- Velocity Verlet integration with 3 sub-steps per frame for stability
- O(n²) pairwise gravitational force with softening (ε²=16) to prevent singularities
- Body merging: when two bodies overlap (sum of radii), heavier absorbs lighter; conserves momentum
- Fading trail system: each body stores up to 200 trail points; configurable trail opacity via alpha-fade
- Radial glow per body (radialGradient) + specular highlight
- Click to place; shift+drag to set launch velocity; scroll wheel to adjust spawn mass (1–500)
- 5 presets: Binary Star (two orbiting stars), Solar System (central mass + 5 planets), Figure-8 (3-body choreography), Galaxy (120 orbiting particles), Random 50
- Controls: G constant (0.1–5), trail opacity, merge toggle, pause, clear
- Keyboard: space=pause, c=clear
- Added animated orbiting bodies thumbnail to index.html

Next ideas:
- Generative poetry engine (Markov chains)
- A noise-based wallpaper / screensaver generator
- A Voronoi / Delaunay interactive diagram
- A hex grid strategy game
- A wave equation simulator

---

## 2026-03-23 — Run 32

Built `wave.html`: 2D wave equation finite difference simulator.
- Wave equation: `next[i] = (2*cur[i] - prev[i] + c²*laplacian) * damp`
- 5-point Laplacian stencil with wall-aware neighbor handling (reflects off walls)
- Half-resolution grid (SCALE=2) with pixel-art upscaling for performance
- 4 interaction modes:
  - Pulse: click/drag to drop Gaussian disturbances
  - Continuous: click to place oscillating wave sources (sin wave emitters)
  - Double Slit: sets up vertical barrier with two openings + continuous source for interference pattern
  - Draw Wall: paint/erase barriers with click/shift-click
- 4 color palettes: Ocean (blue→cyan→white), Thermal (blue→black→red→yellow), Electric (purple→cyan→white), Mono (greyscale)
- Boundary conditions: Reflecting (Neumann) or Absorbing (Dirichlet zero)
- Controls: wave speed (0.1–0.9), damping (0.990–1.000), source radius (1–12), palette, boundary mode
- Keyboard: space=pause, c=clear
- Touch support for mobile
- Added wave interference thumbnail to index.html

Next ideas:
- Generative poetry engine (Markov chains or context-free grammar)
- A Voronoi / Delaunay interactive diagram
- A hex grid strategy game
- A reaction-diffusion GPU explorer
- A noise-based wallpaper / screensaver generator

---

## 2026-03-23 — Run 33

Built `hexgame.html`: Hex Conquest — turn-based hex territory strategy game vs AI.
- Axial hex coordinate system with flat-top hexagons
- Territory expansion: claim empty hexes adjacent to your territory, attack enemy hexes, reinforce own cells
- Attack power scales with adjacent friendly cell strength (total/3, min 1)
- Reinforcement: cells with 3+ friendly neighbors auto-gain +1 strength per turn (cap 5)
- Strength displayed as dot patterns (1–5 dots per hex)
- 3 AI difficulty levels:
  - Easy: 2 moves/turn, high randomness
  - Medium: 3 moves/turn, moderate randomness, occasional reinforcement
  - Hard: 4 moves/turn, low randomness, defensive play, blocks player expansion
- 3 board sizes: Small (radius 7), Medium (9), Large (12)
- Neutral fortress cells scattered at game start (golden, pre-fortified)
- Win condition: own 85%+ of all cells, or eliminate opponent
- Hover highlights valid moves; glow effect on claimable hexes
- Keyboard: Enter/e=end turn, n=new game
- Added static hex grid thumbnail to index.html

Next ideas:
- Generative poetry engine (Markov chains or context-free grammar)
- A reaction-diffusion GPU explorer
- A noise-based wallpaper / screensaver generator
- A circuit logic gate simulator
- A music visualizer with FFT analysis

---

## 2026-03-23 — Run 34

Built `circuit.html`: visual logic gate simulator.
- 7 gate types: AND, OR, NOT, NAND, NOR, XOR, XNOR
- INPUT nodes (toggle on/off by clicking) and OUTPUT nodes (with indicator light)
- Drag from output pin to input pin to create wires; bezier curve routing
- Wire colors: green=high (1), dark=low (0); glow effect on active wires
- Iterative simulation (10 passes) handles feedback loops (e.g. SR latch)
- Each input pin accepts one wire; new wire replaces old
- Right-click near a wire to delete it; Del key to delete selected gate
- Gate symbol overlays (AND curved body, OR curved, XOR double curve, bubble for NOT/NAND/NOR/XNOR)
- Dot grid background for alignment
- 4 presets:
  - Half Adder: XOR for sum, AND for carry
  - SR Latch: cross-coupled NOR gates with feedback
  - 2-bit Comparator: XNOR + AND for equality check
  - Multiplexer: NOT + 2×AND + OR for 2:1 data selection
- Drag gates to reposition; click to select (blue highlight)
- Added static gate diagram thumbnail to index.html

Next ideas:
- Generative poetry engine (Markov chains or context-free grammar)
- A reaction-diffusion GPU explorer
- A noise-based wallpaper / screensaver generator
- A music visualizer with FFT analysis
- A cellular automaton rule explorer (1D elementary automata)

---

## 2026-03-23 — Run 35

Built `automata.html`: elementary cellular automaton explorer (all 256 Wolfram rules).
- 1D cellular automata: 3-cell neighborhood → 8 possible patterns → 8-bit rule number (0–255)
- Rule visualization: clickable bit cells with 3-cell neighborhood preview above each bit
- Wrapping boundary conditions (toroidal)
- 6 initial conditions: Single Cell, Random 50%/25%/75%, Alternating, Blocks
- 5 color palettes: White, Green, Amber, Blue, Rainbow (hue shifts per row)
- Infinite scrolling: when canvas fills, shifts grid up and continues generating
- Adjustable cell size (1–6px) and speed (1–60 rows/frame)
- 10 famous rules quick-select: Rule 30 (chaos), 90 (Sierpinski), 110 (Turing complete), 184 (traffic), etc.
- Random Rule button for exploration
- Keyboard: space=pause, r=random, arrows=±1/±10 rule number
- Added rainbow Rule 110 triangle thumbnail to index.html

Next ideas:
- Generative poetry engine (Markov chains or context-free grammar)
- A reaction-diffusion GPU explorer
- A noise-based wallpaper / screensaver generator
- A music visualizer with FFT analysis
- A platformer game with procedural levels

---

## 2026-03-23 — Run 36

Built `poetry.html`: context-free grammar generative poetry engine.
- 6 poetic forms: Free Verse (9–10 lines, stanza breaks), Haiku (5-7-5), Tanka (5-7-5-7-7), Quatrain (4+4 lines), Couplets (3 pairs), Concrete (diamond shape 1-2-3-4-5-4-3-2-1 words)
- 6 thematic word banks (~25–30 words each): Nature, Cosmos, City, Ocean, Time, Dreams
  - Each bank has: nouns, adjectives, verbs, adverbs, prepositions, determiners, conjunctions
- Context-free grammar: S → structure, each non-terminal → template with `{pos}` slots
- ~10–12 line templates per form with varied sentence structures
- Title generated from separate template set
- Animated line-by-line reveal with CSS transitions (opacity + translateY)
- 15% chance of italic emphasis per line
- Grammar sidebar shows production rules for current form
- History panel: click to revisit any of last 20 poems
- Auto mode: generates new poem on interval (adjustable tempo)
- Keyboard: space=generate, a=auto toggle
- Added static poem text thumbnail to index.html

Next ideas:
- A reaction-diffusion GPU explorer
- A noise-based wallpaper / screensaver generator
- A music visualizer with FFT analysis
- A platformer game with procedural levels
- A pixel art editor

---

## 2026-03-23 — Run 37

Built `pixelart.html`: pixel art editor with full drawing toolkit.
- 7 tools: Pen (B), Eraser (E), Flood Fill (G), Line (L), Rectangle (R), Circle (C), Color Picker (I)
- Bresenham line algorithm for smooth pen strokes and line tool
- Midpoint circle algorithm for the circle tool
- Flood fill via iterative stack-based approach (no recursion)
- Mirror mode: horizontal symmetry drawing (toggleable)
- Undo/redo stack (50 levels)
- 4 canvas sizes: 16×16, 32×32, 48×48, 64×64
- 32-color default palette (rich pixel art colors)
- Recent colors tray (last 16 used)
- Native color picker for custom colors
- Checkerboard transparency background
- Grid overlay (toggleable, auto-hides at low zoom)
- Scroll to zoom (2×–32×), live preview panel in sidebar
- Export to PNG (true pixel resolution, no upscale)
- Right-click to erase with any tool
- Shape tools (line/rect/circle) show live preview while dragging
- Keyboard shortcuts for all tools + Ctrl+Z/Y undo/redo
- Added smiley sprite thumbnail with palette strip to index.html

Next ideas:
- A reaction-diffusion GPU explorer
- A noise-based wallpaper / screensaver generator
- A music visualizer with FFT analysis
- A platformer game with procedural levels
- A Boids flocking simulation

---

## 2026-03-23 — Run 38

Built `boids.html`: Craig Reynolds boid flocking simulation.
- Three classic steering forces: Separation, Alignment, Cohesion — each with adjustable strength
- Spatial hash grid (cell size 80px) for O(n) neighbor queries instead of O(n²)
- Generator-based neighbor iteration over 3×3 grid neighborhood
- Predator agents: chase nearest boid, boids flee within 2× sight range
- Mouse drag attracts nearby boids (radius 300px)
- Toroidal wrapping boundaries
- 3 visual styles: Triangles (velocity-oriented), Dots, Lines (velocity vectors)
- Configurable trail fade (alpha 0–0.98) for motion blur effect
- Speed clamping with minimum velocity floor (30% of max) to prevent stalling
- 6 presets:
  - Classic Flock: 200 boids, balanced forces
  - Tight Swarm: 300 boids, high cohesion/alignment, low separation
  - Loose Drift: 150 boids, high separation, low cohesion
  - Predator: 200 boids + 2 predators
  - Two Species: 120 blue + 120 orange boids
  - Tornado: 400 boids with initial tangential velocity for vortex
- Click=attract, shift+click=add predator, right-click=spawn 20, scroll=±10 boids
- Keyboard: space=pause, c=clear
- Added animated flock thumbnail to index.html

Next ideas:
- A reaction-diffusion GPU explorer
- A noise-based wallpaper / screensaver generator
- A music visualizer with FFT analysis
- A platformer game with procedural levels
- A Perlin noise terrain generator

---

## 2026-03-23 — Run 39

Built `fftvis.html`: FFT-based audio visualizer with 6 modes.
- Web Audio API: AnalyserNode with 2048-point FFT (1024 frequency bins)
- 2 audio sources:
  - Microphone: `getUserMedia` → MediaStreamSource → AnalyserNode
  - Built-in Synth: chord progression (C–Am–F–G) with sine pads, sawtooth bass (LP filtered), and scheduled hi-hat noise bursts
- 6 visualization modes:
  - Bars: vertical frequency bars with per-bar glow for high energy
  - Waveform: time-domain oscilloscope trace with translucent fill
  - Circular: radial frequency bars around center with inner bass glow (radialGradient)
  - Spectrogram: scrolling time-frequency heatmap via ImageData column writes
  - Particles: bass/mid/hi energy drives particle emitters from center and edges; gravity + fade
  - Mirror Bars: symmetric bars reflected above and below center line
- 5 color palettes: Neon (purple→pink→cyan), Fire (red→orange→yellow), Ice (teal→blue), Rainbow (full hue), Mono (greyscale)
- Controls: gain (0.5–4×), smoothingTimeConstant (0–0.95), fade alpha (0.01–0.5)
- Keyboard: 1–6 = switch visualization mode
- Added static frequency bars thumbnail to index.html

Next ideas:
- A reaction-diffusion GPU explorer
- A noise-based wallpaper / screensaver generator
- A platformer game with procedural levels
- A Perlin noise terrain generator
- A Turing machine simulator

---

## 2026-03-23 — Run 40

Built `platformer.html`: procedurally generated infinite platformer.
- Seeded RNG (`seed * 16807 % 2^31-1`) ensures each level is deterministic and replayable
- Level generation: ground with gaps, raised terrain, floating platforms, spikes, coins, enemies
- Level size scales with difficulty: `60 + level*8` tiles wide; enemy density increases per level
- Physics: AABB tile collision, gravity (0.55), friction (0.82), max fall speed (12)
- Jump mechanics: 6-frame coyote time + 6-frame jump buffer for forgiving input
- One-way platforms: solid from above only (checks velocity direction + overlap)
- Enemies: patrol left/right, reverse at walls or ledge edges; stompable from above (bounce)
- Coin collection with golden burst particles; bobbing animation via `sin(time + col)`
- Death: spikes, falling off screen, enemy contact → respawn with lives system
- Exit flag at end of each level → auto-advance with "Level Complete" overlay
- Game Over screen shows final level + coin count, then resets
- Smooth camera: exponential lerp (0.1 horizontal, 0.08 vertical) clamped to level bounds
- Parallax star background (30% scroll rate)
- 4 level themes cycling: Blue/Grey, Brown/Desert, Green/Forest, Purple/Void
- Particle effects: jump dust, coin sparkle, enemy death, player death
- Touch controls: left third=left, right third=right, top half=jump
- Keyboard: arrows/WASD + space/up=jump, R=restart
- Added static platformer scene thumbnail to index.html

Next ideas:
- A reaction-diffusion GPU explorer
- A noise-based wallpaper / screensaver generator
- A Perlin noise terrain generator
- A Turing machine simulator
- A tower defense game

---

## 2026-03-23 — Run 41

Built `turing.html`: visual Turing machine simulator.
- Infinite tape (sparse object storage, reads blank for unset positions)
- Animated tape display: cells scroll to keep head centered, head highlighted with glow + triangle indicator
- Transition table: `(state, symbol) → (write, move, nextState)` displayed as interactive HTML table
- Active transition row highlighted in real time as machine executes
- Execution log panel: shows last 50 steps as `step: state[read] → write,move,next`
- Step mode (single step) and run mode (continuous with adjustable speed 1–200 steps/sec)
- Batch execution: at high speeds processes up to 20 steps per render frame
- Accept states: machine halts and shows "Accepted" when entering an accept state
- 6 programs:
  - Binary Increment: scans to rightmost bit, propagates carry
  - Palindrome Check: marks and matches outer symbols inward (accepts "abba")
  - Unary Addition: replaces + with 1, erases trailing 1 (e.g. 111+11 → 11111)
  - Binary Invert: flips 0↔1 left to right
  - Busy Beaver 3: classic 3-state busy beaver (writes 6 ones, 14 steps)
  - Duplicate String: marks, scans, copies each symbol past separator
- Keyboard: space=run/pause, s=step, r=reset
- Added tape cell thumbnail to index.html

Next ideas:
- A reaction-diffusion GPU explorer
- A noise-based wallpaper / screensaver generator
- A Perlin noise terrain generator
- A tower defense game
- A regex visualizer / tester

---

## 2026-03-23 — Run 42

Built `wallpaper.html`: procedural noise wallpaper generator.
- Custom gradient noise implementation: permutation table seeded via LCG, 8 gradient vectors, smoothstep interpolation
- fBm (fractional Brownian motion): configurable octaves (1–8) with amplitude halving and frequency doubling
- 8 pattern modes:
  - Perlin Clouds: standard fBm with time offset for animation
  - Turbulence: absolute value of noise for billowy effect
  - Ridged: `(1 - |noise|)²` for sharp ridgelines
  - Marble: sine wave distorted by fBm for vein patterns
  - Wood: fractional part of scaled fBm for concentric ring look
  - Voronoi Cells: nearest-neighbor distance field from jittered grid points
  - Domain Warp: feeds fBm output back as coordinate offset (recursive distortion)
  - Fractal Terrain: quantized fBm into discrete height levels
- 8 color palettes: Sunset, Ocean, Forest, Neon, Ember, Frost, Mono, Vaporwave
  - Each palette is 5-stop gradient with linear interpolation
- Half-resolution rendering (2× step) for interactive speed; full-res on export
- Animate mode: slowly evolves time parameter for flowing noise
- Export: renders at full canvas resolution and downloads as PNG with seed in filename
- Controls: scale (0.5–15), octaves, contrast (gamma curve), scroll=scale
- Keyboard: space=new seed, a=animate, e=export
- Added sunset noise thumbnail to index.html

Next ideas:
- A reaction-diffusion GPU explorer
- A tower defense game
- A regex visualizer / tester
- A Perlin noise terrain generator (3D with elevation shading)
- A Spirograph / harmonograph drawing tool

---

## 2026-03-23 — Run 43

Built `spirograph.html`: animated mathematical curve drawing tool.
- 5 curve modes:
  - Spirograph: hypotrochoid `(R-r)cos(t) + d·cos((R-r)/r·t)` with adjustable inner/outer ratio and pen offset
  - Harmonograph: two damped sine oscillators with exponential decay (`e^(-0.0008t)`)
  - Lissajous: `sin(a·t+φ), sin(b·t)` with frequency ratio and phase offset
  - Rose Curve: `r = cos(k·θ)` in polar coordinates where k = p1/p2
  - Maurer Rose: rose curve sampled at integer degree multiples (creates polygonal patterns)
- Progressive drawing: renders N line segments per frame, building up over time
- 7 color schemes: Rainbow (hue cycles with t), Neon Pink, Cyan Glow, Gold, Ice, Fire, White
  - Each uses sinusoidal variation for subtle color breathing
- Glow toggle: `ctx.shadowBlur` for neon bloom effect
- 8 presets: Classic Star, Petals, Chaos Spiral, Harmonic Decay, Lissajous 3:4, Maurer 71°, Rose 7/3, Tight Weave
- 3 parameter sliders (P1, P2, P3) with mode-dependent meaning
- Scroll to adjust P1, shift+scroll for P2
- Speed (1–50 segments/frame), line width (0.3–4px)
- Export current canvas as PNG
- Keyboard: space=pause, r=reset, g=glow, e=export
- Added rainbow hypotrochoid thumbnail to index.html

Next ideas:
- A reaction-diffusion GPU explorer
- A tower defense game
- A regex visualizer / tester
- A Perlin noise terrain generator (3D with elevation shading)
- A Conway's Game of Life pattern library

---

## 2026-03-23 — Run 44

Built `towerdefense.html`: classic tower defense game with procedural path and wave-based enemies.
- Procedural winding path generation: alternating horizontal + vertical segments with random offsets, ensuring a long winding route across the canvas
- 4 tower types with distinct mechanics:
  - Arrow ($10): fast fire rate, single target, moderate damage
  - Cannon ($25): slow fire rate, splash damage in radius, high damage
  - Frost ($20): slows enemies by 50% for 2 seconds, moderate damage
  - Laser ($40): instant beam attack, highest DPS, long range
- Wave-based enemy spawning with 5 enemy types:
  - Normal, Fast (2× speed, low HP), Tank (slow, 3× HP), Swarm (small, many), Boss (huge HP, slow, high reward)
  - Enemy HP and count scale with wave number
- Projectile physics: arrows travel toward targets, cannons explode on impact with splash radius
- Gold economy: start with $100, earn from kills + wave completion bonus, sell towers at 60% cost
- Lives system: enemies reaching the end cost 1 life, game over at 0
- Placement preview: hover shows tower range circle, click to place on valid (non-path, non-occupied) tiles
- 3 game speed settings (1×/2×/3×)
- Tower selection panel with cost display and hotkeys (1-4)
- Wave counter, gold display, lives display in HUD
- Start wave button with auto-start option
- Added path-with-towers thumbnail to index.html

Next ideas:
- A reaction-diffusion GPU explorer
- A regex visualizer / tester
- A Perlin noise terrain generator (3D with elevation shading)
- A Conway's Game of Life pattern library
- A music sequencer / drum machine

---

## 2026-03-23 — Run 45

Built `regex.html`: interactive regex visualizer and tester with real-time matching and railroad diagram.
- Dual-pane layout: test string input (left) with highlighted matches (right), match details sidebar
- Real-time regex compilation with error display on invalid patterns
- Match highlighting with alternating colors for adjacent matches (blue/purple)
- Capture group display: up to 5 color-coded groups per match with index positions
- Railroad-style syntax diagram (bottom panel):
  - Tokenizer parses regex source into: groups, character sets, escapes, literals, dots, anchors, alternation
  - Each token type rendered with distinct color: groups (blue), charsets (gold), escapes (teal), literals (gray), dots (yellow), anchors (pink diamond), alternation (purple chevrons)
  - Quantifiers shown in orange above their token
  - Start/end nodes as filled/hollow circles connected by lines
- 10 presets: Email, URL, IPv4, Date, Hex Color, Phone, HTML Tag, Quoted String, Integers, Words
- 5 regex flags: g (global), i (case insensitive), m (multiline), s (dotAll), u (unicode)
- Replace mode: toggle to show replacement results using $1/$2 back-references
- 80ms debounced input for smooth real-time updates
- Stats bar: match count, group count
- Added railroad-diagram thumbnail to index.html

Next ideas:
- A Mandelbrot/Julia set fractal explorer with zoom
- A markdown editor with live preview
- A color palette generator
- A CSS gradient builder
- A sound synthesizer with ADSR envelope

---

## 2026-03-23 — Run 46

Built `markdown.html`: real-time markdown editor with live preview and custom parser.
- Split-pane layout: editable textarea (left) with rendered HTML preview (right)
- Custom markdown parser (no libraries) handles:
  - Headings (H1–H6) with `#` syntax
  - Bold (`**`/`__`), italic (`*`/`_`), strikethrough (`~~`), inline code
  - Fenced code blocks (```) with language class for syntax display
  - Unordered lists (`-`, `*`, `+`), ordered lists (`1.`, `2.`, etc.)
  - Task lists with checkboxes (`- [x]`, `- [ ]`)
  - Blockquotes (`>`) with nested markdown parsing
  - Tables with header, separator, and data rows
  - Horizontal rules (`---`, `***`, `___`)
  - Links `[text](url)` and images `![alt](src)`
  - Bold+italic combo (`***text***`)
- Toolbar with 18 formatting buttons: B, I, S, code, H1-H3, ul, ol, task, quote, code block, hr, link, img, table
- Keyboard shortcuts: Ctrl+B (bold), Ctrl+I (italic), Tab (indent)
- Synchronized scrolling between editor and preview (percentage-based)
- 4 color themes: Dark (default), Midnight, Sepia, Light
- Word wrap toggle
- Status bar: line count, word count, character count, cursor position
- Export as standalone HTML with embedded styles
- Download raw .md file
- 50ms debounced rendering for smooth real-time updates
- Added split-pane preview thumbnail to index.html

Next ideas:
- A color palette generator with harmony rules
- A CSS gradient builder with visual stops
- A sound synthesizer with ADSR envelope
- A typing speed test with WPM tracking
- A pixel art animation editor (sprite sheets)

---

## 2026-03-23 — Run 47

Built `palette.html`: color palette generator with harmony rules and interactive color wheel.
- 7 harmony rules:
  - Complementary: base + 180deg opposite, fill remaining with nearby offsets
  - Analogous: evenly spaced at 25deg intervals around base
  - Triadic: 3 hues at 120deg intervals
  - Split-Complementary: base + 150deg + 210deg offsets
  - Tetradic: 4 hues at 90deg intervals (rectangle)
  - Monochromatic: same hue with lightness variation across swatches
  - Random: fully random hues, saturation, and lightness
- HSL color math: hsl2rgb, rgb2hsl, hex conversions
- Interactive color wheel (220×220 canvas):
  - Hue ring rendered degree-by-degree with filled arcs
  - Center circle shows base color
  - Harmony dots positioned on ring at each color's hue angle
  - Lines connect dots to show harmony relationships
  - Click wheel to set base hue
- Configurable: 3–8 colors, base color picker, saturation/lightness sliders
- WCAG contrast ratio: calculates relative luminance, shows AA pass/fail badge per swatch
- Lock swatches: click to lock a color so it persists through regeneration
- Double-click swatch to copy hex to clipboard
- CSS variable export: generates `:root { --color-N: #hex; }` block with copy button
- Save/load palettes to localStorage
- Export palette as PNG (200px per swatch × 300px tall)
- Random base button for quick exploration
- Space bar to regenerate unlocked colors
- Added 5-color bar thumbnail to index.html

Next ideas:
- A CSS gradient builder with visual stops
- A sound synthesizer with ADSR envelope
- A pixel art animation editor (sprite sheets)
- A JSON formatter / tree viewer
- A physics sandbox (rigid body with springs and gravity)

---

## 2026-03-23 — Run 48

Built `jsonview.html`: JSON formatter with collapsible tree view and syntax-highlighted output.
- Dual view modes:
  - Tree view: recursive DOM-based collapsible tree with toggle buttons (+/−)
  - Formatted view: syntax-highlighted JSON with color-coded tokens
- Tree features:
  - Collapsible nodes for objects and arrays with item/key count badges
  - Color-coded values: strings (green), numbers (gold), booleans (purple), null (gray), keys (blue)
  - Hover to show JSON path ($.key.nested[0]), click to copy path to clipboard
  - Expand All / Collapse All buttons
- Format / Minify / Sort Keys actions
  - Sort Keys recursively alphabetizes all object keys at every depth
- Configurable indentation: 2 spaces, 4 spaces, or tab
- Search: Ctrl+F opens search bar, highlights matching tree lines, auto-expands collapsed parents to reveal matches
- Syntax highlighting in formatted view using regex-based token coloring
- Error handling: parse errors shown in red bar with position info
- Stats bar: file size, total key count, max nesting depth, root type
- Input size display in header
- Sample data button loads a rich nested example (company/departments/campaigns)
- Tab key inserts correct indentation in textarea
- Keyboard: Ctrl+Enter = format, Ctrl+F = search
- Copy button copies formatted output to clipboard
- Added tree-structure thumbnail to index.html

Next ideas:
- A CSS gradient builder with visual stops
- A sound synthesizer with ADSR envelope
- A pixel art animation editor (sprite sheets)
- A physics sandbox (rigid body with springs and gravity)
- A diff viewer (side-by-side text comparison)

---

## 2026-03-23 — Run 49

Built `gradient.html`: CSS gradient builder with draggable color stops and live preview.
- 3 gradient types: linear (with angle), radial (circle), conic (from angle)
- Repeating gradient toggle for all types
- Interactive stop bar:
  - Draggable stop handles with arrow marker + color swatch + position label
  - Click track to add new stop at that position
  - Selected stop highlighted with blue arrow
- Per-stop editing:
  - Color picker, opacity slider (0–100%), position input (0–100%)
  - Arrow keys to nudge position (±1, Shift+Arrow ±5)
  - Delete/Backspace to remove selected stop (minimum 2)
- Actions: Add Stop (inserts at midpoint), Remove, Reverse, Distribute (evenly space)
- 12 gradient presets rendered as clickable mini-swatches in sidebar
- Random gradient: 2–4 stops with random HSL colors and angle
- Full-size preview with checkerboard background (shows alpha transparency)
- "GRADIENT" text overlay on preview with shadow for readability
- CSS output textarea with copy button — generates complete `background:` property
  - Supports `linear-gradient`, `radial-gradient`, `conic-gradient` and repeating variants
  - RGBA color stops with position percentages
- Angle slider (0–360°) for linear and conic types
- Stop list in sidebar showing all stops with color swatch, hex, position, opacity
- Keyboard: Space = random, Delete = remove stop, Arrow keys = nudge position
- Added gradient-bar thumbnail to index.html

Next ideas:
- A sound synthesizer with ADSR envelope
- A pixel art animation editor (sprite sheets)
- A physics sandbox (rigid body with springs and gravity)
- A diff viewer (side-by-side text comparison)
- A binary/hex/decimal converter calculator

---

## 2026-03-23 — Run 50

Built `diff.html`: side-by-side and unified text diff viewer with character-level highlighting.
- LCS-based diff algorithm:
  - Dynamic programming longest common subsequence for line-level alignment
  - O(mn) DP table with Uint16Array for memory efficiency
  - Fallback simple diff for very large inputs (m*n > 50M)
  - Backtracking to produce same/add/del operations
- Character-level inline diff:
  - Secondary LCS on modified line pairs to identify exact character changes
  - Changed characters highlighted with colored background spans (char-add/char-del)
- Two view modes:
  - Side-by-side: synchronized dual panes with matched line numbers
  - Unified: single pane with +/- prefixes (git-style)
- Configurable context: 3, 5, 10 lines, or full file
  - Chunks separated by `...` separators when context < full
- Color coding: green (added), red (removed), yellow (modified), gray (unchanged), dark (empty filler)
- Minimap: canvas sidebar showing change locations as colored bars, click to scroll
- Chunk navigation: Prev/Next Change buttons, n/j and p/k keyboard shortcuts
- Synchronized scroll between left and right panes
- Stats bar: added/removed/modified/unchanged line counts, chunk count
- Swap button to reverse left/right inputs
- Sample button loads HTML before/after example
- Keyboard: Ctrl+Enter = compare, Escape = back to edit, n/p = navigate changes
- Added side-by-side preview thumbnail to index.html

Next ideas:
- A sound synthesizer with ADSR envelope
- A pixel art animation editor (sprite sheets)
- A physics sandbox (rigid body with springs and gravity)
- A binary/hex/decimal converter calculator
- A cron expression parser and scheduler visualizer

---

## 2026-03-23 — Run 51

Built `baseconv.html`: binary/octal/decimal/hex converter with interactive bit grid and bitwise operations.
- Real-time conversion between 6 representations:
  - Binary (base 2) with space-separated nibbles
  - Octal (base 8)
  - Decimal (base 10) with signed/unsigned toggle
  - Hexadecimal (base 16)
  - Base64 (byte encoding)
  - Custom base (2–36, configurable)
- All fields use BigInt for arbitrary precision within bit width
- Interactive bit grid:
  - Visual 8-bit groups with clickable cells (toggle individual bits)
  - Bit position indices displayed below each cell
  - Color-coded: on bits are blue, off bits are gray
- 4 bit widths: 8-bit, 16-bit, 32-bit (default), 64-bit
  - Automatic masking to selected width
- Signed/unsigned toggle with two's complement display
- Bitwise operations:
  - Shift left/right by configurable amount
  - NOT, AND, OR, XOR with hex operand input
  - Reverse bits, byte swap (endian conversion), population count
- Number info panel:
  - Unsigned and signed (two's complement) decimal values
  - Bits set count, leading/trailing zeros
  - Power of 2 detection with exponent
  - ASCII character for printable range (32–126)
  - IEEE 754 float interpretation for 32-bit values
- "Unix Now" button loads current timestamp
- Copy button per field (strips whitespace)
- Input validation with error highlighting for invalid characters
- Added bit-grid thumbnail to index.html

Next ideas:
- A sound synthesizer with ADSR envelope
- A pixel art animation editor (sprite sheets)
- A physics sandbox (rigid body with springs and gravity)
- A cron expression parser and scheduler visualizer
- A Fourier series visualizer (epicycles drawing shapes)

---

## 2026-03-23 — Run 52

Built `physics.html`: interactive 2D physics sandbox with rigid bodies, springs, and collisions.
- Body types: circles (variable radius) and boxes (variable width/height)
- Physics engine with 4 substeps per frame for stability:
  - Gravity (configurable 0–2000)
  - Spring forces with Hooke's law (stiffness) + velocity damping
  - Velocity integration (semi-implicit Euler)
  - Wall collision with configurable restitution (bounce) and friction
- Collision detection and resolution:
  - Circle-circle: overlap separation + impulse-based velocity exchange
  - Circle-box: local-frame AABB closest-point test, normal transform back to world
  - Tangential friction impulse for realistic sliding
- Spring rendering: zigzag line with 12 segments, stress-colored (blue to red)
- 6 tools:
  - Circle (1): click to spawn, scroll to resize
  - Box (2): click to spawn rectangular bodies
  - Spring (3): click two bodies to connect with spring at rest length
  - Pin (4): toggle pinned/unpinned (static/dynamic)
  - Drag (5): grab and move bodies with spring-like force
  - Erase (6): click to delete body and connected springs
- Right-click: fling body with impulse away from click point
- 4 presets:
  - Stack: 8 circles in a tower
  - Pendulum: chain of 6 bodies on springs from pinned anchor
  - Bridge: 10 nodes connected by springs with pinned endpoints
  - Newton's Cradle: 5 pendulums with stiff springs, leftmost displaced
- Spawn preview: ghost outline follows cursor at current radius
- Configurable: gravity slider, bounce (restitution), friction
- Visual: grid background, body shadows, rotation line on circles, pin indicator
- Stats: body count, spring count, FPS counter
- Keyboard: 1-6 tool select, Space pause, C clear
- Added circles-with-springs thumbnail to index.html

Next ideas:
- A sound synthesizer with ADSR envelope
- A pixel art animation editor (sprite sheets)
- A cron expression parser and scheduler visualizer
- A Fourier series visualizer (epicycles drawing shapes)
- A graph/network editor with force-directed layout

---

## 2026-03-23 — Run 53

Built `fourier.html`: Fourier series visualizer with rotating epicycles that draw shapes.
- Discrete Fourier Transform (DFT):
  - Full complex DFT: computes both positive and negative frequency coefficients
  - For N sample points, calculates amplitude and phase for each frequency k from -N/2 to N/2
  - Coefficients sorted by amplitude descending for progressive approximation
- Epicycle visualization:
  - Chain of rotating circles where each circle represents one Fourier coefficient
  - Circle radius = amplitude, rotation speed = frequency, starting angle = phase
  - Opacity fades with harmonic index for visual clarity
  - Tip traces the reconstructed path over time
- 9 preset shapes:
  - Square wave, Sawtooth, Triangle (polygon-based generation)
  - Circle, Star (5-pointed with inner/outer radius interpolation)
  - Heart (parametric: 16sin^3(t), 13cos(t)-5cos(2t)-2cos(3t)-cos(4t))
  - Treble clef, Pi symbol (parametric approximations)
  - Custom drawing: freehand draw panel with resampling to 300 points
- Custom drawing panel:
  - 500x500 canvas overlay with crosshair guides
  - Freehand mouse drawing, resampled via linear interpolation to 300 uniform points
  - Scaled to fit the main viewport
- Trace rendering: faded HSL-colored line that builds up over time (max 8000 points)
- Waveform display: y-component of trace shown as scrolling wave on right side
- Amplitude spectrum: bar chart of harmonic amplitudes in bottom-right corner
- Original shape shown as faint ghost path behind the epicycles
- 1–200 harmonics (configurable via slider or scroll wheel)
- Speed control, pause, clear trace
- Toggle visibility: circles, radii, original path
- Horizontal projection line from tip to waveform
- Keyboard: Space = pause, R = reset trace, scroll = harmonics
- Added epicycle-with-trace thumbnail to index.html

Next ideas:
- A sound synthesizer with ADSR envelope
- A pixel art animation editor (sprite sheets)
- A cron expression parser and scheduler visualizer
- A graph/network editor with force-directed layout
- A ray casting 2D visibility / shadows demo

---

## 2026-03-23 — Run 54

Built `raycast.html`: 2D ray casting visibility and shadow demo with interactive wall drawing.
- Ray casting algorithm:
  - Casts rays from light source toward every segment endpoint (+ tiny angle offsets ±0.0001 for edge accuracy)
  - Additional uniform rays (30–1000 configurable) fill gaps between endpoint-directed rays
  - Ray-segment intersection: parametric t/u calculation with denominator check for parallel lines
  - Rays sorted by angle, hits form visibility polygon
  - Rays capped at configurable light radius (50–2000)
- Lighting:
  - Soft shadows: radial gradient (4-stop) clipped to visibility polygon for realistic falloff
  - Hard shadows: flat-color polygon fill alternative
  - Light source rendered as radial glow dot
  - Configurable intensity (10–100%) and color picker
- Wall system:
  - Click+drag to draw wall segments
  - Canvas boundaries automatically included as 4 boundary segments
  - Wall endpoints rendered as dots, walls as thick blue lines
  - Click to erase nearest wall (within 15px distance-to-segment threshold)
- Multi-light mode:
  - Toggle to enable multiple light sources
  - Right-click to place additional lights (auto-cycled colors)
  - Each light independently casts its own visibility polygon
  - Additive blending for overlapping light areas
- 3 tools: Place Wall (1), Move Light (2), Erase (3)
- 4 presets:
  - Maze: random horizontal/vertical grid segments (40% density)
  - Pillars: grid of square pillars (4 segments each)
  - Room: outer walls with doorways + interior partitions
  - Spiral: 40-segment Archimedean spiral wall
- Show Rays toggle: visualize individual ray lines
- Custom crosshair cursor (hidden native cursor)
- Scroll wheel adjusts ray count
- Keyboard: 1-3 tool select, C clear
- Added light-with-shadows thumbnail to index.html

Next ideas:
- A sound synthesizer with ADSR envelope
- A pixel art animation editor (sprite sheets)
- A cron expression parser and scheduler visualizer
- A graph/network editor with force-directed layout
- A kaleidoscope drawing tool

---

## 2026-03-23 — Run 55

Built `netgraph.html`: interactive network graph editor with force-directed layout.
- Force-directed simulation:
  - Coulomb repulsion: O(n^2) all-pairs repulsive force inversely proportional to distance squared
  - Hooke spring attraction: edges act as springs with configurable rest length (100px)
  - Center gravity: weak constant pull toward origin to prevent drift
  - Velocity damping (configurable 50–99%) and speed clamping (max 50 units/frame)
  - Configurable repulsion (500–20000), attraction (0.001–0.1), damping
- 4 tools:
  - Add Node (N): click empty space to create, click existing to select
  - Add Edge (E): click two nodes sequentially to connect (duplicate check)
  - Drag (D): grab nodes to reposition, or pan the view
  - Erase (X): click to delete node and all connected edges
- Node properties panel:
  - Editable label, color picker, size slider (8–40)
  - Pin/Unpin toggle to fix position during simulation
  - Double-click to rename via prompt
- Pan & zoom:
  - Scroll wheel zooms toward cursor (0.1x–5x range)
  - Middle-click or Alt+click to pan, or drag empty space in Drag mode
  - World-space grid rendered behind graph
- Visual:
  - Nodes with colored fill + stroke, glow on hover/select
  - Edges highlighted when connected to selected node
  - Degree count (d=N) displayed above each node
  - Labels below nodes (truncated at 8 chars)
  - Pin indicator (white dot) on pinned nodes
- 6 presets:
  - Binary Tree: depth 4 with spreading layout
  - Mesh Grid: 4×5 grid with horizontal + vertical edges
  - Social Network: 12 named nodes with random connections
  - Ring: 12 nodes in a cycle
  - Petersen Graph: classic 5-outer/5-inner non-planar graph
  - Random: 20 nodes with ~30 random edges
- Keyboard: N/E/D/X = tools, Space = toggle simulation, Delete = remove selected, P = pin, C = center
- Added nodes-and-edges thumbnail to index.html

Next ideas:
- A sound synthesizer with ADSR envelope
- A pixel art animation editor (sprite sheets)
- A cron expression parser and scheduler visualizer
- A kaleidoscope drawing tool
- An A* pathfinding visualizer on a grid

---

## 2026-03-23 — Run 56

Built `pathfind.html`: pathfinding algorithm visualizer with animated search on a grid.
- 6 algorithms implemented as JavaScript generators for step-by-step animation:
  - A* (Manhattan heuristic): optimal weighted search with f = g + h
  - A* (Euclidean heuristic): uses straight-line distance
  - Dijkstra: uniform cost search (A* with h=0)
  - BFS: breadth-first, guarantees shortest path in unweighted graphs
  - DFS: depth-first, explores deeply first (not optimal)
  - Greedy Best-First: pure heuristic (fast but not guaranteed optimal)
- MinHeap priority queue for A*/Dijkstra/Greedy (O(log n) push/pop)
- Grid system:
  - Dynamic sizing based on canvas dimensions (20px cells)
  - Cell types: empty, wall, start (S), end (E), weighted (5× cost)
  - Search states: unvisited, frontier, visited, path
- 5 tools: Wall (W), Start (S), End (E), Weight (G), Eraser (R)
  - Click+drag for continuous wall/erase painting
- Diagonal movement toggle (8-directional with √2 cost for diagonals)
- Animated visualization:
  - Configurable speed (1–200 steps per frame)
  - Visited cells colored dark blue, frontier cells teal
  - Path traced in gold after search completes
- 5 maze generators:
  - Recursive backtracking: fill-and-carve with randomized DFS
  - Random 30%/50%: scatter walls at given density
  - Spiral: concentric spiral wall pattern
  - Rooms: 8 random rectangular rooms with doorways
- Path tracing: follows parent pointers from end to start
- Stats: visited count, path length, total cost, elapsed time, grid dimensions
- Keyboard: W/S/E/G/R = tools, Space = run/stop, C = clear all
- Added grid-with-path thumbnail to index.html

Next ideas:
- A sound synthesizer with ADSR envelope
- A pixel art animation editor (sprite sheets)
- A cron expression parser and scheduler visualizer
- A kaleidoscope drawing tool
- A sand/powder simulation (falling sand game)

---

## Run 57 — Kaleidoscope Drawing Tool
**File:** `kaleidoscope.html`
**Date:** 2026-03-23

Chose "A kaleidoscope drawing tool" from the Run 56 ideas list.

### What it does
An interactive kaleidoscope drawing canvas with rotational symmetry. Draw in any sector and strokes are replicated across all segments with optional mirror reflection.

### Key features
- 2–24 rotational symmetry segments with adjustable count
- Mirror mode: reflects strokes across segment bisectors (doubles visual density)
- 5 brush types: Round, Square, Star (5-point), Diamond, Spray (particle scatter)
- 6 color modes: Fixed (color picker), Rainbow (cycling hue), Pastel, Fire (warm tones), Ocean (cool tones), Neon (hard color switching)
- Glow effect: canvas shadowBlur creates soft luminous halos around strokes
- Fade mode: semi-transparent background overlay slowly dissolves older strokes
- Brush size (1–40), opacity (5–100%), scroll wheel for quick size adjustment
- Stroke interpolation: intermediate points drawn along movement vector for smooth continuous lines
- Undo history: 15 states stored via getImageData/putImageData
- Guide lines: faint radial lines from center showing segment boundaries (hidden while drawing)
- Touch support for mobile devices
- PNG export
- Keyboard shortcuts: C=clear, Z=undo, G=glow, M=mirror, F=fade, +/- = segments
- Added rotational-symmetry-pattern thumbnail to index.html

Next ideas:
- A sound synthesizer with ADSR envelope
- A pixel art animation editor (sprite sheets)
- A cron expression parser and scheduler visualizer
- A sand/powder simulation (falling sand game)
- A circuit logic gate simulator

---

## Run 58 — Falling Sand Simulation
**File:** `sand.html`
**Date:** 2026-03-23

Chose "A sand/powder simulation (falling sand game)" from the Run 57 ideas list.

### What it does
A cellular automaton powder/falling sand simulation with 10 interactive materials that follow physics rules and interact with each other.

### Key features
- 10 materials: Sand, Water, Stone, Wood, Fire, Oil, Acid, Steam, Lava, Plant
- Material interactions:
  - Sand sinks through water and oil (density displacement)
  - Fire burns wood, oil, and plants; has short random lifespan
  - Fire + water = steam; fire produces smoke
  - Lava flows slowly, ignites flammable materials, turns water to steam, cools to stone
  - Acid dissolves non-stone materials and is consumed in the process
  - Steam rises, drifts sideways, condenses back to water or dissipates
  - Oil floats on water (density sorting)
  - Plants grow when adjacent to water, consuming water to spread
- Grid-based simulation with 3px cells for fine resolution
- Alternating left/right scan direction per tick to prevent directional bias
- Circular brush with configurable radius (1–20), interpolated strokes for continuous painting
- Deterministic color noise per cell for visual variety (no flicker)
- Fire/lava use random color for flickering flame effect
- Touch support for mobile
- Keyboard: 1-9 = materials, 0 = erase, C = clear, P = pause
- Scroll wheel adjusts brush size
- Status bar: particle count, FPS, grid dimensions
- Added layered-materials thumbnail to index.html

Next ideas:
- A sound synthesizer with ADSR envelope
- A pixel art animation editor (sprite sheets)
- A cron expression parser and scheduler visualizer
- A magnetic field line visualizer
- An interactive periodic table

---

## Run 59 — Magnetic Field Visualizer
**File:** `magfield.html`
**Date:** 2026-03-23

Chose "A magnetic field line visualizer" from the Run 58 ideas list.

### What it does
An interactive 2D magnetic field visualizer where users place North and South poles and see computed field lines, arrow grids, or potential heatmaps in real time.

### Key features
- Place N (positive) and S (negative) magnetic poles with configurable strength (1–10)
- 4 visualization modes:
  - Field Lines: traces from N poles outward using field direction integration (RK1/Euler steps)
  - Arrow Grid: uniform grid of arrows showing field direction and magnitude (log-scaled length)
  - Both: combined field lines + arrow overlay
  - Potential Map: scalar potential heatmap (blue=negative, red=positive) via pixel-level computation
- Field computation: 2D monopole model, B ∝ 1/r², summed across all poles
- Configurable line count (8–64), integration steps (50–500)
- Drag poles to rearrange in real time
- Right-click to delete poles
- Animated flow dots along field lines showing field direction
- Color mode: rainbow hue per line or monochrome blue
- 3 presets: Dipole, Quadrupole, Parallel (4-pole)
- Pole rendering: colored circles with radial glow (red=N, blue=S)
- Lines terminate when reaching opposite pole or leaving canvas bounds
- Touch support for mobile
- Keyboard: N/S = toggle polarity, C = clear, A = animate
- Added dipole-field-lines thumbnail to index.html

Next ideas:
- A sound synthesizer with ADSR envelope
- A pixel art animation editor (sprite sheets)
- A cron expression parser and scheduler visualizer
- An interactive periodic table
- A hex color memory matching game

---

## Run 60 — Interactive Periodic Table
**File:** `periodic.html`
**Date:** 2026-03-23

Chose "An interactive periodic table" from the Run 59 ideas list.

### What it does
A complete interactive periodic table of all 118 elements with detailed property display, multiple coloring modes, temperature-dependent phase visualization, and search.

### Key features
- All 118 elements with data: number, symbol, name, mass, category, phase, block, period, group, electronegativity, melting/boiling points, density, electron configuration, discovery year
- Standard 18-column layout with lanthanides/actinides in separate rows below
- 5 color modes:
  - Category: alkali metal, alkaline earth, transition metal, post-transition, metalloid, reactive nonmetal, noble gas, lanthanide, actinide
  - Phase: solid/liquid/gas at current temperature
  - Block: s/p/d/f orbital blocks
  - Period: hue gradient across periods 1-7
  - Electronegativity: blue-to-warm gradient (Pauling scale 0-4)
- Temperature slider (0-6000K): dynamically recalculates phase state per element using melting/boiling points
- Search: filter by name, symbol, or atomic number (non-matching elements dimmed)
- Click element for detail panel: shows all properties including electron configuration and discovery year
- Category badge with color coding in detail view
- Hover: scale-up highlight effect on cells
- Responsive grid layout with aspect-ratio cells
- Lanthanide/actinide labels and period 6-7 placeholders
- Added mini-grid thumbnail to index.html

Next ideas:
- A sound synthesizer with ADSR envelope
- A cron expression parser and scheduler visualizer
- A hex color memory matching game
- A bouncing DVD logo screensaver
- An analog clock with multiple timezone support
