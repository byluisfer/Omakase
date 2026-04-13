# OMAKASE

OMAKASE starts with a clean flagship dark theme: `OMAKASE Dark`.

It aims for a deep black workspace, low-noise chrome, and bright syntax accents that stay readable during long coding sessions.

## Preview The Theme

You can preview the theme locally with the built-in VS Code extension workflow:

1. Open this folder in Visual Studio Code.
2. Press `F5`.
3. A new **Extension Development Host** window will open.
4. In that new window, run `Preferences: Color Theme`.
5. Pick `OMAKASE Dark`.

There is no build step for this theme right now. Editing the JSON and pressing `F5` again is enough to preview updates.

## Create More Themes

Each new theme follows the same simple pattern:

1. Add a new JSON file inside [`themes`](/Users/luisfer/Documents/01 Projects/OMAKASE-Theme/themes).
2. Register it in [`package.json`](/Users/luisfer/Documents/01 Projects/OMAKASE-Theme/package.json) under `contributes.themes`.
3. Press `F5` and select the new theme in the Extension Development Host.

Example contribution entry:

```json
{
  "label": "OMAKASE Light",
  "uiTheme": "vs",
  "path": "./themes/OMAKASE-light-color-theme.json"
}
```

## Current Direction

`OMAKASE Dark` uses:

- Near-black backgrounds for a focused dark mode foundation
- Cool blue structure colors for navigation and editor chrome
- Soft green strings, rose keywords, gold properties, and violet types
- Brighter contrast on active surfaces so the UI still feels premium, not flat
