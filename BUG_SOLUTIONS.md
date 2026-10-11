# SuperHero Games Debugging Challenges — Developer Solutions Reference

> **DEVELOPER-ONLY REFERENCE DOCUMENTATION**  
> Complete technical breakdown and verified browser DevTools solutions for all eight superhero browser debugging challenges.  
> Games 1–4 feature real DOM/HTML defect challenges. Games 5–8 feature real CSS defect challenges.  
> Each game documentation includes the **full file path** and the **full DOM hierarchy path & selectors for every button** involved in the gameplay, debugging, and reset flows.  
> *Note: Deadpool (Game 9) is strictly excluded from modifications and testing per project specification.*

---

## Game 1: Vision

1. **Game Number & Name**: Game 1 — Vision
2. **Assigned Bug Category**: HTML
3. **Exact Target File, Element & Attribute**:
   - **Full File Path**: `c:\Users\sriva\web escape final\vision and bifrost\avengers.html`
   - **Target Element**: `<div id="jarvis-core" class="matrix-module">`
   - **Location**: Inside `#lab-screen` / `#scene-mindstone` cradle module container
   - **Attribute**: `id="jarvis-core"`
4. **Button Full Paths & Interaction Hierarchy**:
   - **Start / Boot Button**:
     - **Full DOM Path**: `html > body > div#app > div#boot > div.bt-card > div.bt-act > button#btnBegin`
     - **CSS Selector**: `button#btnBegin` / `#btnBegin`
     - **Label**: `INITIALIZE SYSTEM`
     - **Function**: Launches laboratory boot sequence and scene intro.
   - **Dialogue Advance Action**:
     - **Full DOM Path**: `html > body > div#app > div#dialog > div.d-box#dBox`
     - **CSS Selector**: `#dBox`
     - **Label**: Clickable dialogue card / `SPACE` / `ENTER`
     - **Function**: Advances spoken dialogue lines between Tony, Bruce, and J.A.R.V.I.S.
   - **Diagnostic Terminal Trigger Button**:
     - **Full DOM Path**: `html > body > div#app > div#failCard > div.fc-card > button#btnDebug`
     - **CSS Selector**: `button#btnDebug` / `#btnDebug`
     - **Label**: `DIAGNOSTIC TERMINAL`
     - **Function**: Opens the `#debug` diagnostic terminal HUD when system crashes.
   - **Auto-Fix Bypass Button**:
     - **Full DOM Path**: `html > body > div#app > div#debug > div.dbg-shell > div.dbg-body > div.dbg-main > div.dbg-foot > button#btnPassDebug`
     - **CSS Selector**: `button#btnPassDebug` / `#btnPassDebug`
     - **Label**: `⚡ AUTO-PATCH (TEST BYPASS)`
     - **Function**: Auto-corrects `#jarvis-core` to `#jarvis-matrix` and verifies fix.
   - **Restart Mission Button**:
     - **Full DOM Path**: `html > body > div#app > div#endCard > div.ec-card > button#btnRestart`
     - **CSS Selector**: `button#btnRestart` / `#btnRestart`
     - **Label**: `RESTART MISSION`
     - **Function**: Resets timeline, restores `id="jarvis-core"` in DOM, re-arms challenge.
5. **Original Intentional Defect**:
   The primary neural network module element is misattributed with `id="jarvis-core"` instead of the required `id="jarvis-matrix"`.
6. **Why the Defect Breaks Intended Behavior**:
   During the synthetic neural transfer sequence, the cradle initialization engine checks the live DOM for `document.getElementById('jarvis-matrix')` to synchronize the Mind Stone energy pathways with J.A.R.V.I.S. memory nodes. Because the node ID is misnamed, the uplink fails, triggering an Asgardian/Stark diagnostic error (`DOM Error: target element 'jarvis-matrix' not found in document`) and pausing the cinematic sequence in debug mode.
7. **Exact Correction Required**:
   In the browser's Developer Tools Elements panel or via Console, edit the element's `id` attribute from `jarvis-core` to `jarvis-matrix`.
8. **Exact Console Command**:
   ```javascript
   document.getElementById('jarvis-core').id = 'jarvis-matrix';
   ```
