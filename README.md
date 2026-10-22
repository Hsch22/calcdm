# calcdm

An iOS-style calculator with a fixed two-step magic routine, based on [dmaso/calcdm](https://github.com/dmaso/calcdm).

Open: **https://hsch22.github.io/#magic** (direct page: **https://hsch22.github.io/magic/**).

## Fixed routine

1. Enter any numbers or calculation, or leave the display at zero.
2. The first **=** shows **20261030**.
3. The second and every later **=** show **20361030**.
4. Press **AC** to clear the calculator and restart from **20261030**.

**C** clears the current entry or pending expression without restarting the routine. Reloading the page starts a fresh routine. The revealed numbers are displayed without thousands separators. Keyboard **Enter** and **=** work like the equals button; **Escape** works like C/AC.

The two results are hardcoded. The original target-setting and tap-entry controls do not override them, including targets supplied through a URL or local storage.

## Add to Home Screen

1. Open https://hsch22.github.io/magic/ in Safari.
2. Choose **Share → Add to Home Screen** and name it **Calculator**.
3. Launch once while online to cache the app for offline use.

The original portrait-only layout is preserved: the screen goes black in landscape orientation.

## Development and publishing

Static files, no build step:

- `index.html` — calculator markup and inline SVG glyphs.
- `style.css` — the original iOS-style portrait layout.
- `app.js` — calculator input and the fixed result sequence.
- `manifest.webmanifest`, `sw.js`, `calc-icon.png` — Home Screen installation and offline assets.
- `reference/` — upstream screenshots and visual comparison tools.

The six runtime files above are also published in `magic/` in [Hsch22/Hsch22.github.io](https://github.com/Hsch22/Hsch22.github.io). Keep those copies in sync when updating the calculator. Its service worker only removes older caches belonging to its own scope.

## Credits

The interface and original I.C.F. forcing mechanism come from [dmaso/calcdm](https://github.com/dmaso/calcdm). This fork replaces equals with the fixed routine described above.
