# Omakase

A curated theme collection for VS Code and Zed with deep dark surfaces and calm aqua-blue contrast.

## Preview

![Screenshot 1](./assets/shot-1.jpg)

## Omakase Kuroshio

Omakase Kuroshio is a dark theme built for long coding sessions.

It focuses on clarity, strong contrast, and a calm visual rhythm so your editor feels elegant without becoming distracting.

## Highlights

- Deep black background for focus
- Calm blue and aqua palette
- Clear separation between functions, variables, strings, and types
- Built for long coding sessions

## Installation

### VS Code

1. Open Extensions in VS Code
2. Search for `Omakase`
3. Click Install
4. Open `Preferences: Color Theme`
5. Select `Omakase Kuroshio`

### Zed

The Zed package is ready for local development and future submission to the official Zed Extensions registry. It is not yet published there.

To install it locally on macOS:

1. Open Zed.
2. Open the command palette and run `zed: extensions`.
3. Click **Install Dev Extension**.
4. Select this repository's `packages/zed` directory.
5. Open the theme selector with `Cmd-K Cmd-T`.
6. Select `Omakase Kuroshio`.

If the extension does not load, run `zed: open log` and inspect `Zed.log`.

## Development

The existing VS Code theme at `themes/Omakase-Kuroshio-color-theme.json` remains the visual source of truth. The Zed theme at `packages/zed/themes/omakase-kuroshio.json` is a Zed-native translation because the editors expose different UI properties and syntax capture systems. When colors change, update the VS Code theme first, then apply the equivalent semantic color to the Zed theme and validate both files.

The Zed package is self-contained: its manifest, theme, and license are all available under `packages/zed`. It does not use Rust, Cargo, or WebAssembly.

### Validate VS Code

```sh
npm install
npx vsce package --out /tmp/omakase.vsix
```

Install the generated VSIX in VS Code with `Extensions: Install from VSIX...`, then select `Omakase Kuroshio` from `Preferences: Color Theme`.

### Publishing to the Zed Extensions registry

Do not perform these steps until the Zed package has been tested locally and the desired release commit has been pushed to a public branch.

1. Fork `zed-industries/extensions` to a personal GitHub account and clone the fork.
2. From the registry repository root, add Omakase as an HTTPS submodule:

   ```sh
   git submodule add https://github.com/byluisfer/Omakase.git extensions/omakase
   git add extensions/omakase .gitmodules
   ```

3. Add this entry to the registry's `extensions.toml`:

   ```toml
   [omakase]
   submodule = "extensions/omakase"
   path = "packages/zed"
   version = "1.0.0"
   ```

4. Confirm that the submodule commit is reachable from a branch, that `packages/zed/extension.toml` contains the same version, and that the MIT license resolves inside `packages/zed`.
5. Run `pnpm sort-extensions` from the registry repository root.
6. Commit the submodule and registry metadata, push the registry branch, and open a PR to `zed-industries/extensions`.
7. After the PR merges, search for `Omakase` in Zed Extensions and install the published extension.

For later releases: update this repository, bump `packages/zed/extension.toml`, push or tag the release, update the Omakase submodule commit in `zed-industries/extensions`, set the registry entry to the matching version, run `pnpm sort-extensions`, and open a registry PR. Once it merges, Zed can distribute the new version to users.

## About

Built by byLuisfer.
