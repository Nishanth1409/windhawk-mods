# Windhawk Mods

Custom and curated **[Windhawk](https://windhawk.net/)** mods for Windows 11 (taskbar, tray audio/mic, wallpapers, Explorer, and more).

**Author:** [Nishanth K R](https://github.com/Nishanth1409) · [Portfolio](https://nkrportfolio.vercel.app)  
**Related:** [windows-system-maintenance](https://github.com/Nishanth1409/windows-system-maintenance) (PC cleanup menu — no mods in that repo)

Settings JSON may contain **placeholder** image paths — replace them with your own files after import.

---

## Install from scratch

### 1. Install Windhawk
Download and install from [windhawk.net](https://windhawk.net/).

### 2. Get this repo
```bash
git clone https://github.com/Nishanth1409/windhawk-mods.git
cd windhawk-mods
```

### 3. Add a mod (beginner)
1. Open Windhawk → create / open a mod.  
2. Open `analysis/<mod-id>/<mod-id>.cpp` (or `.wh.cpp`) in this repo.  
3. Copy all source into the Windhawk editor.  
4. **Compile** (`Ctrl+B`) → enable the mod.  
5. If the mod targets Explorer, restart Explorer or sign out/in.

### 4. Import settings (intermediate)
1. In Windhawk, open the mod’s settings.  
2. Import the matching `analysis/<mod-id>/*.json` (or `.wh.json`).  
3. Replace any placeholder image/file paths with real paths on your PC.

### 5. Keep the repo in sync (pro)
1. Tweak settings in the Windhawk UI.  
2. Export JSON back into `analysis/<mod-id>/`.  
3. Commit when you want a backup of your curated set.

Compiled engine files are managed by Windhawk under its ProgramData engine folder — you normally only edit sources/JSON in this repo.

---

## Featured mods

| Mod | Folder | What it does |
| :--- | :--- | :--- |
| Lock Screen Wallpaper | `analysis/lock-screen-wallpaper` | Custom lock image that sticks after reboot/sleep |
| Mic Tray Switch & Control | `analysis/mic-tray-switch` | Tray mic list, gain, mute, preferred devices |
| Per-Monitor Wallpaper | `analysis/per-monitor-wallpaper` | Wallpapers on extended monitors only |
| Settings Styler (no XAML diagnostics) | `analysis/settings-styler-safe` | Full Settings Styler engine minus the tap that crashes Background / Lock screen, plus a blurred wallpaper backdrop for when the window loses focus |
| Taskbar Auto-Hide Peek in Fullscreen | `analysis/taskbar-always-visible-fullscreen` | Edge peek works in fullscreen |
| Translucent Windows | `analysis/translucent-windows` | Native translucent effects (Explorer) |
| Tray Audio Output | `analysis/tray-audio-output` | Tray outputs, volume, scroll switch, mirror |

Each folder typically has: source (`.cpp` / `.wh.cpp`), `.bak` snapshot, settings JSON.

**Translucent Windows** is upstream by [Undisputed00x](https://github.com/Undisputed00x); this copy narrows `@include` to `explorer.exe`. The `.bak` file is the original 1.8.0 with `@include *`. `SystemSettings.exe` was dropped because the Settings window is a UWP app with opaque XAML, so these frame level effects never showed there; *Settings Styler (no XAML diagnostics)* handles that window.

**Settings Styler (no XAML diagnostics)** is a fork of *Windows 11 Settings Styler* by [m417z](https://github.com/m417z) (GPL-3.0). The styling engine is untouched; the XAML diagnostics tap is no longer installed, and elements are discovered by a timed visual tree walk that skips React Native subtrees (so **Background** and **Lock screen** keep working). Existing Settings Styler configurations can be imported as-is.

For the curated look in this repo: compile `settings-styler-safe.wh.cpp`, import `settings-styler-safe.wh.json` (or run `apply-settings.reg` elevated, then toggle the mod), and leave **Theme** set to none. Leave **Blurred wallpaper backdrop** on — focused Settings uses live acrylic; when the window loses focus, a blurred copy of the current desktop wallpaper shows instead of flat grey, and it follows wallpaper changes on its own. **Wallpaper backdrop detail** (lower = blurrier) and **Wallpaper backdrop tint** tune that unfocused look.

Browse all mods under [`analysis/`](analysis/).

---

## Tips

- **Tray Audio / Mic Tray** run as tool mods (`windhawk.exe`). Check the hidden tray overflow if the icon is missing.  
- **Taskbar peek in fullscreen** needs *Settings → Personalization → Taskbar → Automatically hide the taskbar*.  
- After you **move a game** (for example Riot / VALORANT), update that mod’s **Excluded folders** setting to the new install path, then recompile / reload the mod so fullscreen peek stays disabled for those apps.  
- Do not run the original *Windows 11 Settings Styler* or a separate Settings-transparent mod alongside `settings-styler-safe` — they fight over the same surfaces.  
- Community mods may keep upstream licenses — check file headers.

## License

MIT for mods authored by Nishanth K R unless noted. Upstream community mods: see each file’s `@license`. **Settings Styler (no XAML diagnostics)** inherits GPL-3.0 from the original Settings Styler.
