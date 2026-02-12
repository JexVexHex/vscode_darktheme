# Repository Guidelines

## Project Structure & Module Organization
This repository contains two VS Code theme packages: `green/` and `yellow/`. Each package is self-contained with `package.json`, a theme definition file (`oldtime-*-theme.json`), `README.md`, `LICENSE.md`, and preview assets (`screenshot.png`). Root-level `.vsix` files are packaged outputs, and `devel/` stores planning notes used during theme updates.

## Build, Test, and Development Commands
Run commands inside a theme folder, not from the repository root.

- `cd green && npm install`: install dependencies for the green theme package.
- `cd yellow && npm install`: install dependencies for the yellow theme package.
- `cd green && npx vsce package`: build `oldtime-green-theme-*.vsix`.
- `cd yellow && npx vsce package`: build `oldtime-yellow-theme-*.vsix`.
- `jq . green/oldtime-green-theme.json` (or yellow equivalent): quick JSON validity check before packaging.

## Coding Style & Naming Conventions
Theme files are JSON and should use 2-space indentation with double-quoted keys/values. Keep UI color keys grouped in `colors` and syntax scopes in `tokenColors`. Use lowercase hex color values for consistency (for example, `#333333`). Preserve established file naming patterns such as `oldtime-green-theme.json` and `oldtime-yellow-theme.json`.

## Testing Guidelines
There is no automated test framework in this repository. Validate changes manually in VS Code by loading each packaged theme and checking:

- editor/sidebar/panel contrast on dark backgrounds,
- border and focus visibility,
- token readability across comments, strings, keywords, and markdown scopes.

Verify both `green/` and `yellow/` variants before publishing artifacts.

## Commit & Pull Request Guidelines
Follow the commit style visible in Git history: `feat(theme): ...`, `fix(theme): ...`, `docs(readme): ...`, `chore(package): ...`, `plan(theme): ...`. Keep commit scope specific to one concern (for example, border colors, token colors, or docs updates).

PRs should include a short summary, the list of modified files, before/after screenshots for visual changes, and a note on whether new `.vsix` files were generated.

## Security & Configuration Tips
Do not commit secrets, local environment files, or editor-specific local config; `.gitignore` already excludes common local artifacts. Only publish packaged `.vsix` files that were built from reviewed theme JSON changes.
