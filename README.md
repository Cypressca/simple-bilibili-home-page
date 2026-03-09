# simple-bilibili-home-page

A Tampermonkey userscript that replaces the default bilibili homepage with a clean, fast search-first layout.

## Features

- Top-left quick links: Dynamic, History, Watch Later, Favorites
- Clean center search box for bilibili content
- Built-in logo rendering via inline SVG (no external file dependency)
- Auto dark mode with `prefers-color-scheme`
- Early injection (`document-start`) to reduce homepage flash
- Scroll disabled on homepage for an app-like view
- Better compatibility with Bilibili Evolved and similar extensions

## Install

1. Install Tampermonkey in your browser.
2. Open `simple-bilibili.js`.
3. Copy the full script into a new Tampermonkey script.
4. Save and enable it.
5. Visit `https://www.bilibili.com/`.

## Files

- `simple-bilibili.js`: Main userscript
- `Bilibili_logo_blue.svg`: Source logo asset used to generate inline SVG

## Notes

- Script only runs on `https://www.bilibili.com/` root page.
- If another extension modifies homepage DOM aggressively, keep this script at a higher execution priority in Tampermonkey.

## License

MIT
