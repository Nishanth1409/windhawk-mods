# Windhawk Mods — Nishanth K R

Custom and curated **[Windhawk](https://windhawk.net/)** mods for Windows 11 shell, tray audio/mic, wallpapers, and taskbar behavior.

**Author:** [Nishanth K R](https://github.com/Nishanth1409) · Portfolio [nkrportfolio.vercel.app](https://nkrportfolio.vercel.app)  
**Related toolkit (Windows cleanup/menu — no mods here):** [windows-system-maintenance](https://github.com/Nishanth1409/windows-system-maintenance)

> **Canonical Windhawk folder:** `D:\Projects\tools\windhawk-mods` (this repo).  
> Runtime installs still live under `C:\ProgramData\Windhawk`. Personal image paths in settings JSON are sanitized to placeholders.

---

## Featured mods (authored / heavily customized)

| Mod | Version | What it does |
| :--- | :--- | :--- |
| **[Lock Screen Wallpaper](analysis/lock-screen-wallpaper)** | 2.2 | Force a custom lock screen image and keep it after restart, sleep, and sign-out |
| **[Mic Tray Switch & Control](analysis/mic-tray-switch)** | 0.5.0 | Microphone counterpart of Tray Audio Output: live input list with % gain, one-click default, mute, scroll-to-adjust gain, preferred slots, priority auto-switch |
| **[Per-Monitor Wallpaper](analysis/per-monitor-wallpaper)** | 1.6 | Set and persist wallpapers on extended/external monitors only (primary display is never changed) |
| **[Taskbar Auto-Hide Peek in Fullscreen](analysis/taskbar-always-visible-fullscreen)** | 1.2.3 | Auto-hide edge peek (mouse to bottom) works in fullscreen apps — same as a normal window |
| **[Tray Audio Output](analysis/tray-audio-output)** | 1.5.8 | System tray audio: pick output, volume, scroll to switch, share to multiple speakers (WASAPI mirror). Auto device list with smart Bluetooth limits |

Each featured folder includes:

| File | Role |
| :--- | :--- |
| `*.cpp` / `*.wh.cpp` | Mod source — paste into Windhawk → Compile |
| `*.bak` | Source backup snapshot |
| `*.json` / `*.wh.json` | Settings backup (placeholder paths) |

---

## Full catalog (`analysis/`)

40 mod folders covering taskbar stylers, Explorer tweaks, Start menu, notifications, translucency, Alt+Tab per monitor, clipboard, and more. See the table in the archived System Maintenance Windhawk guide, or browse [`analysis/`](analysis/).

Community-origin mods may retain upstream licenses (check headers). Featured SystemMaintenance mods use **MIT** unless noted.

---

## Install (Windhawk)

1. Install [Windhawk](https://windhawk.net/).
2. Open a mod’s `.cpp` / `.wh.cpp` → copy into Windhawk Mod Editor.
3. **Compile** (`Ctrl+B`) → enable the mod.
4. Import matching `.json` settings if desired (replace placeholder image paths).
5. Restart Explorer when the mod targets `explorer.exe`.

### Tray Audio / Mic Tray

These run as **tool mods** (`@include windhawk.exe`). Check the hidden tray icons overflow if the icon is missing.

### Taskbar peek in fullscreen

Requires **Settings → Personalization → Taskbar → Automatically hide the taskbar**.

---

## Development notes

- Local analysis tree: `C:\SystemMaintenance\windhawk\analysis`
- Compiled DLLs appear under `C:\ProgramData\Windhawk\Engine\Mods\` as `local@<id>_…`
- After changing settings in the Windhawk UI, re-export JSON into `analysis/<mod-id>/` to keep this repo current

---

## License

MIT for mods authored under SystemMaintenance / Nishanth K R. Upstream community mods: see each file’s `@license` header.
