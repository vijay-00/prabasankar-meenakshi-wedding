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

## One thing to know before hosting

The images total **7.8 MB**. That's fine on wifi but slow on patchy mobile data,
which is how most guests will open it. Nothing is broken — it just takes a few
seconds on a weak connection. When you're ready to host, say so and I'll
compress them (convert to WebP and size each one to how big it actually renders).
That typically cuts it to well under 1 MB with no visible difference. Not worth
doing until the artwork is final.

The four heaviest: `mandap.png` 1.4 MB, `feather.png` 1.3 MB,
`mandala.png` 1.2 MB, `garland.png` 1.0 MB.

Original uncompressed files are kept in `assets/img/_src/` (5.4 MB). **Delete
that folder before you deploy** — it isn't needed by the site.
