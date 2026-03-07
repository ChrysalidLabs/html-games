=====================================================
HEX SENTINEL: SIGNAL BREACH - PROJECT POST-MORTEM
=====================================================
Status: VERSION 1.0 (STABLE / FEATURE COMPLETE)
Build Period: 5 Days
Development Model: AI-Pair Programming (Iterative Sprints)

-----------------------------------------------------
1. RESOURCE & PERFORMANCE METRICS
-----------------------------------------------------
Total Development Time: ~5 Days 
Total Sprints: 8 Major Sprints
Total Tokens Processed: ~1,150,000 Tokens (Cumulative)

The high token count reflects the "Full-Context" approach 
used, where the entire 1,500+ line codebase was re-analyzed 
during every bug-fix and feature addition to ensure 
system-wide stability and zero-dependency integrity.

-----------------------------------------------------
2. SPRINT SUMMARY
-----------------------------------------------------
SPRINT 1: CORE ENGINE
- Implementation of Axial Hex-Grid math.
- Development of the seedable procedural generator (xmur3).
- Creation of the "Occlusion Culling" rendering loop.

SPRINT 2: ENTITY & COMBAT LOGIC
- Scripting the Sentinel (Boss) orbital strike patterns.
- Building the projectile physics and collision detection.
- Establishing the "Energy as Ammo" economy.

SPRINT 3: WIKIPEDIA INTEGRATION
- Connecting the MediaWiki API for real-time data fetching.
- Architecting the "Signal Breach" mini-game UI.

SPRINT 4: THE DATA TRANSLATOR (PILLARS)
- Developing the "Smart" Regex logic to categorize 
  raw Wikipedia data into BIOS, TECH, CHRONOS, ETHOS, and LOGOS.

SPRINT 5: REFACTORING & REDUNDANCY CLEANUP
- Consolidation of duplicate functions.
- Optimization of the global 'world' state object.

SPRINT 6: UX & HUD POLISH
- Centering the Sentinel Core status and Sector Tracking.
- Implementation of the DPR (Device Pixel Ratio) scaling for 4K.

SPRINT 7: BUG HUNTING (FINAL)
- Fixed Sentinel Shield reset logic on level advance.
- Squashed the "Input Ghosting" bug (instant-fire prevention).
- Hard-coded the Stake-Slider limit to 5 for game balance.

SPRINT 8: DOCUMENTATION & SHIPPING
- Generation of anchors and finalized Git README.

-----------------------------------------------------
3. TECHNICAL SPECIFICATIONS
-----------------------------------------------------
- LANGUAGE: Vanilla JavaScript (ES6)
- RENDERER: HTML5 Canvas 2D
- ARCHITECTURE: Single-File / Zero-Dependency
- INPUTS: Mouse (UI/Aim), WASD/Arrows (Move), Space (Fire)

-----------------------------------------------------
4. CORE GAMEPLAY LOOP
-----------------------------------------------------
1. EXPLORE: Navigate the procedural grid to find energy.
2. BREACH: Interact with Signal nodes to risk energy 
   for a 3x multiplier via Wikipedia categorization.
3. COMBAT: Use collected energy to strip Sentinel 
   shields and destroy the Core.
4. ADVANCE: Move to the next Sector with increased 
   difficulty and fresh terrain.

-----------------------------------------------------
