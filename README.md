# Cat Push — Retro 8-bit Browser Game

A cat sits on a shelf next to some household items and, right in front of the
player, makes mischief: it moves along the shelf and pushes items off,
earning points for safe ones and a penalty for dangerous ones.

## How to Play

- **Move**: Arrow keys or WASD
- **Push an item**: Space, while the cat is next to it
- **Goal**: push safe items (mug, flower, food) for points, avoid dangerous
  ones (vase, TV) — items spawn faster and the share of dangerous ones grows
  with every level

## Game Rules

**Items and points**

| Item | Type | Points |
|---|---|---|
| Mug | Safe | +10 |
| Flower | Safe | +15 |
| Food | Safe | +20 |
| Vase | Dangerous | −25 |
| TV | Dangerous | −30 |

- A new item spawns at a random spot on the shelf every few seconds.
- Push a **safe** item off the shelf to score points; push a **dangerous**
  one and you take a penalty instead.
- Your score never drops below 0, no matter how many dangerous items you push.

**Difficulty progression**

- The level goes up every 100 points.
- Higher levels mean items spawn more often (shorter interval between spawns).
- Higher levels also mean a bigger share of dangerous items — it starts at
  20% at level 1 and rises by 10 percentage points per level, capped at 60%.
- There's no explicit ending — the game keeps getting harder the longer you
  survive and score.

## Play Online

[Live Demo](https://username.github.io/cat-push) — replace with the real
link after deployment (see below).

## Run Locally

1. Clone or download this repository
2. Open `index.html` in a modern browser (Chrome, Firefox, Edge) — just
   double-click it, no internet connection needed
3. No build step or dependencies required

## Technical Details

- Pure vanilla JavaScript, HTML5 Canvas
- No external libraries, images, fonts, or CDNs
- Works fully offline, single file
- Retro 8-bit aesthetic, pixel sprites drawn directly in code
