---
title: "JTAG"
draft: false
menu:
  docs:
    title:
    parent: "PineCone"
    identifier: "PineCone/JTAG"
    weight: 2
---

| Default JTAG pins |
| --- |
| GPIO Pin |
| JTAG Pin |
| GPIO17 |
| TDI |
| GPIO11 |
| TDO |
| GPIO12 |
| TMS |
| GPIO14 |
| TCK |

BL602 multiplexes four GPIO pins to provide the familiar JTAG lines. See the accompanying table for the default pin mappings.

These are the default JTAG pins in use after a cold boot. However, many pieces of software, including the demo that’s installed by default on new PineCones, remap these pins to other functions. You cannot use the default wiring for JTAG while such software is running. This issue is especially prevalent on the PineCone because three of the default JTAG pins are connected to the onboard RGB LED. Nothing about the LED itself interferes with JTAG, but any program that uses the LED will necessarily remap some of the default JTAG pins to be GPIO.

The MaskROM download mode that the BL602 enters when you tie GPIO8 high does **not** remap the default JTAG pins, and so you can and should use that mode while checking basic functionality of your JTAG adapter.

Note that, just as software can remap the default JTAG pins to be something else, it can also remap other pins to be JTAG. Control over this is quite granular, with 5-6 candidate pins for each individual JTAG signal that can be mapped independently of one another. LEE Lup Yuen has written some [sample code](https://lupyuen.github.io/articles/openocd#free-the-led-from-jtag-port) showing how to remap the JTAG pins so that your software can use the LED without giving up support for debugging.
