# MacroIconSearch

A fork of [Lardeck/MacroIconSearch](https://github.com/Lardeck/MacroIconSearch) updated for WoW 12.0 (Midnight) only.

## What it does

MacroIconSearch adds a search bar to the macro and equipment manager icon picker popups. Instead of scrolling through thousands of icons to find the one you want, you can search to filter icons instantly.

Features:
- **Spell name search** - Type a spell name to filter the icon grid to matching results
- **Icon filename search** - Search by texture filename (e.g. "wrench", "inv_misc") using a bundled database of ~32K icons
- **Exact match** - Wrap your search in quotes for an exact name match
- **Icon ID input** - Enter a numeric icon ID directly to set a specific icon
- **Equipment manager support** - Works in both the macro UI and the gear manager icon picker
- **MacroSetup compatibility** - Integrates with the MacroSetup addon if installed

## Updating the icon database

`IconData.lua` is a generated file containing ~32K icon filename-to-FileDataID mappings. To regenerate it after a new WoW patch (requires Python 3):

```
python3 tools/generate_icondata.py
```

This downloads the [community listfile](https://github.com/wowdev/wow-listfile) from GitHub, filters for `interface/icons/*.blp` entries, and writes `IconData.lua`.

## Manual Installation

1. Download or clone this repository
2. Copy the following files into `World of Warcraft/_retail_/Interface/AddOns/MacroIconSearch/`:
   - `MacroIconSearch.toc`
   - `MacroIconSearch.xml`
   - `IconData.lua`
   - `Core.lua`
   - `icon.tga`
3. Restart WoW or reload the addon list