9. **Expected Result After Correction**:
   The runtime watcher detects the presence of `#jarvis-matrix`. The diagnostic terminal status changes to `✓ DOM NODE #jarvis-matrix IDENTIFIED — ONLINE`, the diagnostic HUD fades out, the cradle repowers with a golden energy surge, and the cinematic advances into `sceneRestored()`, culminating in Vision's awakening.
10. **Verification Mechanism**:
    A lightweight polling loop and `MutationObserver` inside `Debug.open()` monitor the live DOM for `document.getElementById('jarvis-matrix')`.
11. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Renaming the element ID restored the J.A.R.V.I.S. matrix node, closed the diagnostic HUD, and triggered the restored sequence. Mission restart cleanly restores the initial `id="jarvis-core"` defect.
12. **Unresolved Limitations**:
    None.

---

## Game 2: Civil War

1. **Game Number & Name**: Game 2 — Civil War
2. **Assigned Bug Category**: HTML
3. **Exact Target File, Element & Attribute**:
   - **Full File Path**: `c:\Users\sriva\web escape final\civil war\civilwar.html`
   - **Target Element**: `<div id="arc-reactor" data-vitals="offline">`
   - **Location**: Inside `#im` (Iron Man character container)
   - **Attribute**: `data-vitals="offline"`
4. **Button Full Paths & Interaction Hierarchy**:
   - **Start Cinematic Sequence Button**:
     - **Full DOM Path**: `html > body > div#frame > div#start > div.s-box > div > button#start-btn`
     - **CSS Selector**: `button#start-btn` / `#start-btn`
     - **Label**: `▶  BEGIN SEQUENCE`
     - **Function**: Fades out starting screen and begins Siberia sequence.
   - **Interactive Combat Prompt Button**:
     - **Full DOM Path**: `html > body > div#frame > div#viewport > div#prompt`
     - **CSS Selector**: `#prompt`
     - **Label**: Dynamic action prompt (`SPACE` / Click to `RAISE SHIELD`, `THROW THE SHIELD`, `BRACE THE IMPACT`)
     - **Function**: Player interaction for blocking unibeam, counter-throwing shield, and impact clash.
   - **Diagnostic Auto-Fix Bypass Button**:
     - **Full DOM Path**: `html > body > div#frame > div#debug-overlay > div.d-actions > button#bypass-btn`
     - **CSS Selector**: `button#bypass-btn` / `#bypass-btn`
     - **Label**: `⚡ TEST BYPASS (AUTO-FIX)`
     - **Function**: Updates `data-vitals="online"` on `#arc-reactor` and triggers recovery.
   - **Audio Mute/Unmute Button**:
     - **Full DOM Path**: `html > body > div#frame > button#mute`
     - **CSS Selector**: `button#mute` / `#mute`
     - **Label**: Mute / Unmute Speaker Icon
     - **Function**: Toggles synthesized Web Audio sound FX.
   - **Play Again / Restart Button**:
     - **Full DOM Path**: `html > body > div#frame > div#complete > button#restart-btn`
     - **CSS Selector**: `button#restart-btn` / `#restart-btn`
     - **Label**: `PLAY AGAIN`
     - **Function**: Invokes `resetAll()`, resets `#arc-reactor` to `data-vitals="offline"`, returns to scene 1.
5. **Original Intentional Defect**:
   The Arc Reactor telemetry node in Tony Stark's armor has its custom HTML data attribute set to `data-vitals="offline"`.
6. **Why the Defect Breaks Intended Behavior**:
   Following the climax where Captain America strikes Iron Man's chest, Tony Stark collapses with critical armor failure. The game state halts in `DEBUG_PAUSE` awaiting life support recovery. The recovery script requires `#arc-reactor` to exhibit `data-vitals="online"`.
7. **Exact Correction Required**:
   In DevTools Elements panel or Console, update the `data-vitals` attribute of `#arc-reactor` from `"offline"` to `"online"`.
8. **Exact Console Command**:
   ```javascript
   document.getElementById('arc-reactor').setAttribute('data-vitals', 'online');
   ```
