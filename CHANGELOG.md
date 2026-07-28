# Changelog

All notable changes to this project are documented here.

## [Unreleased]
- Added a persistent best-score record (`localStorage`): shown as "BEST" next to the current score, updates live whenever the current run beats it. The current run always starts from zero — only the displayed record persists across sessions/reloads.
- Enlarged the cat, items, and vacuum sprites for better visibility on real phone screens, where the whole game frame is scaled down to fit a short viewport.
- Fixed touch controls not scaling down with the game on small phone screens: they used to be fixed-pixel-sized and viewport-anchored, so they stayed full size while the game shrank to fit, visually dominating the screen. They now live inside `.tv-frame` and scale proportionally with it.
- Fixed pillarboxing and control overlap on real phone screens: the canvas now resizes to the device's actual aspect ratio instead of a fixed 900:600 ratio (no more empty side margins), and the on-screen D-pad/action button are placed in the verified-empty area below the shelf instead of guessed-at corners.
- Fixed on-screen D-pad buttons rendering too small (~24px) on typical phone-in-landscape screens: replaced the 3-row D-pad with a more compact 2-row layout (Up on top, Left/Down/Right in one row) and increased the base button size, so real on-screen size lands close to the ~44px touch-target guideline instead of well under it.

## [3.0] - 2026-07-28
- Added responsive scaling: the game frame now fits any screen size (capped at native resolution on large screens) via a CSS transform, laying the groundwork for mobile support.
- Added a "rotate your phone" prompt shown instead of the game on small portrait-oriented screens.
- Added on-screen touch controls (D-pad + action button) shown only on touch-primary devices, feeding the same input state the keyboard already uses — the game is now playable on both computer and phone.

## [2.0] - 2026-07-28
- Added jump mechanic: gravity, vertical arc via Up arrow/W, lands back on the same shelf, double-jump prevented.
- Added a second, upper shelf: items now spawn on either shelf, and pushing only affects items on the cat's current level.
- Jump now switches shelf levels: a tall jump climbs from the lower shelf to the upper one, Down/S drops back down; landing on an item mid-air knocks it off, same as a Space push.
- Walking into a dangerous item without jumping over it now costs points automatically, just like pushing it — safe items are unaffected, and jumping over a dangerous item avoids the penalty entirely.
- Added a patrolling robot vacuum: bumping into it from the side costs points, but landing on top while jumping lets the cat ride it for a recurring bonus, and jumping again hops off.
- Enlarged the cat sprite from 40×40 to 60×60 and gave it life: periodic blinking, idle tail sway, and squash/stretch while jumping and landing.
- Fixed a bug where the cat would stay stuck floating in mid-air after leaving the vacuum — gravity now correctly resumes.
- Added floating `+N`/`−N` popups whenever the score changes (push, dangerous-item collision, vacuum hit, ride bonus) for clear feedback on what just happened.
- The vacuum ride bonus is now a one-time reward on landing (+15), not a recurring tick every half-second — riding forever was otherwise the optimal strategy.
- Accidental collisions (a dangerous item without jumping, a side-hit from the vacuum) now cause a brief control freeze (~250ms) and a visible expanding ring at the point of impact — deliberate actions (pushing, stomping) stay instant.

## [1.0] - 2026-07-28
First fully playable version of Cat Push — all mandatory requirements of the
course assignment are met.

- Added the game screen: 900×600 canvas in a retro TV frame, with scan-lines and pixelated rendering.
- Added the cat sprite and controls: moves along the shelf with arrow keys/WASD, clamped at both edges.
- Added item spawning on the shelf: 3 safe types (mug, flower, food) and 2 dangerous ones (vase, TV), a new item every 3 seconds at a random position.
- Added pushing items with the Space key: collision with the cat, item falls off screen, removed after falling.
- Added the scoring system: points for safe items, penalty for dangerous ones, score never goes below zero, shown in the top-left corner.
- Added level progression: level increases every 100 points, spawn interval and the share of dangerous items increase with level (capped at 60% dangerous).
- Detailed pixel art: cat (ears/eyes/nose/striped tail), mug with handle and steam, potted flower, cookie with chips, patterned vase, TV with antenna; shelf texture and wallpaper background; a shared 16-color palette.
- Polished the CRT screen effect: glow (radial gradient behind the play area), subtle contrast/brightness, refined scan-line density.
- Switched the game loop to delta-time (frame-rate independence, protection against jumps after the tab is backgrounded) and added a cap on the number of items on the shelf.
- Prepared for deployment: confirmed no external dependencies, verified the game in an isolated copy (simulating a clean clone), added README.md with instructions.
