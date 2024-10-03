---
title: "Modifications and repairs"
draft: false
hidden: true
menu:
  docs:
    title:
    parent: "PinePhone/Hardware_fixes_and_mods"
    identifier: "PinePhone/Hardware_fixes_and_mods/Modifications_and_repairs"
    weight: 
---

## Replacing the mainboard

The mainboard can be replaced if it is faulty. The replacement board does not have an operating system pre-installed, to test if everything is working after swapping the mainboard a flashed microSD card is required.

**💡 TIP**\
Replacement boards come with an empty eMMC, which means that trying to boot from them looks like the board is faulty (no LEDs, no screen, no reaction of the phone). Please boot an operating System from a microSD card.

Prior to replacing your PinePhone’s mainboard please read the steps outlined in bullet points below and watch the attached video.

1. You’ll need a small Phillips screwdriver and a prying tool to swap out the mainboard.
2. Remove the PinePhone’s back cover. See your quick start guide for details.
3. Remove the battery as well as any inserted SD and SIM cards.
4. Unscrew all 15 Phillips head screws around the midframe of the phone.
5. Gently pry up the midframe using a guitar pick or credit card corner. It is easiest to separate the midframe at one of the bottom edges. Work your way around all the sides of the phone until the midframe separates from the phone’s body.
6. Detach all ribbon cables and "Lego" connectors. List of things to detach: 1) two "Lego" connects at the bottom of the mainboard. 2) u.FL antenna connect and touchscreen digitizer on PCD left side. 3) LCD ribbon cable top of mainboard, next to audio and UART jack.
7. Pry the mainboard up gently from the left-hand side.
8. Remove front and main cameras and reset them into the new mainboard.
9. Check that the rubber proximity sensor housing is in the chassis, not stuck to the removed mainboard.
10. Place the new mainboard in the chassis, hooking in on the plastic tabs on left side and pressing down firmly on opposite side, and follow the steps (7-2) in reverse. When reattaching the midframe take care that no cables are out of place or trapped, as they may be damaged when tightening screws.

After swapping the mainboard the phone won’t boot as there is no OS on the replacement board’s eMMC preinstalled. To boot an OS insert a flashed SD card.

A video tutorial by _Martijn Braam_ can be found here (or alternatively a video tutorial by user _brigadan_ with additional notes about the camera swap and proximity sensor isolator [here](https://www.youtube.com/watch?v=J3AJEF7akkw)):

![width=600](/documentation/images/Pinephone_martijn_pcb_replacement.png)

### Flashing the ANX firmware

#### Method 1

After swapping the mainboard the ANX7688 chip has to be flashed for full USB functionality.

Under GNU/Linux this can be done by downloading the latest ANX7688 firmware image on the phone:

    wget https://xff.cz/git/linux-firmware/plain/anx7688-fw.bin

and executing as root ("sudo su") on the phone:

    cp anx7688-fw.bin /lib/firmware/
    echo 1 > /sys/class/typec/port0/device/flash_eeprom

#### Method 2

Booting a factory test image will automatically flash the ANX7688 chip. See [Factory Test OS](/documentation/PinePhone/Software/Releases/#hardware_test_build) for such an image.

## Replacing the screen

Before attempting to replace the screen be sure to review the section on [replacing the mainboard](/documentation/PinePhone/Hardware_fixes_and_mods/Modifications_and_repairs/#replacing_the_mainboard) since that will get you most of the way there. Be aware that the replacement screen is actually the entire front frame of the phone and there are components that will need to be swapped from your old screen.

* Make sure you have a precision screwdriver set that has the correct size Philips tip. The screws are very small and the heads can easily be stripped if the screwdriver is not correct - if you feel your screwdriver slipping, stop what you are doing and try one that is a better fit. A magnetized screwdriver will help in not losing screws, as will a magnetic parts holder to keep them in while working.
* There are a number of components and cables as well as the insulator sheet under the battery that are glued in place. A hair dryer will loosen the glue and make them much easier to remove. You may want to order extra cables along with the screen just in case.
* The vibration motor, which is part of the USB-C board assembly and glued into place, will come apart easily and be damaged if you pry it up in the wrong place. Make sure you pry from underneath the complete part, not midway on its housing. The ribbon cable attaching this to the USB-C board is small, thin, and fragile so be careful with that as well.
* The new screen comes with new side switches and insulator sheet but there are a number of parts that need to be transferred from the old screen, like the thin coax cable running up the side, the phone ear speaker, proximity sensor gasket, and a gold-colored mesh glued in place that needs to be transferred to a flexible circuit included on the new screen. If you don’t swap over the proximity sensor rubber gasket the screen will immediately turn off after logging in. Be careful when routing the coax cable that it goes around the screw holes or you may drive a screw right through the cable.

Take your time, use the right tools, be careful and you should be rewarded with success.

## Spare parts not available in the Pine Store

* Earpiece dimensions: 12x6x2 mm. Compatible with Xiaomi Mi2 / Mi3 (but not Mi4!) and others, see [here](https://forum.pine64.org/showthread.php?tid=12046&pid=85698#pid85698)
* Loudspeaker dimensions: 15x11x3 mm. Compatible with Nokia N91, Lenovo A536 (requires soldering) and others, see [here](https://forum.pine64.org/showthread.php?tid=12046&pid=85698#pid85698)
* Proximity sensor rubber isolator

## Other hardware issues

See also [Hardware issues](/documentation/PinePhone/Hardware_fixes_and_mods/Hardware_issues) for more issues and how-to’s.
