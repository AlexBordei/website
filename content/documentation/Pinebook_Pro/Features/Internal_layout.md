---
title: "Internal layout"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Features"
    identifier: "Pinebook_Pro/Features/Internal_layout"
    weight: 
---

## Main chips

* RK3399 system-on-chip (1)
* LPDDR4 SDRAM (21)
* SPI NOR flash memory (29)
* eMMC flash memory module (26; Note: Some datasheets indicate a low supported number of mating cycles.)
* WiFi/BT module (27)

## Mainboard Switches and Buttons

There are two switches on the main board: disabling the eMMC module (24), and enabling serial console UART (9) via headphone jack.

The Reset and Recovery buttons (28): the reset button performs an immediate reset of the laptop. The Recovery button is used to place the device in maskrom mode. This mode allows flashing eMMC using Rockchip tools (e.g. rkflashtools).

![width=500](/documentation/images/PBPL_S.jpg)

## Key Internal Parts

|     |     |     |     |
| --- | --- | --- | --- |
| + Numbered parts classification and description | Number | Type | Descriptor |
| scope=row | 1 | Component | RK3399 System-On-Chip |
| scope=row | 2 | Socket | PCIe x4 slot for optional NVMe adapter |
| scope=row | 3 | Socket | Speakers socket |
| scope=row | 4 | Socket | Touchpad socket |
| scope=row | 5 | Component | Left speaker |
| scope=row | 6 | Connector | Power bridge connector |
| scope=row | 7 | Socket | Keyboard Socket |
| scope=row | 8 | Component | Optional NVMe SSD adapter |
| scope=row | 9 | Switch | UART/Audio switch - enables serial console UART via headphone jack |
| scope=row | 10 | Socket | Power bridge socket |
| scope=row | 11 | Socket | Battery socket |
| scope=row | 12 | Component | Touchpad |
| scope=row | 13 | Component | Battery |
| scope=row | 14 | Component | Right speaker |
| scope=row | 15 | Socket | MicroSD card slot |
| scope=row | 16 | Socket | Headphone / serial console UART jack |
| scope=row | 17 | Socket | USB 2.0 Type A |
| scope=row | 18 | Socket | Daughterboard-to-mainboard ribbon cable socket |
| scope=row | 19 | Cable | Daughterboard-to-mainboard ribbon cable |
| scope=row | 20 | Component | microphone |
| scope=row | 21 | Component | LPDDR4 RAM |
| scope=row | 22 | Socket | Mainboard-to-daughterboard ribbon cable socket |
| scope=row | 23 | Socket | Microphone socket |
| scope=row | 24 | Switch | Switch to hardware disable eMMC |
| scope=row | 25 | Antenna | BT/WiFI antenna |
| scope=row | 26 | Component | eMMC flash memory module |
| scope=row | 27 | Component | BT/WiFi module chip |
| scope=row | 28 | Buttons | Reset and recovery buttons |
| scope=row | 29 | Component | SPI flash storage |
| scope=row | 30 | Socket | eDP LCD socket |
| scope=row | 31 | Socket | Power in barrel socket |
| scope=row | 32 | Socket | USB 3.0 Type A |
| scope=row | 33 | Socket | USB 3.0 Type C |

## Smallboard detailed picture

![width=600](/documentation/images/Pinebook_pro_smallboard.jpg)
