# Image status

All five of your latest images are installed. Every decorative element on the
site is now your own artwork, with one exception noted below.

---

## ✅ INSTALLED — your artwork

| File | What | Where it appears |
|---|---|---|
| `murugan.png` | Baby Murugan with vel & peacock | Opening screen (large, haloed) + first card |
| `garland.png` | Jasmine / marigold / mango-leaf garland with bells | Strip across the top of the opening screen |
| `mandala.png` | Gold mandala | Slow-rotating watermark behind **all 9 cards** |
| `medallion.png` | Gold diamond ornament with pearls | Above each section heading |
| `mandap.png` | Ornate wedding mandap | Venue card — main picture |
| `feather.png` | Peacock feather | Floating accents on 4 cards |
| `lotus.png` | Pink & gold lotus | Top of the final card |
| `div-lotus.png` | Lotus divider rule | Main dividers |
| `div-beaded.png` | Beaded divider rule | Small dividers |
| `div-scroll.png` | Scrollwork divider | Between bride & groom, and between the two families |
| `couple.webp` | Illustrated bride & groom | Couple card — under the heading, above the groom |
| `vel.png` | Murugan's vel with garland and silk | Above **ஸ்ரீ முருகன் துணை** on the formal invitation card |
| `orn-sprig.png` | Slim floral sprig | Mirrored pair flanking the big "22" (tablet & desktop only — hidden under 430px so it doesn't crowd a phone) |

### What I did to this batch

- All five arrived as **WebP with real transparency** (44–76% clear, with soft
  anti-aliased edges). No background removal needed — a first.
- Each was auto-cropped to its content and resized.
- **The line-ornament image was a sprite** — five separate ornaments in one
  2000×667 file. I split it automatically by scanning for empty rows and
  columns, which found exactly five boxes: three horizontal rules and two
  vertical ornaments. Each was saved as its own file (listed above).
- The **lotus is full colour**, so I removed it from the gold-masking pipeline —
  it would have been flattened to a gold silhouette and you'd have lost the pink.
  The whole masking system is now gone, since nothing needs it any more.

---

## 🔶 ONE PLACEHOLDER LEFT

| File | What | Where |
|---|---|---|
| `orn-corner.svg` | Corner flourish | The 4 corners of every card |

This is one I drew. It's subtle and it works, but it isn't yours. If you want to
replace it, it needs to be an **L-shaped corner piece** (it gets mirrored into
all four corners) — not a full frame and not a vertical sprig. Roughly 130×150,
transparent.

---

## ⏳ STILL NEEDED

### Nothing — music arrived 28 Oct 2026

`assets/music.mp3` is installed (2m 28s) and starts the moment the temple
doors part, then loops. `assets/music-placeholder.wav` stays as the fallback
if the mp3 ever fails to load.

**Undecided:** whether to add a ceremonial flourish at the door-opening moment.
Three synthesised options are in `assets/_preview/` — open
`preview-music.html` to hear them. **Delete `assets/_preview/` and
`preview-music.html` before deploying** if none is chosen.

### Optional — say the word

- **Ganesha emblem** — your printed card has Ganesha on the English side

---

## Image weight — done 28 Oct 2026

Served artwork is **1.08 MB** across 14 files, down from 8.39 MB. Every piece
is a WebP sized to twice the width it actually renders at, which is what a 2x
screen needs and no more. The worst offender was `vel.png`: 1.2 MB to fill 46
display pixels, now 32 KB.

Originals are kept in `assets/img/_src/` and in this repo's history. Nothing
links to that folder, so it costs no bandwidth even if it is deployed.
