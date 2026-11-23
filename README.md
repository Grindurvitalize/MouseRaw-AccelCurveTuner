<p align="center">
  <img src="https://i.postimg.cc/T3Vv8zYb/banner.png" alt="MouseRaw Sensitivity & 1:1 Curve Tuner — True Raw Input & eDPI / cm-360° Converter" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%2F11%20x64-0078D6?style=flat-square&logo=windows" alt="Platform: Windows 10/11 x64">
  <img src="https://img.shields.io/badge/Mode-1%3A1%20Raw%20Mouse%20%26%20eDPI%20Tool-2EA44F?style=flat-square" alt="Mode">
  <img src="https://img.shields.io/badge/Release-mouseraw--curve--v1.2-5391FE?style=flat-square" alt="Release Tag">
  <img src="https://img.shields.io/badge/License-MIT-8B5CF6?style=flat-square" alt="License: MIT">
</p>

# MouseRaw Sensitivity & 1:1 Curve Tuner — True Raw Input & eDPI / cm-360° Converter

**Windows updates quietly re-enabling 'Enhance Pointer Precision' mouse acceleration, or switching between CS2, Valorant, Apex Legends, and Overwatch 2 and losing your muscle memory? Lock true 1:1 Windows mouse scaling and convert exact cm/360° sensitivity across games.**

MouseRaw Sensitivity & 1:1 Curve Tuner combines Windows mouse registry verification with an FPS sensitivity converter: **locking 6/11 (10/20) pointer speed, disabling `MouseSpeed` acceleration, optionally applying exact MarkC 1:1 `SmoothMouseXCurve`/`YCurve` tables, and converting `cm/360°` across major shooters**.

This project is aimed at **Windows 10 and Windows 11 (64-bit) FPS and competitive PC gamers** maintaining consistent 1:1 mouse aim without heavy peripheral driver bloat.

## Quick Use-Case & Troubleshooting Reference

| Scenario / Issue | Cause | Solution |
| --- | --- | --- |
| Mouse cursor feels inconsistent or floaty after a Windows 11 update | Windows re-enabled `Enhance Pointer Precision` (`MouseSpeed=1`) or changed pointer slider | Enforce `MouseSensitivity=10` (6/11) and `MouseSpeed=0` with 1-click lock |
| Older DirectInput games ignore Raw Input and use Windows curves | Legacy games read `SmoothMouseXCurve` / `SmoothMouseYCurve` even when EPP is unchecked | Apply exact **1:1 Linear MarkC Curve** for your display scaling (`100%` / `125%` / `150%`) |
| Converting mouse sensitivity between CS2, Valorant, Apex & Warzone | Every game engine uses a different yaw multiplier | Enter your DPI + source sensitivity to get exact **eDPI** and **cm/360°** equivalents |
| Want to revert Windows mouse registry curves back to stock defaults | Manual `.reg` edits are hard to undo cleanly | Click **Restore Stock Windows Mouse Curve** anytime |

## Download for Windows

[**Download MouseRawCurve.zip — Latest GitHub Release (Windows x64)**](../../releases/latest/download/MouseRawCurve.zip)  
[View All Releases & Changelog](../../releases) · [Report an Issue](../../issues)

### Why use `MouseRawCurve.exe`? (Key features)

- Audits `HKCU\Control Panel\Mouse` for `MouseSensitivity=10` (6/11), `MouseSpeed=0`, and active DPI scaling.
- Applies exact **1:1 Linear `SmoothMouseXCurve` / `SmoothMouseYCurve`** tables for `100%`, `125%`, `150%`, and `175%` Windows scaling.
- Built-in **FPS Sensitivity & cm/360° Converter** supports *CS2*, *Valorant*, *Apex Legends*, *Overwatch 2*, *Call of Duty*, *Rainbow Six Siege*, and *Fortnite*.
- Exports an automatic `.reg` backup before applying any registry curve with 1-click rollback.

### Sample Output

```text
[MouseRawTuner] Auditing HKCU\Control Panel\Mouse & Display DPI Scaling (100%)...
[OK]   Pointer Speed    : 10 (6/11 — True 1.0x Multiplier) | Enhance Precision: OFF
[OK]   1:1 Linear Curve : Applied exact 100% DPI SmoothMouseXCurve / YCurve (Backup saved)
[INFO] Sensitivity Calc : 800 DPI @ 1.05 CS2 = 840 eDPI (49.48 cm/360°) -> Valorant: 0.330
```