9. **Expected Result After Correction**:
   The life support verification system detects `data-vitals="online"`. Iron Man's Arc Reactor pulses with renewed turquoise energy, Tony Stark rises into a revived kneeling pose, Captain America's vibranium shield drops and grounds onto the battlefield floor, and Steve Rogers vanishes into the shadows, transitioning the mission to victory.
10. **Verification Mechanism**:
    A lightweight runtime polling interval (`pollTimer = setInterval(..., 200)`) in `civilwar.html` evaluates `document.getElementById('arc-reactor').getAttribute('data-vitals') === 'online'`.
11. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Modifying the attribute promptly revives Tony Stark, triggers shield grounding physics, and fades Captain America into the background. Calling `window.resetAll()` resets `data-vitals` to `"offline"`.
12. **Unresolved Limitations**:
    None.

---

## Game 3: Ragnarok

1. **Game Number & Name**: Game 3 — Ragnarok
2. **Assigned Bug Category**: HTML
3. **Exact Target File, Element & Attribute**:
   - **Full File Path**: `c:\Users\sriva\web escape final\vision and bifrost\bifrost.html`
   - **Target Element**: `<button id="bifrost-actvate" class="gate-btn">`
   - **Location**: Inside `#bifrost-conduit` / Asgardian gate interface panel
   - **Attribute**: `id="bifrost-actvate"` (typographical defect missing the letter `i`)
4. **Button Full Paths & Interaction Hierarchy**:
   - **Dialogue Continue Button**:
     - **Full DOM Path**: `html > body > div#app > div#dialog > div.d-box > div.d-controls > button#btn-continue`
     - **CSS Selector**: `button#btn-continue` / `#btn-continue`
     - **Label**: `CONTINUE`
     - **Function**: Advances dialogue between Thor and Loki.
   - **Bugged Bifrost Activation Button (The Target Defect Element)**:
     - **Full DOM Path**: `html > body > div#app > div#stage > div#bifrost-conduit > button#bifrost-actvate`
     - **CSS Selector**: `button#bifrost-actvate` (defective ID) &rarr; `button#bifrost-activate` (corrected ID)
     - **Label**: `ACTIVATE BIFROST`
     - **Function**: Primary gate trigger. Correcting its ID to `#bifrost-activate` binds activation handler.
   - **Console Gate Action Trigger Button**:
     - **Full DOM Path**: `html > body > div#app > div#ui-layer > div#console > div.c-actions > button.btn-action[data-action="activate"]`
     - **CSS Selector**: `#console .btn-action[data-action="activate"]`
     - **Label**: `ACTIVATE BIFROST`
     - **Function**: Triggers rainbow beam once `activationUnlocked` is true.
   - **Diagnostic Auto-Fix Bypass Button**:
     - **Full DOM Path**: `html > body > div#app > div#debug > div.dbg-window > div.dbg-controls > button#btn-bypass`
     - **CSS Selector**: `button#btn-bypass` / `#btn-bypass`
     - **Label**: `⚡ TEST BYPASS`
     - **Function**: Auto-fixes `#bifrost-actvate` ID to `#bifrost-activate`.
   - **Diagnostic Terminal Close Button**:
     - **Full DOM Path**: `html > body > div#app > div#debug > div.dbg-window > div.dbg-head > button.btn-close`
     - **CSS Selector**: `#debug .btn-close`
     - **Label**: `&times;`
     - **Function**: Closes diagnostic overlay window.
   - **Restart Mission Button**:
     - **Full DOM Path**: `html > body > div#app > div#complete > button#btn-restart`
     - **CSS Selector**: `button#btn-restart` / `#btn-restart`
     - **Label**: `RESTART MISSION`
     - **Function**: Calls `resetMission()`, resets gate button ID back to `bifrost-actvate`, re-arms challenge.
5. **Original Intentional Defect**:
   The primary gate activation button element ID is misspelled as `bifrost-actvate` instead of `bifrost-activate`.
6. **Why the Defect Breaks Intended Behavior**:
   The realm evacuation protocol queries the DOM for `#bifrost-activate` to bind the interactive rainbow conduit trigger. Because the element ID is defective, the gate controller fails to bind the activation trigger, causing the Bifrost bridge to remain locked in `st-debug` mode.
