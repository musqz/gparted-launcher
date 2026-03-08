# gparted-launch

## A lightweight GParted wrapper for Linux.

Inspired by the original `gparted_shell` from Puppy Linux, rewritten for modern Linux systems using `yad` and `lsblk` instead of `gtkdialog` and `probedisk`.

## Why this wrapper

GParted launched directly will scan **all** connected drives at startup. On systems with multiple disks or USB devices this causes a slow and unnecessary probe. This wrapper lets you pick exactly the drive you want before GParted opens — making it faster to start and safer to use, since there is no risk of accidentally operating on the wrong device.

One drive, one window, on purpose.

## Dependencies

| Package | Purpose |
|---|---|
| `gparted` | The partition editor |
| `yad` | GTK dialog for drive selection |
| `lsblk` | Drive detection (part of `util-linux`) |

Install any missing dependency with:
```bash
sudo pacman -S gparted yad util-linux
```

## Installation

```bash
cp gparted-launch ~/bin/
chmod +x ~/bin/gparted-launch
```

Optionally add the `.desktop` file to your application menu:
```bash
cp gparted-launch.desktop ~/.local/share/applications/
```

## Usage

Run from terminal or launch via menu:
```bash
gparted-launch
```

A dialog lists all detected drives with name, type, size and model. Select one and click **Launch**. GParted opens directly on that device. To work on a different drive, close GParted and run the launcher again.

## License

MIT
