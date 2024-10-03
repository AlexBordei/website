---
title: "Debugging"
draft: false
menu:
  docs:
    title:
    parent: "SOEDGE"
    identifier: "SOEDGE/Debugging"
    weight: 2
---

## Serial Console

System Serial is located on PI-5 bus (11x2 GPIO header).

* TXD: Pin 6 (Yellow cable) (Connect to RXD on Serial adapter)
* RXD: Pin 8 (Orange cable) (Connect to TXD on Serial adapter)
* GND: Pin 10 (Black cable) (Connect to GND on Serial adapter)

![width=400](/documentation/SOEDGE/images/Soedge_serial_pins.jpg)

The default baudrate is 1500000, note that not all serial adapters support this high baudrate.