7. **Exact Correction Required**:
   Using the Elements panel or JavaScript Console, correct the button element's `id` attribute to `bifrost-activate`.
8. **Exact Console Command**:
   ```javascript
   document.getElementById('bifrost-actvate').id = 'bifrost-activate';
   ```
9. **Expected Result After Correction**:
   The live watcher identifies `document.getElementById('bifrost-activate')`. `STATE.challengeSolved` and `STATE.activationUnlocked` become `true`, the diagnostic HUD reports `✓ BIFROST DOM BUG FIXED`, the activation button becomes interactive, and clicking it unleashes the rainbow Bifrost beam to evacuate Asgard.
10. **Verification Mechanism**:
    Lightweight DOM watcher polling in `openDebug()` checking `document.getElementById('bifrost-activate') !== null`.
11. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Live correction unlocks gate controls and allows the rainbow bridge sequence to conclude. `window.resetMission()` cleanly restores `bifrost-actvate`.
12. **Unresolved Limitations**:
    None.

---

## Game 4: Endgame

1. **Game Number & Name**: Game 4 — Endgame
2. **Assigned Bug Category**: HTML
3. **Exact Target File, Element & Attribute**:
   - **Full File Paths**:
     - `c:\Users\sriva\web escape final\endgame\endgame.html`
     - `c:\Users\sriva\web escape final\endgame\index.html`
   - **Target Element**: `<div class="cosmic-energy" id="cosmicEnergy" data-resonance="disabled">`
   - **Location**: Inside `#stage` / `#world` nanotech gauntlet assembly
   - **Attribute**: `data-resonance="disabled"`
4. **Button Full Paths & Interaction Hierarchy**:
   - **Begin Mission Button**:
     - **Full DOM Path**: `html > body > div#ui > div#title > div > div > button#begin`
     - **CSS Selector**: `button#begin` / `#begin`
     - **Label**: `Begin`
     - **Function**: Initiates the Infinity Gauntlet assembly sequence and snap cinematic.
   - **Diagnostic Auto-Fix Bypass Button**:
     - **Full DOM Path**: `html > body > div#ui > section#debug > div.bypassRow > button#bypass`
     - **CSS Selector**: `button#bypass` / `#bypass`
     - **Label**: `⚡ Test Bypass (Auto-Fix)`
     - **Function**: Updates `data-resonance="active"` on `#cosmicEnergy` and verifies fix.
   - **Restart Mission Button**:
     - **Full DOM Path**: `html > body > div#ui > div#end > div > div > button#restart`
     - **CSS Selector**: `button#restart` / `#restart`
     - **Label**: `Restart`
     - **Function**: Resets game state, restoring `data-resonance="disabled"` on `#cosmicEnergy`.
5. **Original Intentional Defect**:
   The cosmic energy conduit node possesses `data-resonance="disabled"`.
6. **Why the Defect Breaks Intended Behavior**:
   The stylesheet rule `.cosmic-energy[data-resonance="active"] { display: block; }` suppresses energy propagation through the Infinity Gauntlet circuits when `data-resonance` is disabled. When Tony Stark snaps his fingers, energy cannot propagate across the gauntlet, halting the cinematic in `S.DEBUG` state.
7. **Exact Correction Required**:
   In the Elements panel or Console, update `data-resonance` on `#cosmicEnergy` from `"disabled"` to `"active"`.
8. **Exact Console Command**:
   ```javascript
   document.getElementById('cosmicEnergy').setAttribute('data-resonance', 'active');
   ```
9. **Expected Result After Correction**:
   The runtime polling loop verifies `data-resonance === 'active'`. Cosmic energy surges across the screen, the diagnostic card closes, Tony Stark snaps his fingers, and Thanos and his army disintegrate into cosmic particles.
10. **Verification Mechanism**:
    Polling loop in `startPoll()` in `endgame/js/app.js` checking `document.getElementById('cosmicEnergy').getAttribute('data-resonance') === 'active'`.
11. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Attribute update verified, advancing state from `S.DEBUG` to `S.SUCCESS` and `S.DISSOLVE`. Page reset restores `data-resonance="disabled"`.
12. **Unresolved Limitations**:
    None.

---

## Game 5: Shang-Chi

1. **Game Number & Name**: Game 5 — Shang-Chi
2. **Assigned Bug Category**: CSS
3. **Exact Target File, Element & Declaration**:
   - **Full File Path**: `c:\Users\sriva\web escape final\sangchi\sangchi.html`
   - **Target Stylesheet**: `<style id="ring-css">`
   - **Selector**: `.ring`
   - **Declaration**: `animation: ringOrbit 2s linear infinite;`
4. **Button Full Paths & Interaction Hierarchy**:
   - **Diagnostic Auto-Fix Bypass Button**:
     - **Full DOM Path**: `html > body > div#hud > div#debug-mode > div.row > button#bypass-btn`
     - **CSS Selector**: `button#bypass-btn` / `#bypass-btn`
     - **Label**: `⚡ TEST BYPASS (AUTO-FIX)`
     - **Function**: Replaces `ringOrbit` with `ring-orbit` in `#ring-css` and unlocks Ten Rings.
   - **Ten Rings Pattern Interaction Buttons (Combat Mode)**:
     - **Full DOM Path**: `html > body > div#hud > div#pattern-mode > div.row > button.gbtn[data-idx="0..4"]`
     - **CSS Selector**: `button.gbtn[data-idx="0"]` through `button.gbtn[data-idx="4"]`
     - **Labels**: `RING 1` &bull; `RING 2` &bull; `RING 3` &bull; `RING 4` &bull; `RING 5`
     - **Function**: Interactive ring strike combat sequence once orbit engine is repaired.
   - **Skip Pattern Combat Button**:
     - **Full DOM Path**: `html > body > div#hud > div#pattern-mode > div.row > button#skip-pattern-btn`
     - **CSS Selector**: `button#skip-pattern-btn` / `#skip-pattern-btn`
     - **Label**: `SKIP PATTERN`
     - **Function**: Advances directly to dragon defense final strike sequence.
   - **Play Again / Restart Button**:
     - **Full DOM Path**: `html > body > div#hud > div.foot > button#restart-btn`
     - **CSS Selector**: `button#restart-btn` / `#restart-btn`
     - **Label**: `PLAY AGAIN`
     - **Function**: Calls `restart()`, re-injects `BUGGY_CSS` (`ringOrbit`) into `#ring-css`, resets rings.
5. **Original Intentional Defect**:
   The `.ring` rule specifies `animation: ringOrbit 2s linear infinite;`, referencing a camelCase identifier `ringOrbit` that does not match the defined `@keyframes ring-orbit` (kebab-case).
6. **Why the Defect Breaks Intended Behavior**:
   Because the animation name does not match the keyframe declaration in the CSS stylesheet, the browser does not animate the rings. The Ten Rings remain motionless, leaving Shang-Chi unable to channel their orbital energy, locking gameplay in `phase = 'debug'`.
7. **Exact Correction Required**:
   In the DevTools Styles panel or Console, change the animation name declaration to `ring-orbit` (or update `#ring-css`).
8. **Exact Console Command**:
   ```javascript
   document.getElementById('ring-css').textContent = document.getElementById('ring-css').textContent.replace('ringOrbit', 'ring-orbit');
   ```
9. **Expected Result After Correction**:
   The computed `animationName` of `.ring` becomes `'ring-orbit'`. The Ten Rings immediately begin orbiting in golden energy trails. The polling detector triggers `succeedFix()`, unlocking the dragon defense sequence.
10. **Verification Mechanism**:
    Runtime polling in `startShangchiPoll()` evaluates `window.getComputedStyle(ringEl).animationName === 'ring-orbit'`.
11. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Computed animation name detected, rings began orbital trajectory, and game advanced to combat. `window.restartShangchi()` re-inserts `BUGGY_CSS` with `ringOrbit`.
12. **Unresolved Limitations**:
    None.

---

## Game 6: Spider-Man

