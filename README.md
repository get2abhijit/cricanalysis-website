# cricanalysis-website

Static site for **cricanalysis.in**: evidence-led cricket analysis with a focus on Associate nations and European cricket, by Abhijit Deshpande and Aniket Kashikar.

Live (GitHub Pages, deploy from `main`): https://get2abhijit.github.io/cricanalysis-website/

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

## Moving to cricanalysis.in (not done yet)

`cricanalysis.in` currently points at the personal site (`get2abhijit/abhijitdeshpande-website`, which has the `CNAME`). To switch without breaking links:

1. Decide where the personal site will live (e.g. its github.io address or a new domain) and remove its `CNAME`.
2. Add a `CNAME` file containing `cricanalysis.in` to this repo and set the custom domain in Settings → Pages.
3. Change the canonical/og URLs and `sitemap.xml`/`robots.txt` from the github.io address to `https://cricanalysis.in/`, and the 404 page's `/cricanalysis-website/` paths to `/`.
4. Old personal-site URLs under cricanalysis.in (e.g. `/projects/player-profiles.html`, `/notes/...`) will 404 after the switch. Add small redirect pages at those paths here (a `<meta http-equiv="refresh">` plus a link) pointing either to the new article or to the personal site's new home.
