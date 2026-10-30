# iOS Web Widgets

Transparent, monochrome lock screen widgets for iOS, built as a single HTML page for the [Widget Web 27](https://apps.apple.com/br/app/widget-web-27/id1522169352) app.

No build step, no dependencies: one `index.html`.

## Widgets

| URL | Size | Shows |
| --- | --- | --- |
| `?w=rect` | Rectangular | Year-progress ring, weekday, date, moon phase, ISO week |
| `?w=circle` | Circular | Day of the month with a month-progress ring |
| `?w=moon` | Circular | Moon phase with % illuminated |

Opening the page without `?w=` shows a lock screen preview with copyable links. If the page is loaded in a widget-sized viewport without `?w=`, it picks `rect` for wide spaces and `circle` for square ones.

### Options

- `&c=000000` sets the widget color (hex, no `#`). Default is white.
- `&hemi=n` draws the moon as seen from the northern hemisphere. Default is southern (Brazil).

Labels are in Brazilian Portuguese and dates use the device's local time.

## Hosting

Any static host works. Config for the common ones is included:

- **GitHub Pages:** Settings → Pages → Deploy from branch → `main` / root. URL: `https://apontes-dev.github.io/ios-web-widgets/?w=rect`
- **Netlify:** `_headers` disables caching so widget refreshes always get fresh content.
- **Vercel:** `vercel.json` does the same.

## Setup in Widget Web 27

1. Create a new widget in the app and paste a widget URL, e.g. `…/?w=rect`.
2. Turn on transparent background for the lock screen.
3. On the lock screen, touch and hold → Customize → add Widget Web in the matching size.
4. Set auto-refresh to every hour to keep the date and moon phase current.
