# Grow a living farm

A touch-friendly educational game that shows coffee and cattle farmers the benefits of agroforestry. Built for iPad (Safari, landscape) at farmer fairs and cooperative events.

Players plant shade, fruit, fodder and native forest trees, then grow their farm through 8 years of weather and market events, side by side with a neighbour who plants no trees. The end screen can then fast-forward both farms to year 30.

## Two versions

- `index.html` is the playable game. Visitors choose a farm, plant trees and grow the farm themselves.
- `demo.html` plays the game by itself in a loop, with a red frame and a caption on every action. Tap the screen to pause and tap again to continue. On Netlify it is at `/demo.html`.

Both open in any modern browser. No build step or server is needed.

Both files are the same code. The only difference is one line near the top of the script: `const VERSION = 'play';` or `const VERSION = 'demo';`. After changing the game, copy `index.html` to `demo.html` and change that line.

## Publish with Netlify

**Quickest: drag and drop**
1. Go to app.netlify.com/drop.
2. Drag the `grow-a-living-farm` folder onto the page.
3. Netlify gives you a live link. Rename the site under Site configuration if you want a nicer address.

**From GitHub (updates automatically)**
1. Push this folder to a GitHub repository.
2. In Netlify, add a new site and import the project from GitHub.
3. Leave the build command empty and set the publish directory to `/` (the repository root).
4. Every push to `main` redeploys the game.

On the iPad, open the link in Safari and choose **Share → Add to Home Screen** so it runs full screen like an app.

## Kiosk behaviour

- Play version: returns to the start screen after 2.5 minutes without a touch (`IDLE_MS`).
- Demo version: loops coffee and pasture rounds, including the 30-year view; `DEMO_PACE` sets the speed (1 = normal, 1.5 = 50% slower).
- Pinch and double-tap zoom are blocked.
- Works offline once loaded; fonts fall back to system fonts if there is no connection.

## Editing the game

All numbers and texts sit at the top of the `<script>` block in `index.html`:

- `FARMS` — farm size (`ha`), tree types, trees per plot (`per`), costs, income, shade, carbon and the tips shown when a tree is selected.
- `EVENTS` — yearly events, how hard they hit, and the fact shown after each year.
- `START_CASH`, `YEARS` — starting money and game length.
- `PROJECT_YEARS` — how far the end screen fast-forwards (30).
- `CARBON_PRICE`, `CARBON_SHARE`, `CARBON_PAY_FROM` — carbon credit price ($35/t), the farmer's share (80%) and the first payment year (3).

## What the game measures

Money tab: profit, money in the bank, coffee (or milk and cattle) income, fruit and tree income, carbon credits, fertiliser cost, pesticide (or tick and fly treatment) cost.

Farm health tab: coffee quality (or herd condition), soil health, soil moisture, biodiversity (with birds, bees and soil life levels), resilience, carbon stored.

30-year view: after the 8 years, "Fast-forward to year 30" keeps the player's trees, repeats the weather they just played, and draws money earned since planting for both farms. It also shows extra profit, carbon stored, soil health and biodiversity at year 30. Trees are never cut.

The model is illustrative, not a forecast. Review the figures and fact texts with your agronomy team before using it with farmers.

---

Made by GrowGrounds — [growgrounds.org](https://growgrounds.org)