The release ZIP is named `MouseRawCurve.zip`; the Windows executable inside is named `MouseRawCurve.exe`.

1. Close MouseRaw Tuner before updating or replacing executable files.
2. Click **Download MouseRawCurve.zip** above.
3. Right-click the downloaded archive and choose **Extract All**.
4. Open the extracted folder and run `MouseRawCurve.exe`.
5. Review the options and output paths before processing files.

**Requirements:** Windows 10 or 11 (64-bit).

### Verification & Windows SmartScreen Note

- **Offline & standard user permissions:** `MouseRawCurve.exe` runs locally without uploading your personal files and does not require disabling Windows Defender.
- **Windows SmartScreen:** Because this is an independent open-source utility without a commercial EV code-signing certificate, Windows SmartScreen may show *"Windows protected your PC"* on first launch. Click **More info → Run anyway** after verifying the release checksum on the [Releases](../../releases) page.

## Problems this project solves

### True 1:1 unaccelerated aim even in older games without Raw Input

Linear `SmoothMouseXCurve`/`YCurve` ensures 1:1 pixel response across legacy and modern titles alike.

### Exact muscle-memory conversion across FPS engines

Calculates true physical `cm/360°` distance so your flicks feel identical in every shooter.

### Zero background processes required after applying

Writes native Windows registry curves and exits cleanly.

### Instant `.reg` backup & restore

Revert to default Windows mouse curves in one click.

## Default folders and configuration paths

MouseRaw Tuner configures `HKCU\Control Panel\Mouse` and stores a backup in `%APPDATA%\MouseRawTuner`:

```text
HKCU\Control Panel\Mouse\
```

Typical directory layout:

```text
HKCU\Control Panel\Mouse\
├── MouseSensitivity  = "10"  (6/11 True 1:1 Scale)
├── MouseSpeed        = "0"   (Acceleration Disabled)
├── SmoothMouseXCurve = [Exact 1:1 Linear Table]
└── SmoothMouseYCurve = [Exact 1:1 Linear Table]
```

Sign out and sign back in (or restart Windows) after applying `SmoothMouseXCurve` / `SmoothMouseYCurve` so Windows reloads the curve tables.

## Quick start guide

Follow these steps to get started:

1. **Extract `MouseRawCurve.zip` and launch `MouseRawCurve.exe`.** Review your current pointer speed, acceleration state, and Windows DPI scaling.
2. **Click **Apply 1:1 Raw Curve** (automatic `.reg` backup is created first).** Sign out and back in to activate the curve system-wide.
3. **Use the **eDPI & cm/360° Converter** tab to match sensitivities across your FPS games.** Close MouseRaw Tuner completely—zero background RAM needed.

### Data safety note

MouseRaw Tuner saves `stock_mouse_backup.reg` before modifying any registry value.

## What the status summary shows

MouseRaw Tuner displays **pointer speed ratio, Enhance Pointer Precision status, Windows DPI scaling %, 1:1 curve match, and calculated eDPI / cm-360°**.

## FAQ

**Does MouseRaw Tuner need to stay running while I play?**

No. Once you apply the 1:1 curve and sign out/in, Windows uses it natively with zero background apps.

**Why does Windows DPI scaling (100% vs 125% vs 150%) affect mouse curves?**

Windows multiplies `SmoothMouseYCurve` by your desktop DPI scaling factor when acceleration is active; MouseRaw Tuner matches the curve table to your exact display scaling.

**How do I restore the default Windows mouse settings?**

Open MouseRaw Tuner, click 'Restore Stock Windows Curve', and sign out/in.

## Useful reading

- [PCGamingWiki — Glossary: Mouse Acceleration & Raw Input](https://www.pcgamingwiki.com/wiki/Glossary:Mouse_acceleration)

## More Windows Gaming Utilities

- [PadDrift-ControllerPollingTest](../PadDrift-ControllerPollingTest) — Gamepad stick drift & mouse polling rate (1000-8000 Hz) tester
- [CrosshairDot-CustomGamingOverlay](../CrosshairDot-CustomGamingOverlay) — Click-through custom screen crosshair & PNG reticle overlay
- [WinTimer-LatencyDoctor](../WinTimer-LatencyDoctor) — Windows gaming latency, Ultimate Performance & timer check
- [KeySwap-CustomRemapTray](../KeySwap-CustomRemapTray) — Native Windows Scancode keyboard remapper with 1-click reset

*Independent open-source desktop utility for Windows.*
