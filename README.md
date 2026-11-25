# Cellular Automata Workbench

An interactive 3-D explorer for cellular automata, built for learning and experimenting. Every cell follows the same short rule, looking only at its neighbours, yet crystals, clouds, gliders and fractals appear. Pick a case, press play, then change one number and see what happens.

**Open it:** [hossbh.github.io/Cellular-Automata-Workbench](https://hossbh.github.io/Cellular-Automata-Workbench/)

It is a single HTML file with no build step. Open `index.html` in any modern browser with an internet connection (three.js and the fonts load from CDNs).

## Three kinds of automaton

| Mode | What you see |
|---|---|
| **3-D volume** | Life-like birth/survival rules on an N × N × N grid, with optional decay states (“Generations” rules) and Moore (26) or von Neumann (6) neighbourhoods. |
| **2-D + time** | Conway's Life and its relatives. Each generation is stacked on the last, so a still life becomes a column, an oscillator a braid and a glider a slanted tube. |
| **1-D + time** | Wolfram's 256 elementary rules as space-time walls, on a flat sheet or wrapped onto a cylinder to show the joined edges. |

## What you can do

- **Case library:** 29 ready-made cases, from the Gosper glider gun and Rule 30 to 3-D crystal growth, each with a short explanation.
- **Edit the rule:** type a rule string (`B3/S23`, `B4/S4/C5/M`, or the S/B/C/N form `4/4/5/M`), click the birth and survival counts, or flip the eight output tiles of a 1-D rule.
- **Inspect a cell:** click any cube to see its state, its live-neighbour count and what the rule will do with it.
- **Draw a seed:** paint on a layer of the volume, on the newest 2-D generation, or on the 1-D starting row. The 1-D history recomputes instantly as you draw.
- **Watch the numbers:** live population, births and deaths, and a quick guess at the behaviour (extinct, fixed, periodic, growing or aperiodic).
- **Learn:** plain-language notes on rules, neighbourhoods and Wolfram's four classes, plus guided experiments that each load with one click.
- **Share:** *Copy link* stores the rule and settings in the URL; *Save image* downloads the 3-D view as a PNG.

Keyboard: <kbd>Space</kbd> play or pause · <kbd>→</kbd> one step · <kbd>R</kbd> restart · <kbd>F</kbd> fit the view.

## How it works

- The simulation runs in plain JavaScript on typed arrays. Neighbour counts are scattered from live cells only, so sparse patterns are cheap; a 48³ volume (110 592 cells) typically steps in 5–15 ms.
- The 3-D view draws every live cell as one instance of a single cube mesh (three.js `InstancedMesh`), skipping cubes hidden inside solid regions.
- Random starts use a seeded generator, so the same seed always gives the same run.
- Light and dark themes follow the system setting or the toggle in the top bar.

## Further reading

- J. von Neumann, *Theory of Self-Reproducing Automata*, ed. A. W. Burks. University of Illinois Press, 1966.
- M. Gardner, “Mathematical Games: The fantastic combinations of John Conway's new solitaire game ‘life’”, *Scientific American* 223(4), 120–123, 1970.
- S. Wolfram, “Statistical mechanics of cellular automata”, *Reviews of Modern Physics* 55, 601–644, 1983.
- C. Bays, “Candidates for the Game of Life in three dimensions”, *Complex Systems* 1, 373–400, 1987.
- S. Wolfram, *A New Kind of Science*. Wolfram Media, 2002.
- M. Cook, “Universality in elementary cellular automata”, *Complex Systems* 15, 1–40, 2004.

## Credits

3-D rendering by [three.js](https://threejs.org/) (MIT licence). Fonts: Archivo and STIX Two Text from Google Fonts.

© 2026 Hossein Basereh. All rights reserved.
