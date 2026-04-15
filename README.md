# Syntax on the Rocks

Pour a smooth, late-night coding experience.

Syntax on the Rocks brings the vibrant yet relaxed energy of local nightlife straight to your editor. Inspired by the moody atmospheres and neon accents of evening happy hours, this theme delivers a perfectly balanced dark mode. It features deep, muted backgrounds paired with crisp, punchy syntax highlighting—designed to keep your eyes comfortable and your code readable long after the sun goes down over the valley.

Grab a drink, dim the lights, and write some liquid code.

## Prerequisites

- [Node.js](https://nodejs.org/) (LTS recommended)
- [Visual Studio Code](https://code.visualstudio.com/)

## Local development

1. Open this folder in VS Code.
2. Run **Run Extension** from the Run and Debug panel (or press F5).
3. In the new window, open **Preferences: Color Theme** and pick **Syntax on the Rocks**.

## Change colors later

- **Workbench / UI:** keys under `colors` in `themes/theme-dark.json`. Reference: [Theme color reference](https://code.visualstudio.com/api/references/theme-color).
- **Syntax:** `tokenColors` (TextMate scopes). Use **Developer: Inspect Editor Tokens and Scopes** from the Command Palette to see scopes under the cursor.

## Package a `.vsix`

```bash
npm install
npm run package
```

This creates `vscode-theme-0.0.1.vsix` (name follows `package.json`).

## Publish on GitHub

This project tracks **[Syntax on the rocks](https://github.com/iDevam/Syntax-on-the-rocks)** (`repository.url` in `package.json` is set accordingly).

If this clone has no `origin` yet:

```bash
git remote add origin https://github.com/iDevam/Syntax-on-the-rocks.git
git branch -M main
git push -u origin main
```

If `origin` already exists and should point at this repo:

```bash
git remote set-url origin https://github.com/iDevam/Syntax-on-the-rocks.git
git push -u origin main
```

## Publish to the VS Code Marketplace (optional)

1. Create a [Personal Access Token](https://code.visualstudio.com/api/working-with-extensions/publishing-extension#get-a-personal-access-token) with **Marketplace (Manage)**.
2. `npx vsce login your-publisher`
3. `npm run publish`

## Add a light theme

1. Copy `themes/theme-dark.json` to e.g. `themes/theme-light.json`, set `"type": "light"`, and adjust hex values.
2. In `package.json`, under `contributes.themes`, add another entry with `"uiTheme": "vs"` and `"path": "./themes/theme-light.json"`.
