# Wendy Vang portfolio

Source for my personal site, published with GitHub Pages. It is one HTML page and one stylesheet with no build step and no JavaScript. Design rules live in [DESIGN.md](DESIGN.md).

## Files

- `index.html`: the page
- `styles.css`: all styles, with colors, type, and spacing as CSS custom properties
- `favicon.svg`: site icon
- `assets/Wendy-Vang-Resume.pdf`: resume linked from the header
- `assets/img/`: project screenshots taken from each project's repository

## Preview locally

```bash
python -m http.server 8123
```

Then open http://localhost:8123.

## Publish

1. Push this folder to `Programming-Mellow/Programming-Mellow.github.io` (or any repository).
2. In the repository, open Settings, then Pages, and set the source to the `main` branch, root folder.
3. If the site ends up at a different address, update `og:url` and `og:image` in `index.html`.
