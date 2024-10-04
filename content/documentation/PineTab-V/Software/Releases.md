---
title: "Releases"
draft: false
menu:
  docs:
    title:
    parent: "PineTab-V/Software"
    identifier: "PineTab-V/Software/Releases"
    weight: 2
---

This page contains a list of all available releases and tools for the PineTab-V in alphabetical order. 

## Factory releases ==

The PineTab-V ships with _Factory Test Code_. The factory test reference source code can be found here:

* [PineTab-V_factorytestcode_SDK-20230725.tar.gz](https://files.pine64.org/SDK/PineTab-V/PineTab-V_factorytestcode_SDK-20230725.tar.gz) from _pine64.org_ (8.36GB, MD5 of the TAR-GZip file: _3e35e2760d82155b024f7601ac2b1275_)

Community releases:

* [sdcard.img](https://pine64.my-ho.st:8443/pinetabv/factoryimage/) pre-built image from the community member Fishwaldo derived from the factory SDK. Note: Use _dd_ to write it to microSD card or the eMMC.

## Linux ==

### Gentoo

A Gentoo overlay is available [here](https://gitlab.com/bingch/gentoo-overlay), it shares most ebuilds for [StarFive VisionFive 2](https://wiki.gentoo.org/wiki/Embedded_Handbook/Boards/StarFive_VisionFive_2) except the kernel source ebuild contains patches from the above factory SDK.

### KDE Plasma Yocto

A KDE Plasma Yocto Image from the community member Fishwaldo. Based on the Star64 images developed [here](https://github.com/Fishwaldo/meta-pine64). Please see this [issue](https://github.com/Fishwaldo/meta-pine64/issues/12) for known problems.

#### Download

* https://github.com/Fishwaldo/meta-pine64/releases/

| Default credentials |
| --- |
| Root |
| `root`/`pine64` |
| Default user |
| `pine64`/`pine64` |

#### Notes
* Use _dd_ or _Balena Etcher_ to copy to a microSD card and then insert the microSD card into your PineTab-V and boot