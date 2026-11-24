# UnbrickTool // Android Recovery & Flashing Utility (v0.4)

**UnbrickTool** is a lightweight, zero-bloat local web interface for recovering bricked Android devices. It wraps `ADB`, `Fastboot`, `Fastbootd`, and emergency low-level port scanners (`Qualcomm EDL 9008` & `MediaTek BROM`) into a clean engineering UI — packaged as a 100% offline Windows `.exe`.

<img width="488" height="830" alt="image" src="https://github.com/user-attachments/assets/02a49255-79fa-4dcd-ae16-df120391bf4f" />


## What's New in v0.4
- **`fastbootd` Mode:** Added `reboot fastbootd` button to enter userspace fastboot for flashing dynamic partitions (`system`, `product`, `vendor`).
- **Smart `vbmeta` Flashing:** Automatically applies `--disable-verity --disable-verification` flags when flashing `vbmeta` to prevent `dm-verity` / `The system has been destroyed` bootloops.
- **Factory Reset (`fastboot -w`):** One-click user data wipe with a safety confirmation prompt.
- **ADB Quick Reboot Panel:** Reboot directly into Bootloader or Recovery from a booted Android OS (`adb reboot bootloader` / `adb reboot recovery`).
- **Offline Driver Installer:** Bundled signed Google USB Drivers directly inside the executable — installs offline via `pnputil`.

## Key Features
- **100% Offline Standalone `.exe`:** Pre-bundled with `adb.exe`, `fastboot.exe`, and signed Google USB Drivers — no Python or internet connection required.
- **Soft Brick & Bootloop Recovery:** Exit Fastboot loops (`fastboot reboot`), reboot to Recovery/Fastbootd, switch active slots (`--set-active=a/b`), check unlock state (`getvar unlocked`), and flash `boot`, `init_boot`, `recovery`, `vbmeta`, or `system`.
- **Hard Brick Scanner & Flashing (EDL 9008 & MTK BROM):** Automatically detects `Qualcomm HS-USB QDLoader 9008` and `MediaTek USB / PreLoader` ports for Firehose (`rawprogram0.xml`) and `MTKClient` boot recovery.
- **Bilingual UI (`EN / RU`) & Simulation Mode:** Instant language toggle in the top bar and a built-in simulation mode to test workflows without a connected device.

## Download (Windows)
Go to the **[Releases](../../releases)** page and download `UnbrickTool.exe` (`v0.4`). Run it — the interface opens automatically in your default browser.

## Compatibility Notes
- **Soft Brick (Fastboot/ADB):** Works on all Android devices with standard Fastboot support (requires an unlocked bootloader for partition flashing).
- **Qualcomm EDL 9008:** Works out-of-the-box on devices with unauthenticated / patched Firehose programmers (`No-Auth`). Modern Xiaomi/Redmi/POCO and Samsung devices with server-side EDL Auth still require an authorized service account.
- **MediaTek BROM:** Works on devices with an open BootROM interface via `mtkclient`.

## Support
If this tool helped unbrick your device, please consider giving the repository a **Star** ⭐!