1. **Game Number & Name**: Game 6 — Spider-Man
2. **Assigned Bug Category**: CSS
3. **Exact Target File, Element & Declaration**:
   - **Full File Paths**:
     - `c:\Users\sriva\web escape final\spiderman\spiderman\index.html`
     - `c:\Users\sriva\web escape final\spiderman\spiderman\js\DebugInterface.js`
     - `c:\Users\sriva\web escape final\spiderman\spiderman\game.js`
   - **Target Element & Stylesheet**: `<style id="webshooter-css">` & `<div id="web-beam" class="web-beam">`
   - **Selector**: `#web-beam`
   - **Declaration**: `opacity: 0;`
4. **Button Full Paths & Interaction Hierarchy**:
   - **Commence Chase Start Button**:
     - **Full DOM Path**: `html > body > div#game-container > div#hud-overlay > div.start-screen > button#start-btn`
     - **CSS Selector**: `button#start-btn` / `#start-btn`
     - **Label**: `COMMENCE CHASE`
     - **Function**: Launches aerial pursuit through Manhattan.
   - **Web-Shooter Hardware Pin Trigger Button**:
     - **Full DOM Path**: `html > body > div#debug-interface-overlay > div#web-shooter > button#web-fire-trigger`
     - **CSS Selector**: `button#web-fire-trigger` / `#web-fire-trigger`
     - **Label**: `PALM STUD FIRE TRIGGER`
     - **Function**: Hardware stud trigger pin node in Stark diagnostic schematic.
   - **Web-Shooter Release Pin Trigger Button**:
     - **Full DOM Path**: `html > body > div#debug-interface-overlay > div#web-shooter > button#web-release-trigger`
     - **CSS Selector**: `button#web-release-trigger` / `#web-release-trigger`
     - **Label**: `PALM STUD RELEASE TRIGGER`
     - **Function**: Hardware release stud node in Stark diagnostic schematic.
   - **Diagnostic Auto-Calibrate Bypass Button**:
     - **Full DOM Path**: `html > body > div#debug-interface-overlay > div.repair-box > button#btn-quick-debug-shooter`
     - **CSS Selector**: `button#btn-quick-debug-shooter` / `#btn-quick-debug-shooter`
     - **Label**: `⚡ AUTO-CALIBRATE (TEST BYPASS)`
     - **Function**: Sets `#web-beam` opacity to `1`, solves challenge, and resumes pursuit.
   - **Replay Pursuit / Restart Button**:
     - **Full DOM Path**: `html > body > div#hud-overlay > div.victory-screen > button#restart-btn`
     - **CSS Selector**: `button#restart-btn` / `#restart-btn`
     - **Label**: `REPLAY PURSUIT`
     - **Function**: Calls `restartMission()`, resets `#web-beam` opacity to `0`, re-initiates chase.
5. **Original Intentional Defect**:
   The web-shooter targeting reticle beam `#web-beam` is styled with `opacity: 0; pointer-events: none;`.
6. **Why the Defect Breaks Intended Behavior**:
   The optical targeting sensor requires the beam's computed opacity to reach at least 0.9. Because `opacity: 0` suppresses visibility, web targeting lock fails and Spider-Man is forced to perch on the rooftop with a diagnostics error.
7. **Exact Correction Required**:
   In the Styles panel or via Console, set `#web-beam`'s `opacity` to `1`.
8. **Exact Console Command**:
   ```javascript
   document.getElementById('web-beam').style.opacity = '1';
   ```
9. **Expected Result After Correction**:
   The computed opacity of `#web-beam` reaches `1`. The diagnostic interface confirms targeting calibration, closes the overlay, and Spider-Man launches a web-line to resume high-speed aerial pursuit of the mechanical falcon.
10. **Verification Mechanism**:
    Polling loop in `DebugInterface.js` monitors `parseFloat(window.getComputedStyle(beam).opacity) >= 0.9`.
11. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Modifying opacity to `1` verified computed style, cleared diagnostic HUD, and resumed pursuit. Replay resets `#web-beam` opacity to `0`.
12. **Unresolved Limitations**:
    None.

---

## Game 7: Doctor Strange / Wanda

