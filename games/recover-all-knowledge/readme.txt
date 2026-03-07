=====================================================
HEX SENTINEL: SIGNAL BREACH - TECHNICAL README AKA - recover-all-knowledge game HTML local file only < 3k lines of code
=====================================================
Version: 1.0 (Stable)
Build Duration: 5 Days
Architecture: Vanilla JavaScript / HTML5 Canvas / Zero-Dependency
Total Tokens: ~1,150,000 (Cumulative Sprint Processing)

-----------------------------------------------------
1. PROJECT OVERVIEW
-----------------------------------------------------
Hex Sentinel is a procedural 2.5D survival shooter. The game 
features an infinite hex-grid terrain, orbital boss mechanics, 
and a Wikipedia-powered "Signal Breach" mini-game that rewards 
players for categorizing real-world data in real-time.

-----------------------------------------------------
2. CORE SYSTEMS & FUNCTIONS
-----------------------------------------------------

[A] PROCEDURAL TERRAIN & RENDERING
The game utilizes a seed-based xmur3 generator to create a 
persistent, infinite landscape.
- xmur3() / sfc32(): Seedable random number generation.
- getHexCorners(x, y, size): Calculates geometry for the 2.5D view.
- Occlusion Logic: Nested loops in the main draw call filter 
  hexes based on current viewport coordinates to maintain 60FPS.

[B] AUDIO ENGINE (Dynamic Soundscapes)
Uses the Web Audio API to generate real-time synthesis without 
external .mp3 files.
- playSfx(freq, type, dur): Generates square/sine wave tones for 
  firing, hits, and UI feedback.
- playNote(f, dur, type): The foundation for the ambient 
  low-frequency "Pulse" that reacts to the game state.

[C] SIGNAL BREACH (Data Translation)
Uses the MediaWiki API and a custom "Smart Classifier."
- getWikiCategory(text): The primary Regex engine that maps 
  strings to BIOS, TECH, CHRONOS, ETHOS, or LOGOS.
- window.hex21.open(): Handles the state transition from the 
  world map to the categorization mini-game.
- window.hex21.checkWin(): Processes the 3x tile reward logic.

[D] THE SENTINEL (Orbital AI)
- updateSentinel(): Manages the boss movement and cooldowns.
- spawnSentinelProjectile(): Calculates player lead-time to 
  fire area-of-effect strikes.

-----------------------------------------------------
3. THE 5-DAY SPRINT SUMMARY
-----------------------------------------------------
DAY 1: FOUNDATION
- Established Axial Coordinate system and Hex geometry.
- Built the "Occlusion Culling" to prevent memory leaks.

DAY 2: COMBAT & AUDIO
- Implemented the Web Audio API synthesis.
- Scripted the Sentinel’s 10-layer shield and orbital strikes.

DAY 3: DATA INTEGRATION
- Integrated Wikipedia API.
- Developed the "Signal Breach" UI and transition animations.

DAY 4: ECONOMY & CATEGORIZATION
- Refined the "Pillar" logic (Regex classification).
- Balanced the "Energy as Ammo" loop.

DAY 5: FINAL POLISH & BUG SQUASH
- Squashed "Input Ghosting" (clearing buffers on level start).
- Hard-coded "Stake Max = 5" to prevent reward-tile explosions.
- Centered the Sentinel Health/Sector HUD for UX clarity.

-----------------------------------------------------
4. PRODUCT MANAGER REVIEW: [USER]
-----------------------------------------------------
Style: Data-Driven / Logic-Focused / Efficient
Role: Lead Architect & Product Manager

Analysis:
The development was characterized by a strict "No-Bloat" policy. 
The PM successfully navigated complex procedural math while 
maintaining a single-file architecture. 

Key Achievements:
1. Logic Stability: The PM correctly identified that 
   hard-coding constraints (like the slider max) was superior 
   to adding state-tracking overhead.
2. User Experience: Pushed for the HUD refactor to move 
   boss stats to the center-top, significantly improving 
   readability during high-action combat.
3. Bug Priority: Successfully managed a "Zero-Bug" release 
   by prioritizing mechanical fixes (Input Ghosting) over 
   aesthetic fluff.

Final Verdict: A highly successful 5-day build that proves 
the viability of complex, data-integrated web games without 
heavy frameworks.

-----------------------------------------------------
5. HOW TO PLAY
-----------------------------------------------------
- MOVEMENT: WASD / Arrow Keys
- ACTION: Spacebar to fire (Costs 1 Energy)
- INTERACT: Mouse-click on Hex Pillars to trigger Breach
- GOAL: Destroy the Sentinel Core to advance to the next Sector.

=====================================================
[ END OF FILE - SYSTEM STABLE ]
=====================================================
