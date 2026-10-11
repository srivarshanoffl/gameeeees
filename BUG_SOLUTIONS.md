# SuperHero Games Debugging Challenges — Developer Solutions Reference

> **DEVELOPER-ONLY REFERENCE DOCUMENTATION**  
> Complete technical breakdown and verified browser DevTools solutions for all eight superhero browser debugging challenges.  
> Games 1–4 feature real DOM/HTML defect challenges. Games 5–8 feature real CSS defect challenges.  
> *Note: Deadpool (Game 9) is strictly excluded from modifications and testing per project specification.*

---

## Game 1: Vision

1. **Game Number & Name**: Game 1 — Vision
2. **Assigned Bug Category**: HTML
3. **Exact Target File, Element & Attribute**:
   - **File**: `vision and bifrost/avengers.html`
   - **Target Element**: `<div id="jarvis-core" class="matrix-module">`
   - **Location**: Inside `#lab-screen` / `#scene-mindstone` cradle module container
   - **Attribute**: `id="jarvis-core"`
4. **Original Intentional Defect**:
   The primary neural network module element is misattributed with `id="jarvis-core"` instead of the required `id="jarvis-matrix"`.
5. **Why the Defect Breaks Intended Behavior**:
   During the synthetic neural transfer sequence, the cradle initialization engine checks the live DOM for `document.getElementById('jarvis-matrix')` to synchronize the Mind Stone energy pathways with J.A.R.V.I.S. memory nodes. Because the node ID is misnamed, the uplink fails, triggering an Asgardian/Stark diagnostic error (`DOM Error: target element 'jarvis-matrix' not found in document`) and pausing the cinematic sequence in debug mode.
6. **Exact Correction Required**:
   In the browser's Developer Tools Elements panel or via Console, edit the element's `id` attribute from `jarvis-core` to `jarvis-matrix`.
7. **Exact Console Command**:
   ```javascript
   document.getElementById('jarvis-core').id = 'jarvis-matrix';
   ```
8. **Expected Result After Correction**:
   The runtime watcher detects the presence of `#jarvis-matrix`. The diagnostic terminal status changes to `✓ DOM NODE #jarvis-matrix IDENTIFIED — ONLINE`, the diagnostic HUD fades out, the cradle repowers with a golden energy surge, and the cinematic advances into `sceneRestored()`, culminating in Vision's awakening.
9. **Verification Mechanism**:
   A lightweight polling loop and `MutationObserver` inside `Debug.open()` monitor the live DOM for `document.getElementById('jarvis-matrix')`.
10. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Renaming the element ID restored the J.A.R.V.I.S. matrix node, closed the diagnostic HUD, and triggered the restored sequence. Mission restart cleanly restores the initial `id="jarvis-core"` defect.
11. **Unresolved Limitations**:
    None.

---

## Game 2: Civil War

1. **Game Number & Name**: Game 2 — Civil War
2. **Assigned Bug Category**: HTML
3. **Exact Target File, Element & Attribute**:
   - **File**: `civil war/civilwar.html`
   - **Target Element**: `<div id="arc-reactor" data-vitals="offline">`
   - **Location**: Inside `#im` (Iron Man character container)
   - **Attribute**: `data-vitals="offline"`
4. **Original Intentional Defect**:
   The Arc Reactor telemetry node in Tony Stark's armor has its custom HTML data attribute set to `data-vitals="offline"`.
5. **Why the Defect Breaks Intended Behavior**:
   Following the climax where Captain America strikes Iron Man's chest, Tony Stark collapses with critical armor failure. The game state halts in `DEBUG_PAUSE` awaiting life support recovery. The recovery script requires `#arc-reactor` to exhibit `data-vitals="online"`.
6. **Exact Correction Required**:
   In DevTools Elements panel or Console, update the `data-vitals` attribute of `#arc-reactor` from `"offline"` to `"online"`.
7. **Exact Console Command**:
   ```javascript
   document.getElementById('arc-reactor').setAttribute('data-vitals', 'online');
   ```
