# lindanichols.dev

Personal site + speaker bio / press kit. Plain static HTML, no build step.

```
lindapalooza/
├── index.html        # Home page
├── bio.html          # Bio / press kit (headshot, short/medium/long bios, speaking, contact)
├── style.css         # Shared styles (warm editorial/print look, light + dark, responsive)
├── CNAME             # Custom domain for GitHub Pages
├── assets/
│   └── headshot.jpg  # <-- add your headshot here with this exact name
└── README.md
```

Fonts (Marcellus, PT Serif) load from Google Fonts over the network, so a live internet
connection is needed to see them; without it the site falls back to system serif fonts.

## Before you publish

1. **Add your headshot** as `assets/headshot.jpg` (or change the filename in `bio.html`).
2. **Fill the `[BRACKETS]`** in `bio.html`. They're HTML comments (invisible to visitors)
   marking things to confirm or add, e.g. the placeholder speaking engagement.

## Preview locally

From this folder:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000

## Publish to GitHub Pages

1. Create a **public** repo on GitHub (any name, e.g. `personal-site`).
2. Push these files to the `main` branch.
3. Repo **Settings → Pages** → Source: **Deploy from a branch** → Branch: `main` / `/root` → Save.
4. Under the same Pages screen, set **Custom domain** to `lindanichols.dev` (the `CNAME`
   file already does this too) and check **Enforce HTTPS**.

## Point the domain (DNS at your registrar for lindanichols.dev)

Add these records so the apex domain resolves to GitHub Pages:

| Type  | Host / Name | Value                     |
|-------|-------------|---------------------------|
| A     | @           | 185.199.108.153           |
| A     | @           | 185.199.109.153           |
| A     | @           | 185.199.110.153           |
| A     | @           | 185.199.111.153           |
| CNAME | www         | <your-github-username>.github.io |

DNS can take up to a few hours to propagate; HTTPS may take a little longer to activate.
