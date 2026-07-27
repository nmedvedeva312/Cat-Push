# Changelog

All notable changes to this project are documented here.

## [Unreleased]

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
