=====================================================
HEX SENTINEL: SIGNAL BREACH - TECHNICAL POST-MORTEM
=====================================================
Classification: Portfolio Piece / Technical Demo
Lead PM: [Your Name]
Framework: Zero-Dependency Vanilla JS
Context: 5-Day Iterative Sprint (AI-Augmented)
Total Tokens: ~1,150,000

-----------------------------------------------------
1. EXECUTIVE SUMMARY (THE PM PERSPECTIVE)
-----------------------------------------------------
This project demonstrates the ability of a non-coding Technical PM 
to architect, debug, and ship a complex, data-integrated software 
product. By managing logic flow rather than syntax, the PM 
successfully steered the project through 8 distinct sprints, 
handling real-time API integration and procedural generation.

-----------------------------------------------------
2. TECHNICAL SECRETS & ARCHITECTURE (THE "DEEP DIVE")
-----------------------------------------------------

[A] THE "GHOST" STATE & INPUT BUFFERING
Secret: To prevent "Input Ghosting" (where a player fires ammo while 
transitioning between game states), the PM implemented a manual 
Keyboard Buffer Flush. 
Logic: Upon `world.reset()`, the `keysDown` set is forced to .clear(), 
decoupling the hardware input from the game logic during state changes.

[B] PROCEDURAL OCCLUSION CULLING
Secret: Rendering thousands of hexes would crash a browser. The 
engine uses "Viewport Clipping."
Logic: Instead of drawing the world, the `loop()` calculates the 
min/max axial coordinates visible within `innerWidth` and 
`innerHeight`. Only hexes within that mathematical "window" are 
pushed to the GPU, allowing for infinite-feeling maps at 60FPS.

[C] DATA TRANSLATION (THE 5-PILLAR REGEX)
Secret: Mapping the entire Wikipedia database to 5 game categories 
is done via a "Weighted Keyword Heuristic."
Logic: The `getWikiCategory` function doesn't just look for words; 
it uses a tiered Regex search. If a string contains "Species" and 
"Kingdom," it's BIOS; if it contains "Battle" and "Dynasty," it's 
CHRONOS. This creates a "Smart Translator" that feels like AI to 
the player but is actually high-efficiency pattern matching.

[D] MEMORY LEAK PREVENTION (THE TILE CAP)
Secret: The "Tile Explosion" fix.
Logic: By hard-coding `slider.max = 5`, the PM enforced a strict 
memory limit. Since each reward tile is a unique ID in the 
`world.visited` set, capping the reward at 15 prevents the 
JavaScript heap from expanding exponentially during long sessions.

[E] THE "FAKE" 3D (2.5D PROJECTION)
Secret: The game uses no 3D libraries (Three.js/WebGL).
Logic: It uses high-school trigonometry (sin/cos) within the 
Canvas 2D context to project 3D coordinates onto a 2D plane, 
simulating depth through scale and vertical offset.

-----------------------------------------------------
3. CORE FUNCTION DICTIONARY
-----------------------------------------------------
- generateLevel(seed): Deterministic world-building using xmur3.
- updateSentinel(): The "Lead-Targeting" AI for orbital strikes.
- hex21.checkWin(): The core multiplier logic for resource reward.
- playSfx(): Real-time audio synthesis (Web Audio API).

-----------------------------------------------------
4. SPRINT HISTORY & LOGISTICS
-----------------------------------------------------
- SPRINT 1: Math Foundation (Hex Geometry & Occlusion).
- SPRINT 2: Audio/Visual (Web Audio Synthesis & 2.5D Projection).
- SPRINT 3: Connectivity (MediaWiki API & Async Data Fetching).
- SPRINT 4: Gameplay Balance (Pillar Regex & Stake Scaling).
- SPRINT 5: UX/UI (HUD Relocation, DPR Scaling, & Final Polish).

-----------------------------------------------------
5. PM REVIEW: LEADERSHIP & STRATEGY
-----------------------------------------------------
The PM (Non-Coder) acted as the System Architect, making high-level 
decisions on:
1. Resource Economy: Designing the "Risk vs. Reward" loop.
2. Technical Constraints: Opting for a single-file build to ensure 
   portability and zero-latency performance.
3. Rapid Troubleshooting: Identifying and fixing the Sentinel 
   Shield Reset bug and the Stake Over-inflation bug within the 
   final sprint.

Final Verdict: This project proves that Technical PMs can 
successfully navigate complex codebase management, drive 
optimization, and deliver a "Playable Final State" through 
strategic AI-pairing and logical rigor.
=====================================================

To complete your portfolio documentation, here are the How to Play instructions and the Mission Protocols. This section is written in a high-flavor "in-universe" style that matches the game's aesthetic while clearly explaining the mechanics you've balanced over the last 5 days.

[ MANUAL OVERRIDE: OPERATIONAL GUIDE ]
I. CONTROL SCHEME
MOVEMENT: Use WASD or ARROW KEYS to navigate the hex-grid. The world generates procedurally as you move; keep an eye on your coordinates.

COMBAT: Press SPACEBAR to fire a pulse of collected energy at the Sentinel or its projectiles.

Note: Every shot consumes 1 Energy Tile.

INTERACTION: Use your MOUSE to select options during a Signal Breach and to navigate the HUD.

II. MISSION PROTOCOLS (THE GAME LOOP)
1. HARVESTING PHASE
Explore the grid to collect "Unspent Energy" (Tiles). Your total current ammo is displayed in the top-left HUD. You cannot fight the Sentinel without a steady supply of energy.

2. THE SIGNAL BREACH (RISK/REWARD)
Locate specialized Pillars on the map to initiate a Signal Breach.

The Stake: You may risk up to 5 Energy Tiles.

The Challenge: You will be presented with raw data intercepted from the "Old World" (Wikipedia).

Categorization: You must correctly identify which of the 5 Pillars the data belongs to:

BIOS: Biological, Medical, or Organic.

TECH: Scientific, Mathematical, or Mechanical.

CHRONOS: Historical, Political, or Geographical.

ETHOS: Cultural, Artistic, or Social.

LOGOS: Logic-based, Abstract, or Philosophical.

The Payout: A successful categorization returns 3x your stake (Max 15 tiles). Failure results in a total loss of the staked energy.

3. SENTINEL ENGAGEMENT
The orbital Sentinel will track your movement and fire area-of-effect strikes.

Shield Depletion: The Sentinel is protected by a 10-layer physical shield. You must land 10 successful hits to expose the Core.

Core Destruction: Once the shields are down, a final strike to the Sentinel Core will trigger a Sector Reset.

4. SECTOR ADVANCEMENT
Upon the Sentinel's defeat, you will advance to the next SECTOR.

The world re-seeds with new terrain.

The Sentinel's shields are fully restored.

Difficulty and projectile frequency increase as you climb higher into the sectors.

III. SURVIVAL HEURISTICS (PM SECRETS)

Stake Wisely: Because the PM has capped the maximum stake at 5, you should use the Signal Breach frequently to "top off" your ammo rather than waiting until you are empty.

Culling Awareness: The world only exists where you can see it. Use the edges of the screen to your advantage to lose trailing projectiles.

PM Technical Note for Portfolio:
The "Mission Protocols" effectively explain the Resource Economy you designed. By limiting the risk to 5 tiles, you transformed the Signal Breach from a "luck-based win button" into a strategic reload mechanic that is essential for surviving the higher Sectors.
