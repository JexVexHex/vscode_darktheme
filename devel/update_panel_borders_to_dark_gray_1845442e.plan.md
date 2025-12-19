---
name: Update Panel Borders to Dark Gray
overview: Change all panel border colors from blue (#0080ff) and theme colors to dark gray (#1a1a1a) in both theme files, preserving alpha channel values where present.
todos: []
---

# Update Panel Borders to Dark Gray

## Overview

Update all panel border colors in both `oldtime-green-theme.json` and `oldtime-yellow-theme.json` to use dark gray (`#1a1a1a`) instead of the current blue (`#0080ff`) or theme colors, making borders subtle but visible for section identification.

## Changes Required

### Files to Modify

- [`green/oldtime-green-theme.json`](green/oldtime-green-theme.json)
- [`yellow/oldtime-yellow-theme.json`](yellow/oldtime-yellow-theme.json)

### Border Properties to Update

Both theme files currently have the following border properties that need updating:

1. **Panel borders** (currently `#0080ff` or theme colors):

- `panel.border` - currently `#00ff00` (green) / `#ffff00` (yellow) → `#1a1a1a`
- `panelTitle.activeBorder` - currently `#0080ff` → `#1a1a1a`
- `panelSectionHeader.border` - currently `#0080ff80` → `#1a1a1a80` (preserve alpha)
- `editorGroup.border` - currently `#0080ff` → `#1a1a1a`
- `editorGroupHeader.tabsBorder` - currently `#0080ff` → `#1a1a1a`
- `sideBar.border` - currently `#0080ff` → `#1a1a1a`
- `sideBarSectionHeader.border` - currently `#0080ff60` → `#1a1a1a60` (preserve alpha)
- `activityBar.border` - currently `#0080ff` → `#1a1a1a`
- `activityBar.activeBorder` - currently `#0080ff` → `#1a1a1a`
- `tab.activeBorder` - currently `#0080ff` → `#1a1a1a`
- `tab.border` - currently `#0080ff40` → `#1a1a1a40` (preserve alpha)
- `statusBar.border` - currently `#0080ff` → `#1a1a1a`
- `titleBar.border` - currently `#0080ff` → `#1a1a1a`

2. **Widget/Input borders** (currently theme colors):

- `editorWidget.border` - currently `#00ff00` (green) / `#ffff00` (yellow) → `#1a1a1a`
- `input.border` - currently `#00ff00` (green) / `#ffff00` (yellow) → `#1a1a1a`

### Color Choice

- Base dark gray: `#1a1a1a` (RGB: 26, 26, 26) - dark enough to be subtle but visible against black background
- Alpha channels preserved: `80` (50% opacity), `60` (37.5% opacity), `40` (25% opacity)

### Implementation Notes

- All changes will be made to the `colors` object in both JSON files
- Alpha channel suffixes (`80`, `60`, `40`) will be preserved where they exist