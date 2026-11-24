# UnbrickTool // Android Recovery & Flashing Utility (v0.3)

**UnbrickTool** is a lightweight, zero-bloat local web interface for recovering bricked Android devices. Built with Python and Flask, it wraps standard `ADB`, `Fastboot`, and low-level emergency port scanners (`Qualcomm EDL 9008` & `MediaTek BROM`) into a clean, dark-mode engineering UI — available as a standalone offline Windows `.exe` or cross-platform Python script.

![UnbrickTool Preview]
<img width="484" height="730" alt="image" src="https://github.com/user-attachments/assets/b31b9eef-9d4b-44a9-9651-32ebf8548c25" />


## Key Features

- **100% Offline Standalone `.exe`:** Pre-bundled with `adb.exe`, `fastboot.exe`, and official Google USB Drivers — no Python or internet connection required on Windows.
- **One-Click USB Driver Installer:** Installs signed Google WinUSB drivers directly via `pnputil` with a single click.
- **Soft Brick & Bootloop Recovery:**
  - Instant exit from Fastboot loops (`fastboot reboot`) and direct reboot to Recovery.
  - Active slot switching (`--set-active=a` / `--set-active=b`) for A/B partition devices stuck in bootloops.
  - Bootloader unlock status verification (`getvar unlocked`).
  - Direct flashing for `boot`, `init_boot`, `recovery`, and `vbmeta` images.
- **Hard Brick Detection & Flashing (EDL 9008 & MTK BROM):**
  - Automatically detects `Qualcomm HS-USB QDLoader 9008` and `MediaTek USB / PreLoader` ports.
  - Supports Firehose (`rawprogram0.xml`) flashing for Qualcomm devices and `MTKClient` boot recovery for MediaTek chips.
- **Bilingual UI (`EN / RU`) & Simulation Mode:** Instant language toggle in the top bar and a built-in simulation mode to test workflows without a connected device.

## Download (Windows)

Go to the **[Releases](../../releases)** page and download `UnbrickTool_v0.3_Win64.zip`. Extract and run `UnbrickTool.exe` — the interface will launch automatically in your default browser.

## Run from Source (Windows / Linux / Android Termux)

```bash
git clone https://github.com
cd UnbrickTool
pip install -r requirements.txt
python main.py
```

### Termux (Android OTG)
```bash
pkg install python android-tools
pip install flask
python main.py
```

## Compatibility Notes

- **Soft Brick (Fastboot/ADB):** Works on all Android devices with standard Fastboot support (requires an unlocked bootloader for partition flashing).
- **Qualcomm EDL 9008:** Works out-of-the-box on devices with unauthenticated / patched Firehose programmers (`No-Auth`). Modern Xiaomi/Redmi/POCO and Samsung devices with server-side EDL Auth still require an authorized service account.
- **MediaTek BROM:** Works on devices with an open BootROM interface via `mtkclient`.

## Support the Project

If this tool saved your device, consider giving the repository a **Star** ⭐ or supporting future updates:
im working for free