8. **Expected Result After Correction**:
   The life support verification system detects `data-vitals="online"`. Iron Man's Arc Reactor pulses with renewed turquoise energy, Tony Stark rises into a revived kneeling pose, Captain America's vibranium shield drops and grounds onto the battlefield floor, and Steve Rogers vanishes into the shadows, transitioning the mission to victory.
9. **Verification Mechanism**:
   A lightweight runtime polling interval (`pollTimer = setInterval(..., 200)`) in `civilwar.html` evaluates `document.getElementById('arc-reactor').getAttribute('data-vitals') === 'online'`.
10. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Modifying the attribute promptly revives Tony Stark, triggers shield grounding physics, and fades Captain America into the background. Calling `window.resetAll()` resets `data-vitals` to `"offline"`.
11. **Unresolved Limitations**:
    None.

---

## Game 3: Ragnarok

1. **Game Number & Name**: Game 3 — Ragnarok
2. **Assigned Bug Category**: HTML
3. **Exact Target File, Element & Attribute**:
   - **File**: `vision and bifrost/bifrost.html`
   - **Target Element**: `<button id="bifrost-actvate" class="gate-btn">`
   - **Location**: Inside `#bifrost-conduit` / Asgardian gate interface panel
   - **Attribute**: `id="bifrost-actvate"` (typographical defect missing the letter `i`)
4. **Original Intentional Defect**:
   The primary gate activation button element ID is misspelled as `bifrost-actvate` instead of `bifrost-activate`.
5. **Why the Defect Breaks Intended Behavior**:
   The realm evacuation protocol queries the DOM for `#bifrost-activate` to bind the interactive rainbow conduit trigger. Because the element ID is defective, the gate controller fails to bind the activation trigger, causing the Bifrost bridge to remain locked in `st-debug` mode.
6. **Exact Correction Required**:
   Using the Elements panel or JavaScript Console, correct the button element's `id` attribute to `bifrost-activate`.
7. **Exact Console Command**:
   ```javascript
   document.getElementById('bifrost-actvate').id = 'bifrost-activate';
   ```
8. **Expected Result After Correction**:
   The live watcher identifies `document.getElementById('bifrost-activate')`. `STATE.challengeSolved` and `STATE.activationUnlocked` become `true`, the diagnostic HUD reports `✓ BIFROST DOM BUG FIXED`, the activation button becomes interactive, and clicking it unleashes the rainbow Bifrost beam to evacuate Asgard.
9. **Verification Mechanism**:
   Lightweight DOM watcher polling in `openDebug()` checking `document.getElementById('bifrost-activate') !== null`.
10. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Live correction unlocks gate controls and allows the rainbow bridge sequence to conclude. `window.resetMission()` cleanly restores `bifrost-actvate`.
11. **Unresolved Limitations**:
    None.

---

## Game 4: Endgame

1. **Game Number & Name**: Game 4 — Endgame
2. **Assigned Bug Category**: HTML
3. **Exact Target File, Element & Attribute**:
   - **Files**: `endgame/endgame.html` and `endgame/index.html` (with styles in `endgame/css/style.css` and logic in `endgame/js/app.js`)
   - **Target Element**: `<div class="cosmic-energy" id="cosmicEnergy" data-resonance="disabled">`
   - **Location**: Inside `#stage` / `#world` nanotech gauntlet assembly
   - **Attribute**: `data-resonance="disabled"`
4. **Original Intentional Defect**:
   The cosmic energy conduit node possesses `data-resonance="disabled"`.
5. **Why the Defect Breaks Intended Behavior**:
   The stylesheet rule `.cosmic-energy[data-resonance="active"] { display: block; }` suppresses energy propagation through the Infinity Gauntlet circuits when `data-resonance` is disabled. When Tony Stark snaps his fingers, energy cannot propagate across the gauntlet, halting the cinematic in `S.DEBUG` state.
6. **Exact Correction Required**:
   In the Elements panel or Console, update `data-resonance` on `#cosmicEnergy` from `"disabled"` to `"active"`.
7. **Exact Console Command**:
   ```javascript
   document.getElementById('cosmicEnergy').setAttribute('data-resonance', 'active');
   ```
8. **Expected Result After Correction**:
   The runtime polling loop verifies `data-resonance === 'active'`. Cosmic energy surges across the screen, the diagnostic card closes, Tony Stark snaps his fingers, and Thanos and his army disintegrate into cosmic particles.
