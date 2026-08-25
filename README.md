# Bolivian Torch Field Guide

Care guide for *Trichocereus bridgesii* (`Echinopsis lageniformis`), written for Salt Lake Valley conditions. Single static page, no build step, no dependencies.

## Where the info comes from

Nearly all of it is adapted from [this consolidated write-up](https://www.reddit.com/r/sanpedrocactusseeds/s/4ZlaQmuzDO) by u/TossinDogs on r/sanpedrocactusseeds, covering seed sowing, seedling care and adult care.

Four things aren't from that post. They're tagged "Adapted, not sourced" on the page itself:

1. the Salt Lake seasonal calendar and the "Right now" card, both derived by applying the post's 60°F / 35°F watering rule to the valley's monthly normals
2. bringing the pot indoors for winter (zone 7a hits 0-5°F, the species is good to roughly 20°F)
3. the note on hard local tap water
4. the altitude note on afternoon shade

## How it works

`index.html` is the whole site. CSS, SVG illustrations and the one script are all inline.

The only dynamic part is the "Right now" card and the current-month marker on the year chart. Both read `new Date()` in the visitor's browser and pick a seasonal phase out of a lookup table, so there's no server, no API and nothing stored. It re-renders if the page is left open past midnight.

The one external dependency is Google Fonts (Syne, Newsreader, JetBrains Mono). If that's ever blocked the fallback stacks take over and the page still reads fine.

Light and dark both come from `prefers-color-scheme`, so it follows the visitor's OS. The `[data-theme]` hooks are still in the CSS if a manual toggle is ever wanted.

## Local preview

```
python3 -m http.server 8000
```

then open `http://localhost:8000`. Opening `index.html` directly over `file://` works too.

## Pages setup

Settings > Pages > Source: `Deploy from a branch`, branch `main`, folder `/ (root)`.

`.nojekyll` is there so Pages serves the files as-is instead of running them through Jekyll.
