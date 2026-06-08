# Dandy Music — site CSS

WordPress/Avada custom CSS for [dandy-music.co.uk](https://dandy-music.co.uk).

## How it's deployed

The CSS file in this repo is served to the live site via [jsDelivr CDN](https://www.jsdelivr.com/), which proxies raw GitHub files with proper caching and `Content-Type: text/css`.

The live site loads it via a `<link>` tag in Avada → Theme Options → **Advanced → Code Fields → Space before `</head>`**. **Always pin to the commit SHA, never `@main`** — `@main` goes stale at the jsDelivr edge and you serve old CSS:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/free777777/dandy-music-css@afcc7f6/css/avadaextra.css">
```

## Edit workflow

1. Edit `css/avadaextra.css` locally
2. `git commit -am "describe change"` and `git push`
3. Grab the new short SHA (`git rev-parse --short HEAD`) and update the `@<sha>` in the live `<link>` tag
4. Hard-refresh the live site (`Cmd+Shift+R`)

> SHA-pinned URLs are immutable, so no purge step and no `?v=` cache-buster needed — a new SHA *is* the cache-bust.

## Files

- `css/avadaextra.css` — the master stylesheet (only file the live site loads)
