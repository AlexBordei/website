---
title: "Software State"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone_Pro/Software"
    identifier: "PinePhone_Pro/Software/Software_state"
    weight: 4
---

Presently the PinePhone Pro Explorer Edition is aimed at **Linux developers with an extensive knowledge of embedded systems and/or experience with mobile Linux**. It will take time for all the PinePhone Pro’s functionality to reach software parity with the original PinePhone and for mobile operating systems, in more general, to reach a higher degree of maturity.

Bear in mind that the software for these smartphones is still in a very early stage, with most of the software being in alpha or beta state. That’s especially also the case for scalability of applications, their availability and practicability, any hardware function implementations and the firmware. The software is provided as is. There is no warranty for the software, not even for merchantability or fitness for a particular purpose.

The following table lists the feature functionality status of the unaltered pre-installed factory image of the current shipping batch and as comparison an up-to-date reference image (no responsibility is accepted for the accuracy of this information, the list is provided and updated by the community). If you have any questions regarding the current state of the software or of specific features working, please don’t hesitate to ask in the [community chat](/documentation#Community_and_Support) **before buying the device**:

* Discord: _#pinephone_ under https://discord.gg/pine64
* IRC: _#pinephone_ on _irc.pine64.org_. Note: please consider Matrix, Discord or Telegram due to the volatile nature of IRC
* Matrix: https://app.element.io/#/room/#pinephone:matrix.org
* Telegram: https://t.me/pinephone

**💡 TIP**\
The software is **written by the community**, any contributions towards the community projects are greatly appreciated! Please see "[How to Contribute](/documentation/Introduction/How_to_contribute)" to learn about how to contribute to the software projects and "[Where to Report Bugs](/documentation/Introduction/Where_to_report_bugs)" to learn about where to report bugs.

| Functionality | Component | Status (factory)¹ | Status (updated)² | Notes .3+ |
| --- | --- | --- | --- | --- |
| Bootloader | `Bootloader` 2+ | Working |  | `SPI` 2+ |
| Working | Devices bought after July 2022 come with Tow-Boot or rk2aw flashed to the SPI memory | `Boot GUI` 2+ | Working | Implemented with _rk2aw_ .3+ |
| Operating System | `Stability` 2+ | WIP |  | `Suspend` 2+ |
| Experimental | Audio is often higher pitched after waking up from suspend due to a bug, make sure to update your system^[Report](https://github.com/dreemurrs-embedded/Pine64-Arch/issues/381);^ ^[Report](https://gitlab.manjaro.org/manjaro-arm/packages/core/linux-pinephonepro/-/issues/3)^ | `Updates` 2+ | WIP | The pre-flashed and outdated operating system on the eMMC often gets corrupted after updating^[Example](https://forum.pine64.org/showthread.php?tid=15950)^; Pacman database lock preventing updates^[Solution](https://wiki.archlinux.org/title/pacman#%22Failed_to_init_transaction_(unable_to_lock_database)%22_error)^; Keyring bug (solution is to run "pinephonepro-post-install" script as root). .5+ |
| Modem | `General` 2+ | WIP | [Alternative firmware](https://github.com/Biktorgj/pinephone_modem_sdk); Slow wakeup^[Report](https://gitlab.com/mobian1/devices/eg25-manager/-/issues/34)^; Some carriers blocking specific TANs in their network^[Carrier support](/documentation/PinePhone/Modem/Carrier_support)^; **Note:** Proprietary firmware | `Phone` 2+ |
| WIP | The modem connection crashes frequently, which can lead to missed calls^[Report](https://gitlab.com/mobian1/devices/eg25-manager/-/issues/34#note_984212350);^ ^[Alternative firmware](https://github.com/Biktorgj/pinephone_modem_sdk)^; Slow wakeup^[Report](https://gitlab.com/mobian1/devices/eg25-manager/-/issues/34)^; bad call audio quality^[Report](https://gitlab.manjaro.org/manjaro-arm/issues/pinephone/phosh/-/issues/249)^; Audio is often higher pitched after waking up from suspend due to a bug^[Report](https://github.com/dreemurrs-embedded/Pine64-Arch/issues/381);^ ^[Report](https://gitlab.manjaro.org/manjaro-arm/packages/core/linux-pinephonepro/-/issues/3)^ | `SMS` 2+ | Working | SMS functionality is expected to work. In certain cases the functionality might be blocked by a clogged modem^[Report](https://gitlab.manjaro.org/manjaro-arm/issues/pinephone/phosh/-/issues/203)^; Some bugs |
| `MMS` 2+ | WIP | MMS functionality is integrated into the application "Spacebar", some bugs remaining and expected | `Push notifications` 2+ | Not implemented |
| Receiving push notifications while the phone is suspended is not implemented .12+ | Components | `LCD` 2+ | WIP | **Hardware issue**^[Details](https://xnux.eu/log/#055)^ |
| `Touch` 2+ | Working |  | `Rear camera` | Not working |
| WIP | Camera work-in-progress with DTS fix^[Citation]^; userspace still needs to do some catching up^[debugging article](/documentation/PinePhone_Pro/Various/IMX258_camera_debugging)^; Green image tint^[Citation]^ | `Front camera` | Not working | WIP |
| Camera work-in-progress with DTS fix^[Citation]^; userspace still needs to do some catching up^[debugging article](/documentation/PinePhone_Pro/Various/IMX258_camera_debugging)^; Green image tint^[Citation]^ | `Camera flash` 2+ | Critical issues | **Hardware issue**^[Details](https://xnux.eu/log/#069)^; Note: `/sys/class/leds/white:flash` | `WiFi` 2+ |
| Working | WiFi is expected to work. The firmware does not support monitor mode and package injection. **Note:** Proprietary firmware | `Bluetooth` 2+ | WIP | Bluetooth not necessarily working for calls yet due to missing audio routing^[Citation]^; Bluetooth in general dodgy under Pulseaudio.^[Info](https://wiki.archlinux.org/title/bluetooth_headset#Headset_via_Pipewire)^ **Note:** Proprietary firmware |
| `GNSS/GPS` 2+ | WIP | aGPS to be implemented^[PinePhone docs](/documentation/PinePhone/Modem/#gps_gnss)^; long loading times to get a GPS fix^[Citation]^; No preinstalled application^[Citation]^ | `Sensors` 2+ | WIP |
| "Geo Magnetic Sensor" (`af8133j`): Status unknown (at `/sys/bus/i2c/devices/4-001c/iio:device1`)<br> "Accelerometer / Gyroscope" (`mpu6500`): Working (at `/sys/bus/i2c/devices/4-0068/iio:device2`)<br> "Ambient light / Proximity" (`stk3311`): Working after updating | `Vibration motor` 2+ | Working |  | `Notification LED` 2+ |
| Working |  | `Buttons` 2+ | Working | Power buttons and volume buttons are working. .5+ |
| Accessory compatibility, spare parts | `Keyboard Add-on` 2+ | WIP | The keyboard add-on compatibility is work-in-progress. | `LoRa Add-on` 2+ |
| Not implemented | No software support implemented | `Qi Wireless Charging Add-on` 2+ | WIP | Wireless charging with the add-on case is expected to work to some degree. Certain software functionality and a driver is currently missing^[Citation]^ |
| `Fingerprint Reader Add-on` 2+ | Not implemented | No software support implemented | `Spare parts` 2+ | Partial |
| Some spare parts now available in the store.^[Store](https://pine64.com/product-category/pinephonepro-spare-parts/)^ | Software notes | `Waydroid` 2+ | Working | Waydroid is an Android container used to run Android applications. |

¹ Status of the features at the time of the last factory installation without updates

² Status of the features with an up-to-date reference image
