---
title: "TODOs"
draft: false
menu:
  docs:
    title:
    parent: "PineNote/Development"
    identifier: "PineNote/Development/TODOs"
    weight: 5
---

## Kernel/driver TODOs
These exist, but they haven’t been written down yet.

## Artifacting

There is some artifacting with the current driver that has been difficult to diagnose and resolve. The github issue tracking this is here: https://github.com/PNDeb/pinenote-debian-image/issues/47

Some members of the community have been considering hiring an e-ink professional to consult on this issue. The thought is to hire someone with expertise in developing drivers for e-ink displays to provide advice and pointers, not to do the actual work (because that’s expensive).

## Userspace TODOs

The TODOs in this space are organized around what functionality they enable. A table of the important functions that a user may want in the PineNote and a status are listed below:

| Functionality | Approaches (apps) | Level of support (subjective) | Supports | Does not yet support | Notes .2+ |
| --- | --- | --- | --- | --- | --- |
| Reading Documents | `[Koreader](https://github.com/koreader/koreader)` | Great | Fully featured ebook reader; Supports many filetypes; | Handwritten notes | Large user base on many devices; codebase has a somewhat of a reputation for being messy |

### Themes

A lot of getting the PineNote to work nicely will be theming things appropriately. Please list themes for various components here:

#### GNOME

Untested: https://github.com/fujimo-t/gnome-shell-theme-e-ink

#### GTK

TODO

### GNOME Configurations

See [here](/documentation/PineNote/Development/Apps#gnome).

### Sway Configurations

See [here](/documentation/PineNote/Development/Apps#sway).

## Documentation TODOs

* Pin Mesa Packages so they don’t update when we upgrade other packages
  * Add the information near step 5 [here](/documentation/PineNote/Development/Building_kernel#steps_to_build).
* Control the backlight
* Building alacritty correctly
* Force a screen refresh?
  * See conversation here: https://matrix.to/#/!QtTzSRYMuozjbOQkzJ:matrix.org/$tfumBpnP2UPouNpaeFrggR40ZkrD_pHAtJdQmQvzL-o?via=matrix.org&via=kde.org&via=tchncs.de

### Status table draft

This table is a draft for the documentation development page:

| Functionality | Component | Status (Android from factory) | Status (Linux) | Notes |
| --- | --- | --- | --- | --- |
| Bootloader | `Bootloader` |  Android only |  WIP for Linux | Booting into linux requires a patched U-Boot. [Instructions here.](/documentation/PineNote/Development/Booting_Linux) .4+ |
| Operating System | `Stability` 2+ | WIP | Users have successfully booted Arch, Manjaro, and Debian. Debian has most support right now. | `Suspend` 2+ |
| Works | [This kernel patch](https://gitlab.com/hrdl/pinenote-shared/-/blob/main/patches/linux/0001-Rudimentary-attempt-to-keep-PMIC-usable-after-suspen.patch) adds suspend support. | `Updates` 2+ | WIP | GPU libs (mesa) and mutter rely on patched packages. These should not be updated via the package manager at the moment, make sure to exclude them. |
| `Networking` 2+ | Works | .5+ | Components | `E-Paper Display` 2+ |
| WIP | Mostly functional. There is some ghosting and work remains, but the device and screen are usable. | `Touch` 2+ | Works |  |
| `Bluetooth` 2+ | Works, audio stutters | [Switching the driver](/documentation/PineNote/Development/Building_kernel#fixing_bluetooth) provides stable connections for keyboards, but audio still stutters. Trying to fix this [here](/documentation/PineNote/Development/Software_tweaks#preliminary_fix_for_stuttering_bluetooth_audio). | `Sensors` 2+ | Unsure |
| Light sensors? Rotational sensors? | `Buttons` 2+ | Works | Power button works. | Accessory compatibility, spare parts |
