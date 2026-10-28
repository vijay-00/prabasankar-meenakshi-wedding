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
