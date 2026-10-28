# V. Prabasankar ♥ S. Meenakshi — Wedding E‑Invitation

Sunday, **22 November 2026** · 8.30 a.m. – 10.00 a.m.
Sri Shanmuga Vilas Prasanna Sabha Mandapam, Sri Vaidyanathar Swamy Udanurai
Sri Thaiyal Nayaki Amman Temple, Vaitheeswaran Koil, Mayiladuthurai Dt.

---

## What's here

```
index.html                      the whole site (HTML + CSS + JS in one file)
assets/
  music-placeholder.wav         temporary background music — replace, see below
  README.txt                    how to swap the music
netlify.toml                    deploy config
```

No build step, no npm install. It is plain static HTML.

## Run it locally

Open `index.html` in a browser, or serve the folder:

```bash
npx --yes serve D:\Prabasankar-Meenakshi-Wedding
```

## Replace the background music

The player looks for `assets/music.mp3` first and falls back to the
placeholder if that file is missing.

So: **drop your song in as `assets/music.mp3`.** Nothing else to change.

See `assets/README.txt` for details.

## Deploy

**Netlify (drag & drop):** go to <https://app.netlify.com/drop> and drag this
folder onto the page. Done — you get a URL like
`https://prabasankar-meenakshi.netlify.app`.

**Netlify (CLI):**

```bash
npx --yes netlify-cli deploy --dir=. --prod
```

Any static host works the same way (Vercel, GitHub Pages, Cloudflare Pages).

## Changing details

Everything you'd want to edit is near the top of the `<script>` block in
`index.html`, in the `CFG` object:

| Key | What it controls |
|---|---|
| `start` / `end` | muhurtham time — drives the countdown and the calendar file |
| `mapsQuery` | what "Get Directions" searches for on Google Maps |
| `addr.en` / `addr.ta` | the address that "Copy Address" copies |
| `shareText.en` / `shareText.ta` | the WhatsApp / share message |
| `music` | path to your song (`assets/music.mp3`) |

**Default language** is Tamil. To open in English instead, change
`<body class="lang-ta locked">` to `<body class="lang-en locked">` and, in the
script, `setLang(savedLang === 'en' ? 'en' : 'ta')` to
`setLang(savedLang === 'ta' ? 'ta' : 'en')`.

## Features

- Opening gate screen → scroll-through cards
- EN / தமிழ் toggle (remembered per visitor)
- Thirukkural 45 with a "reveal the meaning" modal
- Live countdown to the muhurtham
- Google Maps directions + copy address
- Add to Calendar (`.ics`, works on phone and desktop)
- WhatsApp share + native share + copy link
- Background music toggle
- Falling petals, scroll reveals, progress bar
- Respects `prefers-reduced-motion`

## Colour theme

Taken from the printed card (Murugan + gopuram artwork):

| Role | Colour |
|---|---|
| Paper | `#FAF4E4` → `#F4E9CE` |
| Maroon ink | `#7A1225` / `#53101C` |
| Temple gold | `#C19A3B` / `#E6CE8C` |
| Peacock green | `#1C6A6E` |

---

## Publishing

Live at **https://vijay-00.github.io/prabasankar-meenakshi-wedding/**

GitHub Pages serves the **`gh-pages`** branch, not `main`. That branch holds
only what the site actually serves — `index.html`, the WebP artwork, the music
and a `.nojekyll` marker. The source originals in `assets/img/_src/`, the music
previews and the docs stay on `main` and are never published.

**Pushing to `main` does not update the live site.** `gh-pages` is built
deliberately, so rebuild it after a change:

```bash
# from the project root, on main, with a clean working tree
export GIT_INDEX_FILE=/tmp/ghpages.index && rm -f "$GIT_INDEX_FILE"
touch .nojekyll
git add --force .nojekyll index.html assets/music.mp3 assets/music-placeholder.wav
git add --force assets/img/*.webp assets/img/*.svg
TREE=$(git write-tree)
COMMIT=$(git commit-tree "$TREE" -m "Publish")
unset GIT_INDEX_FILE && rm -f .nojekyll
git branch -f gh-pages "$COMMIT" && git push -f origin gh-pages
```

It uses a temporary git index so the working tree is never touched — no branch
switching, nothing to stash.
