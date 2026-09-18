# Memory Garden

A card-matching memory game that runs entirely in the browser. Two people can play on the same screen, or one person can play against a bot. Cards can show animals, plants, or a mix of the two. The interface is available in English and Turkish, where the game is called *Hafıza Bahçesi*.

**Play:** https://srknozdemir.github.io/memory-garden/

## Features

- **Three card themes** — animals, plants, or both shuffled together; 52 illustrations in all
- **Two modes** — two players taking turns, or a single player against a bot
- **Two bot personalities** — one that forgets every card it sees, and one that remembers every card either side has turned over
- **Time trial** — each player gets their own clock, and it only runs on their turn
- **Five board sizes** — 8, 16, 24, 32 or 48 cards
- **Day and night appearance**
- **Turkish and English**, switched from the top of the menu and remembered between visits
- **Keyboard and screen-reader friendly** — Tab between cards, Enter to flip, with spoken labels for every card

Matching a pair lets you go again; missing passes the turn to your opponent. In a time trial, running out of time loses the game outright.

## No dependencies, no build step

The whole game is one file: `index.html`. All 26 animals and 26 plants are drawn as inline SVG and the sound effects are synthesised with the Web Audio API, so there is no image folder, no audio folder, no package manager and nothing to compile. Fonts are pulled from Google Fonts; without a connection the game still plays and simply falls back to a system typeface.

## Running it

Download `index.html` and double-click it. Any modern browser will open it directly — a local server is not needed.

## Publishing on GitHub Pages

1. Create a repository and put `index.html` in its root.
2. Go to **Settings → Pages**, set Source to **Deploy from a branch**, and choose the `main` branch with the `/ (root)` folder.
3. The game goes live at `https://<username>.github.io/<repository>/` within a minute or two.

## Customising

- **Cards** — add an entry to the `ANIMALS` or `PLANTS` array in the form `{ n:"Name", bg:"#colour", s:\`...SVG...\` }`. Every entry widens the pool that round draws from. English names live in the `AN_EN` lookup, and `DECKS` maps the three themes onto those arrays.
- **Timings** — the `time` values in the `SIZES` array are the per-player clocks, in seconds.
- **Colours** — the `:root` and `html[data-theme="night"]` blocks at the top of the file hold the day and night palettes.
- **Languages** — `I18N` holds one block per language. A third language needs a block with the same keys and one more button in the menu.

## Background

This started as a desktop game written in Python with pygame, which needed an assets folder and a local install to run. The web version keeps the same rules and options while fitting into a single file that anyone can open from a link.

## Licence

MIT.
