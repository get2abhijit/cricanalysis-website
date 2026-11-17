# cricanalysis-website

Static site for **cricanalysis.in**: evidence-led cricket analysis with a focus on Associate nations and European cricket, by Abhijit Deshpande and Aniket Kashikar.

Live: https://cricanalysis.in/ (GitHub Pages, deploy from `main`, custom domain via `CNAME`)

Plain HTML and one stylesheet. No build step, no JavaScript, no tracking, no third-party requests. Light and dark mode follow the reader's system setting.

## Structure

```
index.html                 Home: intro, what we publish, latest articles
articles/index.html        All articles
articles/*.html            One file per article
about.html                 The analysts, how we work (#method), data, contact
404.html                   Not-found page (uses absolute /cricanalysis-website/ paths)
assets/style.css           All styling
assets/favicon.svg         Logo (ball with seam + rising bars)
sitemap.xml, robots.txt    For search engines
.nojekyll                  Serve files as they are
```

## Adding an article

1. Copy an existing file in `articles/` and change the title, `<meta name="description">`, canonical/og URLs, byline and body.
2. Add a card for it to `articles/index.html` and to "Latest articles" in `index.html`.
3. Add its URL to `sitemap.xml`.
4. House rules: lead with the finding; name the source and date of all data; keep fact, calculation and opinion apart (labels: `label-fact`, `label-calc`, `label-view`); flag small samples; never publish an unverified number.

Preview locally: `python3 -m http.server` in this folder, then open http://localhost:8000.

## Domain

`cricanalysis.in` is served from this repo (`CNAME`). Canonical URLs, `sitemap.xml` and `robots.txt` use `https://cricanalysis.in/`; `404.html` uses root-absolute paths (`/assets/...`).

The domain used to host Abhijit's personal site, which now lives at https://get2abhijit.github.io/abhijitdeshpande-website/. `projects/player-profiles.html` redirects to the article here; the 404 page points other old visitors to the personal site.

## Photos

`assets/images/` holds the analysts' photos (square, about 320 px, metadata removed). Aniket's card shows initials until `aniket-kashikar.jpg` is added and the About page is updated to use it.
