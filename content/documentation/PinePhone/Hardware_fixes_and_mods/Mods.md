---
title: "Mods"
draft: false
hidden: true
menu:
  docs:
    title:
    parent: "PinePhone/Hardware_fixes_and_mods"
    identifier: "PinePhone/Hardware_fixes_and_mods/Mods"
    weight: 
---

There are a number of options to hardware mod the PinePhone.

Some are upgrades to fix issues that were not done optimally in the production of that version of the electronics, and some are to add options that were not part of the phone spec.

## General

Make pictures of the situation before and after your mods, so you can compare the change, and don’t need to disassemble the device to get the right pics later.

## Laser cut parts

Mcyam2 has created some laser cut templates for the rear facing components here:

https://imgur.com/a/LAUatOa

https://anonfiles.com/L0BeK5L5oe/ppsvg-backplate-CUTOUT_svg

Originally based on silver’s work on a 3d printed rear frame

## 3D Printed parts

Silver has created a 3D-printable rear frame for the PinePhone and used it to create a folding keyboard design (work in progress), User:Silver/3d printed a folding keyboard mostly.

https://ibb.co/album/ScDttH

https://www.youmagine.com/designs/pinephone-folding-keyboard-mockup

## PCBs

https://github.com/SMR404/PinephonePogoBreakout

https://github.com/jnavarro7/pinephone_flex_breakout_board_grove

## Device Specific Mods

There are a number of upgrades possible for the different versions of the PinePhone.

### Braveheart Edition

{{< admonition type="warning" >}}
 These are fixes for hardware bugs for old revisions of the PinePhone (from 2019 and early 2020). They do not apply to current revisions.
{{< /admonition >}}

* PMIC mod - Stops the battery drain from a shutdown phone, draining the battery to 0V.
* VCONN mod - Unblocks the USB-C power negotiation rail, so convergence functions are unlocked.

#### PMIC mod

[PinePhone 1.1 VBUS power usage hardware fix](/documentation/PinePhone/Hardware_fixes_and_mods/PinePhone_1.1_VBUS_power_usage_Hardware_Fix)

The original description of this fix is given on megi’s pager here https://xnux.eu/devices/pp-pmic-fix.jpg

#### VCONN mod

See below.

### Braveheart Edition and UBPorts Community Edition

{{< admonition type="warning" >}}
 These are fixes for hardware bugs for old revisions of the PinePhone (from 2019 and early 2020). They do not apply to current revisions.
{{< /admonition >}}

* VCONN mod - Unblocks the USB-C power negotiation rail, so convergence functions are unlocked.

There are also a number of mods that can be done adding more functions by adding extra hardware to the pogo pins, and a number of options to change the screen protector.

At this moment there are not many pogo addons, and most are just connector boards. Likely the makers will add links to these projects to this page. Pine is looking into adding a N900 style keyboard attached to these pins.

#### VCONN mod

The original description of this fix is given on megi’s pager here https://xnux.eu/devices/pp-usbc-fix.jpg
There is a discussion on the merits of the different ways to do the fix

##### VCONN mod, Removal only

[PinePhone 1.2 VCONN hardware fix](/documentation/PinePhone/Hardware_fixes_and_mods/PinePhone_1.2_VCONN_Hardware_Fix)

There are now a few documented ways,

* Removal only, the tweezer "stupid" way: https://www.youtube.com/watch?v=j3jc7Mvn9Eo
* Removal only, the soldering iron "less stupid" way: https://www.youtube.com/watch?v=ZqOb45N2sMc

There are hopefully videos coming doing it the proper way, and so they can be linked here.

After this the firmware for the power negotiation chip needs to be upgraded, this can be done by running the factory test image, version http://images.postmarketos.org/pinephone/pine64-pinephone-20200724-factorytest55.img.xz or higher. This will do the firmware flashing and respond with a message indicating the state. After this the phone is ready for its added functions.
ANX states:

* No CC Fix - Fix not applied
* No USB Cable - No USBC connection, cannot upgrade firmware
* OK - Firmware Applied, you are all set

##### VCONN mod, Replacement

Using 2x NCP334FCT2G you could do the full fix, making VCONN powered devices able to negotiate power. IT needs the parts to be removed first without damaging the pads, and then replacing the parts.
