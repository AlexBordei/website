---
title: "Tips and tricks"
draft: false
menu:
  docs:
    title:
    parent: "PineTab"
    identifier: "PineTab/Tips_and_tricks"
    weight: 4
---

### Reset

If your PineTab is in unknown state or doesn’t want to start: Press power button for 7-8s. It makes a sound and you know it’s totally off. 3 seconds after, power button  again for 2-3s and it will start to boot.

### Power Off While Charging

When plugging your Pinetab into a charger, it automatically powers on. Use the above "Reset" instruction (holding the power button in for several seconds) to turn it off. This will allow your Pinetab to charge without being powered on.

### Display rotated 90° on Arch ARM

With the following command you can turn the display to landscape:

    echo 1 | sudo tee /sys/class/graphics/fbcon/rotate

This command does not persist a reboot.
