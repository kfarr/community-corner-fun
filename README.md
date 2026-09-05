# SF Community Corners

A simple, durable landing page for San Francisco's **Community Corners** pilot: the SFMTA program
that lets neighborhoods turn safer, daylit street corners into beautiful places with planters and
murals. It explains *what it is, why it matters, how to get one, the rules, the supporting coalition,
and an FAQ*, and collects interest sign-ups.

Built as **plain HTML/CSS/JS** with no build step, no dependencies, and no framework. Open the folder,
edit the files, deploy them anywhere.

## Files

```
index.html     All page content (semantic, accessible). Edit copy here.
styles.css     All styling (design tokens at the top in :root).
main.js        Tiny optional enhancements (sticky nav, mobile menu, scroll reveal).
assets/
  favicon.svg
  img/         Real corner photos (.jpg); see IMAGES.md for sources, credits & how to add more
  img/partners/  Drop partner logos here + REPLACE-ME.md (how to wire them up)
  video/       REPLACE-ME.md (how to add the hero timelapse)
```

## Preview locally

Just open `index.html` in a browser; that's it. Or serve it (nicer for testing):

```bash
python3 -m http.server   # then visit http://localhost:8000
```

## Things to fill in (search the code for `TODO`)

1. **Hero video.** Add a timelapse to `assets/video/` and uncomment the `<video>` block in `index.html`.
   See `assets/video/REPLACE-ME.md` for specs (16:9, < 5 MB, muted loop). Until then the hero is a
   still photo of the Cortland Ave corner.
2. **Photos.** All images are real photos now. To add or swap one, see `assets/img/IMAGES.md`
   (sizes, sources, and the one third-party credit).
3. **Partner logos.** The "Supported by" section (`#partners`) lists the coalition as text tiles.
   Drop real logos into `assets/img/partners/` and swap them in. See
   `assets/img/partners/REPLACE-ME.md`.
4. **Contact.** The footer "Get involved" column links to the interest form, Green SF Now, Civic Joy
   Fund, and the GitHub repo. There is deliberately no contact email; add one there if the project
   gets a shared address.
5. **Official source links** in the footer: confirm they still resolve.

## Editing content

All copy lives in `index.html` as plain text; change wording directly. To restyle, the color
palette, fonts, spacing, and radii are CSS variables in `:root` at the top of `styles.css`.

## Deploy

It's a static folder, so any static host works:

- **Netlify / Cloudflare Pages / Vercel:** drag-and-drop the folder, or connect the repo (no build
  command, publish directory = project root).
- **GitHub Pages (current setup):** `.github/workflows/static.yml` deploys the repo root to Pages on
  every push to `main`. Nothing else to configure.

## Accessibility & performance notes

- Works with JavaScript disabled (FAQ uses native `<details>`; all nav is real anchors).
- Respects `prefers-reduced-motion`; AA color contrast; keyboard-navigable; descriptive `alt` text.
- No external JS/CSS frameworks; images below the fold lazy-load; the hero image is `fetchpriority="high"`
  and the (optional) hero video is `preload="none"`. The signup form is an embedded Google Form.

## Disclaimer

This is an independent, community-run advocacy site. It is not affiliated with or endorsed by the
City and County of San Francisco. Always confirm program details with official SFMTA sources.