9. **Verification Mechanism**:
   Polling loop in `startPoll()` in `endgame/js/app.js` checking `document.getElementById('cosmicEnergy').getAttribute('data-resonance') === 'active'`.
10. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Attribute update verified, advancing state from `S.DEBUG` to `S.SUCCESS` and `S.DISSOLVE`. Page reset restores `data-resonance="disabled"`.
11. **Unresolved Limitations**:
    None.

---

## Game 5: Shang-Chi

1. **Game Number & Name**: Game 5 — Shang-Chi
2. **Assigned Bug Category**: CSS
3. **Exact Target File, Element & Declaration**:
   - **File**: `sangchi/sangchi.html`
   - **Target Stylesheet**: `<style id="ring-css">`
   - **Selector**: `.ring`
   - **Declaration**: `animation: ringOrbit 2s linear infinite;`
4. **Original Intentional Defect**:
   The `.ring` rule specifies `animation: ringOrbit 2s linear infinite;`, referencing a camelCase identifier `ringOrbit` that does not match the defined `@keyframes ring-orbit` (kebab-case).
5. **Why the Defect Breaks Intended Behavior**:
   Because the animation name does not match the keyframe declaration in the CSS stylesheet, the browser does not animate the rings. The Ten Rings remain motionless, leaving Shang-Chi unable to channel their orbital energy, locking gameplay in `phase = 'debug'`.
6. **Exact Correction Required**:
   In the DevTools Styles panel or Console, change the animation name declaration to `ring-orbit` (or update `#ring-css`).
7. **Exact Console Command**:
   ```javascript
   document.getElementById('ring-css').textContent = document.getElementById('ring-css').textContent.replace('ringOrbit', 'ring-orbit');
   ```
8. **Expected Result After Correction**:
   The computed `animationName` of `.ring` becomes `'ring-orbit'`. The Ten Rings immediately begin orbiting in golden energy trails. The polling detector triggers `succeedFix()`, unlocking the dragon defense sequence.
9. **Verification Mechanism**:
   Runtime polling in `startShangchiPoll()` evaluates `window.getComputedStyle(ringEl).animationName === 'ring-orbit'`.
10. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Computed animation name detected, rings began orbital trajectory, and game advanced to combat. `window.restartShangchi()` re-inserts `BUGGY_CSS` with `ringOrbit`.
11. **Unresolved Limitations**:
    None.

---

## Game 6: Spider-Man

1. **Game Number & Name**: Game 6 — Spider-Man
2. **Assigned Bug Category**: CSS
3. **Exact Target File, Element & Declaration**:
   - **Files**: `spiderman/spiderman/index.html`, `js/DebugInterface.js`, `game.js`
   - **Target Element & Stylesheet**: `<style id="webshooter-css">` & `<div id="web-beam" class="web-beam">`
   - **Selector**: `#web-beam`
   - **Declaration**: `opacity: 0;`
4. **Original Intentional Defect**:
   The web-shooter targeting reticle beam `#web-beam` is styled with `opacity: 0; pointer-events: none;`.
5. **Why the Defect Breaks Intended Behavior**:
   The optical targeting sensor requires the beam's computed opacity to reach at least 0.9. Because `opacity: 0` suppresses visibility, web targeting lock fails and Spider-Man is forced to perch on the rooftop with a diagnostics error.
6. **Exact Correction Required**:
   In the Styles panel or via Console, set `#web-beam`'s `opacity` to `1`.
7. **Exact Console Command**:
   ```javascript
   document.getElementById('web-beam').style.opacity = '1';
   ```
8. **Expected Result After Correction**:
   The computed opacity of `#web-beam` reaches `1`. The diagnostic interface confirms targeting calibration, closes the overlay, and Spider-Man launches a web-line to resume high-speed aerial pursuit of the mechanical falcon.
9. **Verification Mechanism**:
   Polling loop in `DebugInterface.js` monitors `parseFloat(window.getComputedStyle(beam).opacity) >= 0.9`.
10. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Modifying opacity to `1` verified computed style, cleared diagnostic HUD, and resumed pursuit. Replay resets `#web-beam` opacity to `0`.
11. **Unresolved Limitations**:
    None.

---

## Game 7: Doctor Strange / Wanda

1. **Game Number & Name**: Game 7 — Doctor Strange / Wanda
2. **Assigned Bug Category**: CSS
3. **Exact Target File, Element & Declaration**:
   - **File**: `doctor strange wanda visison/doc_strange.html`
   - **Target Stylesheet**: `<style id="bug-style">`
   - **Selector**: `.spell-transition`
   - **Declaration**: `animation: dimensionalTransition 4.2s cubic-bezier(.22, 1, .36, 1) forwards;`
4. **Original Intentional Defect**:
   The `.spell-transition` animation rule specifies `dimensionalTransition` (camelCase) instead of the defined `@keyframes dimensional-transition` (kebab-case).
5. **Why the Defect Breaks Intended Behavior**:
   Because the keyframe rule is not matched, the dimensional warping transition never executes on `#world`. The eldritch spell collapses, causing reality to shatter into an anomaly pause (`State.DEBUG_PAUSE`).
6. **Exact Correction Required**:
   In the Styles panel or Console, correct `dimensionalTransition` to `dimensional-transition` in `#bug-style`.
7. **Exact Console Command**:
   ```javascript
   document.getElementById('bug-style').textContent = document.getElementById('bug-style').textContent.replace('dimensionalTransition', 'dimensional-transition');
   ```
8. **Expected Result After Correction**:
   The browser triggers the genuine `dimensional-transition` CSS animation on `#world`. The animation listener `onAnimStart()` detects the event, reality stabilizes, the Eldritch ground seal manifests, and Wanda's darkhold corruption is cured.
9. **Verification Mechanism**:
   Native `document.addEventListener('animationstart', onAnimStart, true)` and `world.getAnimations()` checking `a.animationName === 'dimensional-transition'`.
10. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Genuine CSS animation event fired upon stylesheet repair, resuming the sequence. Calling `beginRun()` cleanly re-injects `BUGGY_CSS`.
11. **Unresolved Limitations**:
    None.

---

## Game 8: Thor — Thunder

1. **Game Number & Name**: Game 8 — Thor — Thunder
2. **Assigned Bug Category**: CSS
3. **Exact Target File, Element & Declaration**:
   - **Files**: `thor/thor-hammer.html` and `thor/index.html`
   - **Target Element & Stylesheet**: `<style id="bifrost-ward-css">` & `<div id="bifrostWard" class="bifrost-ward">`
   - **Selector**: `.bifrost-ward`
   - **Declaration**: `display: center;` (invalid CSS property value)
4. **Original Intentional Defect**:
   The layout rule `.bifrost-ward` declares `display: center;`, which is an invalid CSS value discarded by the CSS parser.
5. **Why the Defect Breaks Intended Behavior**:
   Because `display: center` is invalid, the Asgardian barrier defense layout fails to render. The Bifrost Ward collapses, leaving Asgardian citizens trapped and Thor's Celestial Thunder locked.
6. **Exact Correction Required**:
   In DevTools Styles panel or Console, set the layout property on `.bifrost-ward` to a valid layout property (e.g. `display: flex;`).
7. **Exact Console Command**:
   ```javascript
   document.getElementById('bifrostWard').style.display = 'flex';
   ```
   *(Or updating `#bifrost-ward-css`: `document.getElementById('bifrost-ward-css').textContent = document.getElementById('bifrost-ward-css').textContent.replace('center', 'flex');`)*
8. **Expected Result After Correction**:
   The computed style of `#bifrostWard` becomes `display: flex`. Asgardian runic sensors detect the valid layout, Thor summons Celestial Thunder, civilians are rescued, and Mjölnir defeats the intruders.
9. **Verification Mechanism**:
   `checkDevToolsFix()` polling and `MutationObserver` checking `window.getComputedStyle(testEl).display === 'flex'`.
10. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Setting `display: flex` was detected via `getComputedStyle`, unlocking Celestial Thunder and finishing the battle. Restart cleanly resets `#bifrost-ward-css` to `display: center`.
11. **Unresolved Limitations**:
    None.
