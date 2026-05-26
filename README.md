# Dandy Music — site CSS

WordPress/Avada custom CSS for [dandy-music.co.uk](https://dandy-music.co.uk).

## How it's deployed

The CSS file in this repo is served to the live site via [jsDelivr CDN](https://www.jsdelivr.com/), which proxies raw GitHub files with proper caching and `Content-Type: text/css`.

The live site loads it via a `<link>` tag in Avada → Theme Options → **Advanced → Code Fields → Space before `</head>`**:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/free777777/dandy-music-css@main/css/avadaextra.css?v=1">
```

## Edit workflow

1. Edit `css/avadaextra.css` locally
2. `git commit -am "describe change"` and `git push`
3. Either bump the `?v=` query string in the `<link>` tag, OR hit the purge URL:
   `https://purge.jsdelivr.net/gh/free777777/dandy-music-css@main/css/avadaextra.css`
4. Hard-refresh the live site (`Cmd+Shift+R`)

## Files

- `css/avadaextra.css` — the master stylesheet (only file the live site loads)