1. **Game Number & Name**: Game 7 — Doctor Strange / Wanda
2. **Assigned Bug Category**: CSS
3. **Exact Target File, Element & Declaration**:
   - **Full File Path**: `c:\Users\sriva\web escape final\doctor strange wanda visison\doc_strange.html`
   - **Target Stylesheet**: `<style id="spell-transition-css">`
   - **Selector**: `.spell-transition`
   - **Declaration**: `animation: dimensionalTransition 700ms ease-out forwards;`
4. **Button Full Paths & Interaction Hierarchy**:
   - **Begin Ceremony Button**:
     - **Full DOM Path**: `html > body > div#app > div#boot > div.b-card > button#begin-btn`
     - **CSS Selector**: `button#begin-btn` / `#begin-btn`
     - **Label**: `BEGIN`
     - **Function**: Launches ceremony intro and Strange spell casting preparation.
   - **Diagnostic Test Bypass Button**:
     - **Full DOM Path**: `html > body > div#app > div#debug-panel > div.d-actions > button#bypass-btn`
     - **CSS Selector**: `button#bypass-btn` / `#bypass-btn`
     - **Label**: `⚡ TEST BYPASS (AUTO-FIX)`
     - **Function**: Replaces `dimensionalTransition` with `dimensional-transition` in `#spell-transition-css`.
   - **Audio Toggle Button**:
     - **Full DOM Path**: `html > body > div#app > button#sound-btn`
     - **CSS Selector**: `button#sound-btn` / `#sound-btn`
     - **Label**: Ambient Sound / Mute Toggle Icon
     - **Function**: Toggles synthesized Web Audio drone and chimes.
   - **Play Again / Restart Ceremony Button**:
     - **Full DOM Path**: `html > body > div#app > div#complete-card > button#play-again`
     - **CSS Selector**: `button#play-again` / `#play-again`
     - **Label**: `PLAY AGAIN`
     - **Function**: Calls `beginRun()`, restores `BUGGY_CSS` into `#spell-transition-css`, resets timeline.
5. **Original Intentional Defect**:
   The `.spell-transition` animation rule specifies `dimensionalTransition` (camelCase) instead of the defined `@keyframes dimensional-transition` (kebab-case).
6. **Why the Defect Breaks Intended Behavior**:
   Because the keyframe rule is not matched, the dimensional warping transition never executes on `#world`. The eldritch spell collapses, causing reality to shatter into an anomaly pause (`State.DEBUG_PAUSE`).
7. **Exact Correction Required**:
   In the Styles panel or Console, correct `dimensionalTransition` to `dimensional-transition` in `#spell-transition-css`.
8. **Exact Console Command**:
   ```javascript
   document.getElementById('spell-transition-css').textContent = document.getElementById('spell-transition-css').textContent.replace('dimensionalTransition', 'dimensional-transition');
   ```
9. **Expected Result After Correction**:
   The browser triggers the genuine `dimensional-transition` CSS animation on `#world`. The animation listener `onAnimStart()` detects the event, reality stabilizes, the Eldritch ground seal manifests, and Wanda's darkhold corruption is cured.
10. **Verification Mechanism**:
    Native `document.addEventListener('animationstart', onAnimStart, true)` and `world.getAnimations()` checking `a.animationName === 'dimensional-transition'`.
11. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Genuine CSS animation event fired upon stylesheet repair, resuming the sequence. Calling `beginRun()` cleanly re-injects `BUGGY_CSS`.
12. **Unresolved Limitations**:
    None.

---

## Game 8: Thor — Thunder

1. **Game Number & Name**: Game 8 — Thor — Thunder
2. **Assigned Bug Category**: CSS
3. **Exact Target File, Element & Declaration**:
   - **Full File Paths**:
     - `c:\Users\sriva\web escape final\thor\thor-hammer.html`
     - `c:\Users\sriva\web escape final\thor\index.html`
   - **Target Element & Stylesheet**: `<style id="bifrost-ward-css">` & `<div id="bifrostWard" class="bifrost-ward">`
   - **Selector**: `.bifrost-ward`
   - **Declaration**: `display: center;` (invalid CSS property value)
