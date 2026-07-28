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
| Taskbar Auto-Hide Peek in Fullscreen | `analysis/taskbar-always-visible-fullscreen` | Edge peek works in fullscreen |
| Tray Audio Output | `analysis/tray-audio-output` | Tray outputs, volume, scroll switch, mirror |

Each folder typically has: source (`.cpp` / `.wh.cpp`), `.bak` snapshot, settings JSON.

Browse all mods under [`analysis/`](analysis/).

---

## Tips

- **Tray Audio / Mic Tray** run as tool mods (`windhawk.exe`). Check the hidden tray overflow if the icon is missing.  
- **Taskbar peek in fullscreen** needs *Settings → Personalization → Taskbar → Automatically hide the taskbar*.  
- Community mods may keep upstream licenses — check file headers.

## License

MIT for mods authored by Nishanth K R unless noted. Upstream community mods: see each file’s `@license`.
