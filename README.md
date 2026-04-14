# VS Code Theme

Starter color theme extension. Edit `themes/theme-dark.json` for UI (`colors`) and syntax (`tokenColors`), then reload the Extension Development Host window.

## Prerequisites

- [Node.js](https://nodejs.org/) (LTS recommended)
- [Visual Studio Code](https://code.visualstudio.com/)

## Local development

1. Open this folder in VS Code.
2. Run **Run Extension** from the Run and Debug panel (or press F5).
3. In the new window, open **Preferences: Color Theme** and pick **VS Code Theme (Dark)**.

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

1. Replace `your-publisher` and the `repository.url` in `package.json` with your [publisher id](https://code.visualstudio.com/api/working-with-extensions/publishing-extension#create-a-publisher) and repo URL.
2. Create a new repository on GitHub and push this folder:

```bash
git init
git add .
git commit -m "Initial VS Code theme extension"
git branch -M main
git remote add origin https://github.com/your-username/vscode-theme.git
git push -u origin main
```

## Publish to the VS Code Marketplace (optional)

1. Create a [Personal Access Token](https://code.visualstudio.com/api/working-with-extensions/publishing-extension#get-a-personal-access-token) with **Marketplace (Manage)**.
2. `npx vsce login your-publisher`
3. `npm run publish`

## Add a light theme

1. Copy `themes/theme-dark.json` to e.g. `themes/theme-light.json`, set `"type": "light"`, and adjust hex values.
2. In `package.json`, under `contributes.themes`, add another entry with `"uiTheme": "vs"` and `"path": "./themes/theme-light.json"`.