4. **Button Full Paths & Interaction Hierarchy**:
   - **Continue / Start Mission Button**:
     - **Full DOM Path**: `html > body > div#app > div.canvas-wrapper > div.game-hud > div.hud-bottom-actions > button#continueBtn`
     - **CSS Selector**: `button#continueBtn` / `#continueBtn`
     - **Label**: `CONTINUE`
     - **Function**: Dismisses starting mission briefing panel and arms Mjölnir action controls.
   - **Primary Action / Summon Thunder Button**:
     - **Full DOM Path**: `html > body > div#app > div.canvas-wrapper > div.game-hud > div.hud-bottom-actions > button#primaryActionBtn`
     - **CSS Selector**: `button#primaryActionBtn` / `#primaryActionBtn`
     - **Label**: `⚡ SUMMON THUNDER` &rarr; `🔨 THROW MJÖLNIR`
     - **Function**: Triggers thunder power restoration / opens diagnostic HUD if locked, throws Mjölnir when unlocked.
   - **Bifrost Inspector Close Button**:
     - **Full DOM Path**: `html > body > div#app > div.canvas-wrapper > div#debugTerminalOverlay > div.debug-terminal-window > div.terminal-header > button#terminalCloseBtn`
     - **CSS Selector**: `button#terminalCloseBtn` / `#terminalCloseBtn`
     - **Label**: `&times;`
     - **Function**: Closes/minimizes Bifrost diagnostic HUD.
   - **Diagnostic Auto-Patch Button**:
     - **Full DOM Path**: `html > body > div#app > div.canvas-wrapper > div#debugTerminalOverlay > div.debug-terminal-window > div.terminal-body > div.terminal-footer > button#terminalSolveBtn`
     - **CSS Selector**: `button#terminalSolveBtn` / `#terminalSolveBtn`
     - **Label**: `⚡ AUTO-PATCH`
     - **Function**: Sets `display: flex` on `#bifrostWard` / `#bifrost-ward-css` and unlocks Celestial Thunder.
   - **Restart Mission Button**:
     - **Full DOM Path**: `html > body > div#app > div.canvas-wrapper > div#victoryOverlay > div.victory-window > div.overlay-btn-group > button#victoryRestartBtn`
     - **CSS Selector**: `button#victoryRestartBtn` / `#victoryRestartBtn`
     - **Label**: `RESTART MISSION`
     - **Function**: Calls `restartThor()`, resets `#bifrost-ward-css` to `display: center;`, resets game state to `START`.
5. **Original Intentional Defect**:
   The layout rule `.bifrost-ward` declares `display: center;`, which is an invalid CSS value discarded by the CSS parser.
6. **Why the Defect Breaks Intended Behavior**:
   Because `display: center` is invalid, the Asgardian barrier defense layout fails to render. The Bifrost Ward collapses, leaving Asgardian citizens trapped and Thor's Celestial Thunder locked.
7. **Exact Correction Required**:
   In DevTools Styles panel or Console, set the layout property on `.bifrost-ward` to a valid layout property (e.g. `display: flex;`).
8. **Exact Console Command**:
   ```javascript
   document.getElementById('bifrostWard').style.display = 'flex';
   ```
   *(Or updating `#bifrost-ward-css`: `document.getElementById('bifrost-ward-css').textContent = document.getElementById('bifrost-ward-css').textContent.replace('center', 'flex');`)*
9. **Expected Result After Correction**:
   The computed style of `#bifrostWard` becomes `display: flex`. Asgardian runic sensors detect the valid layout, Thor summons Celestial Thunder, civilians are rescued, and Mjölnir defeats the intruders.
10. **Verification Mechanism**:
    `checkDevToolsFix()` polling and `MutationObserver` checking `window.getComputedStyle(testEl).display === 'flex'`.
11. **Actual Browser-Testing Result**:
    **PASSED**. Verified in headless Chrome. Setting `display: flex` was detected via `getComputedStyle`, unlocking Celestial Thunder and finishing the battle. Restart cleanly resets `#bifrost-ward-css` to `display: center`.
12. **Unresolved Limitations**:
    None.
