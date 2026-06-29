# 🎵 Vinyl Poster Editor

A standalone, single-file web app for designing a vinyl-record lyric art poster. No server, no install, no dependencies — just open `index.html` in any modern browser.

![Vinyl Poster Editor](https://via.placeholder.com/800x400?text=Vinyl+Poster+Editor+Preview)

## What It Does

Renders song lyrics as a continuous spiral of text that winds inward toward the centre of a vinyl record graphic. Every visual element is adjustable with live-preview sliders — what you see updates instantly as you drag.

When you're happy with the result, export a print-ready **PNG at 300 DPI** (3300 × 4200 px, perfect for an 11″ × 14″ print) or a scalable **SVG vector file**.

## Features

- **Spiral text** — lyrics follow an Archimedean spiral path from the outer edge inward
- **Live preview** — every control updates the poster in real time
- **Lyric modes** — print lyrics once only, or repeat them to fill the entire spiral
- **Lyric counter** — colour-coded indicator shows whether your lyrics fit, are cut off, or have space left over
- **Full typography control** — font size, letter spacing, and line spacing sliders
- **Spiral geometry** — outer radius, inner radius, and line spacing all adjustable
- **Border** — optional black border with adjustable width (0 = no border)
- **Centre disc** — adjustable size for the black vinyl label circle
- **Tonearm overlay** — a transparent PNG tonearm image with size and position controls
- **Poster text** — editable song title, artist, names, and date fields
- **Export to PNG** — 3300 × 4200 px at 300 DPI, ready for professional printing at 11″ × 14″
- **Export to SVG** — scalable vector format, opens in Illustrator, Inkscape, or any print shop

## Getting Started

### Option 1 — Use it directly (no install)

1. Download `index.html`
2. Double-click to open it in your browser
3. Edit your song details and adjust the sliders
4. Click **Download PNG** or **Download SVG**

> **Important:** Download the file and open it locally (`file://`). Do not try to use it directly from a CDN or file-sharing link — browser security policies will block the export buttons when the page is served from certain origins.

### Option 2 — Host on GitHub Pages

1. Fork or clone this repository
2. Go to **Settings → Pages → Source: Deploy from branch → main → Save**
3. Your editor will be live at `https://yourusername.github.io/vinyl-poster/`

## Controls Reference

### Poster Text
| Field | Description |
|-------|-------------|
| Song Title | Displayed in italic serif above the record |
| Artist | Small-caps text above the record |
| Names | Bold text below the record |
| Date | Smaller text below the names |

### Lyrics
| Control | Description |
|---------|-------------|
| Lyrics textarea | The text that fills the spiral. Newlines are treated as spaces. |
| 🔁 Repeat to fill | Lyrics loop continuously until the spiral is full |
| 1× Print once only | Lyrics appear exactly once; the spiral may have empty space toward the centre |

### Spiral
| Slider | Range | Description |
|--------|-------|-------------|
| Font Size | 5 – 36 pt | Size of the lyric text |
| Letter Spacing | 0 – 3 | Extra space between characters |
| Line Spacing | 5 – 45 px | Gap between spiral rings; also controls number of turns |
| Outer Radius | 180 – 500 px | Outer edge of the spiral |
| Inner Radius | 0 – 200 px | How close the spiral gets to the centre (0 = all the way to the middle) |

### Border
| Slider | Range | Description |
|--------|-------|-------------|
| Border Width | 0 – 120 px | Width of the black frame around the poster (0 = no border) |

### Centre Disc
| Slider | Range | Description |
|--------|-------|-------------|
| Disc Size | 20 – 124 px | Outer radius of the black vinyl label circle in the centre |

### Tonearm
| Slider | Range | Description |
|--------|-------|-------------|
| Size | 0.2 – 3× | Scale of the tonearm overlay image |
| Horizontal (X) | −200 – 900 px | Horizontal position |
| Vertical (Y) | −200 – 1000 px | Vertical position |

## Exporting & Printing

### PNG Export (recommended for printing)
- Click **⬇ Download PNG (300 dpi)**
- Output: `vinyl-poster-300dpi.png`, 3300 × 4200 px
- Print size: 11″ × 14″ at 300 DPI
- May take 10–20 seconds depending on your browser and machine

### SVG Export
- Click **⬇ Download SVG**
- Output: `vinyl-poster.svg`, fully scalable vector
- Opens in Adobe Illustrator, Inkscape, Affinity Designer, or any print shop workflow

### Where to Print
Any of these accept a walk-in 11×14 print job, usually same-day:
- **FedEx Office** — upload online or bring on USB; photo or matte paper
- **Staples** — similar, slightly cheaper
- **Costco Photo** — best price, ready same-day if ordered before noon

For framing, an off-the-shelf 11×14 frame from **Michaels**, **Hobby Lobby**, or **Target** fits perfectly.

## Technical Notes

- **No dependencies** — pure HTML, CSS, and vanilla JavaScript
- **Self-contained** — the tonearm PNG is base64-encoded directly in the file; no external requests
- **Spiral algorithm** — Archimedean spiral polyline, `STEPS=360` segments per turn for smoothness
- **Character width estimation** — `cw ≈ fontSize × 0.50 + letterSpacing × 0.3` with a 20% buffer in repeat mode
- **SVG coordinate space** — poster canvas is 1000 × 1260 units; exported PNG scales this up to 3300 × 4200 px
- **Download method** — uses `data:` URIs (not `blob:` URLs) to avoid Content-Security-Policy restrictions on CDN-hosted pages

## Browser Compatibility

| Browser | Preview | PNG Export | SVG Export |
|---------|---------|------------|------------|
| Chrome / Edge | ✅ | ✅ | ✅ |
| Firefox | ✅ | ✅ | ✅ |
| Safari | ✅ | ⚠️ May fail on large canvas | ✅ |

If PNG export fails in Safari, use the SVG download — it works in all browsers and is accepted by any print shop or design app.

## License

MIT — do whatever you like with it.
