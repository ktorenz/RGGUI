# RG-Downloads

Download host for the RG settings app and device firmware.

## Software

- The app exe lives in [`dist/`](dist/) (Windows 10/11, digitally signed).
  The app self-updates from this file.

## Firmware

Two hardware generations, matching the model selector in the app:

| Folder | Model |
|---|---|
| `firmware/usb_c/` | **Pro Model** (USB-C charging port) |
| `firmware/micro_usb/` | **Old Model** (Micro-USB charging port) |

Each model has:

- `gun/` — P1–P4 `.uf2` files, one per player slot
- `Receiver/` — P1–P4 `.uf2` files, one per player slot
- `flash_nuke/` — erases the device flash for a clean re-flash

### Manual flashing (without the app)

1. Hold the button on the device (gun: inside the battery bay; receiver:
   on the dongle) while plugging its USB into the PC.
2. A drive named **RPI-RP2** appears.
3. Drag the matching `.uf2` onto that drive. The device reboots flashed.

## How the app uses this repo

- `update-log.txt` — advertised latest versions; the app compares at startup
  and shows the update notification.
- `download-urls-software.txt` — URL the self-updater downloads the exe from.
- `download-urls-firmware.txt` — URLs the firmware flasher downloads from.

Editing those text files re-points existing installs — no app update needed.
