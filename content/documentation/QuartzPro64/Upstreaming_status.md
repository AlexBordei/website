---
title: "Upstreaming status"
draft: false
menu:
  docs:
    title:
    parent: "QuartzPro64"
    identifier: "QuartzPro64/Upstreaming_status"
    weight: 2
---

* Upstream Linux kernel DT: https://github.com/torvalds/linux/blob/master/arch/arm64/boot/dts/rockchip/rk3588-quartzpro64.dts
* Upstream U-Boot DT: https://github.com/u-boot/u-boot/blob/master/arch/arm/dts/rk3588-quartzpro64-u-boot.dtsi

| Function 2+ |
| --- | --- | --- | --- | --- |
| Status | Component | Notes | Video Output 2+ | Needs porting |
| `VOP2` | Collabora said they’ll work on this. The video output IP on the RK3588 should mostly be the same as the one on the RK356x, but the chip specific stuff will need to be integrated into the vop2 driver. | Video Input 2+ | Needs porting | `rk_hdmirx` |
| Huge 3600 line driver, but generally seems to be in good condition | 3D Acceleration | Needs writing | Needs writing | `panfrost` |
| Collabora said they’ll work on this. New architecture, reportedly needs many changes to the kernel component of Panfrost. .4+h | Video Decode | Needs writing .4+ | GStreamer only, no ffmpeg^[Source](https://patchwork.ffmpeg.org/project/ffmpeg/list/?series=2898)^ | `hantro` using `v4l2-requests` |
| VDPU121 handling 1080p60 H.263/MPEG-4, MPEG-1 and MPEG-2 | Needs writing | `rkvdec2` using `v4l2-requests` | Nobody is known to be working on this for now. VDPU346 handling 8K60 H.265, H.264, VP9 and AVS | Needs writing |
| `rkdjpeg` using `v4l2-requests` | User:CounterPillow is doing a little work on this. VDPU720 handling JPEG | In review^[Source](https://patchwork.kernel.org/project/linux-rockchip/list/?series=721724)^ | `hantro` using `v4l2-requests` | Collabora is working on this. VDPU981 handling 4K60 AV1 .3+h |
| Video Encode | Needs writing | GStreamer only | JPEG on VEPU121 | Driver already exists, only minor changes needed. |
| Needs writing | ? | H.264 on VEPU580 |  | Needs writing |
| ? | H.265 on VEPU580 | .2+h | Audio 2+ | Linux Mainline |
| `rockchip-i2s-tdm` | As of 6.2^[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=c619bd4268ff9895760dab303b4eb15ed3d0f7e9)^ 2+ | Linux Mainline | `es8388` CODEC |  |
| CRU 2+ | Linux Mainline | `clk-rk3588` | As of 6.2^[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=f1c506d152ff235ad621d3c25d061cb16da67214)^ | MMC 2+ |
| Linux Mainline | `sdhci-of-dwcmshc` | As of 5.19^[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=bbbd8872825310b14bc6e04250d2cb5edcd55edb)^ | pinctrl 2+ | Linux Mainline |
| `pinctrl-rockchip` | As of 5.19^[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=fdc33eba11c5919199f3d13dc53571cc7bf19d7d)^ | GPIO 2+ | Linux Mainline | `rockchip-gpio` |
| As of 6.1^[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=cc165ba48aaf7d792e99d0c7e4b12e9625bc73e3)^ | I^2^C 2+ | Linux Mainline | `rk3x-i2c` | Should be the same as RK3399, just needs devicetree work |
| SPI 2+ | Linux Mainline | `rockchip-spi` | Should be the same as previous SoCs, just needs devicetree work | PMU 2+ |
| In review^[Source](https://patchwork.kernel.org/project/linux-rockchip/list/?series=687286)^ | `rk806` | Talks over SPI | Regulators 2+ | Needs porting |
| `rk860` | Talks over I^2^C | GMAC 2+ | Linux Mainline | `dwmac-rk` |
| As of 6.1^[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=2f2b60a0ec2826e5a2b2a1ddf68994a868dccbc1)^ | Power Domains 2+ | Linux Mainline | `rockchip-pm-domain` | As of 6.1^[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=6541b424ce1dda616d3946e839f015c984df7a99)^ |
| CAN 2+ | Needs porting | `rockchip_canfd` | Not broken out on the QuartzPro64, so we probably won’t be the ones porting it | SPDIF TX 2+ |
| May need porting | `rockchip-spdif` | Genuinely just needs the compatible string added, I think, otherwise we’re all good. Not broken out on QuartzPro64 dev board | SPDIF RX 2+ | Needs porting |
| `rockchip-spdifrx` | Not broken out on QuartzPro64 dev board | PCIe 2+ | May need porting | `rockchip-dw-pcie` |
| Downstream driver and upstream are quite different, look into how much work actually needs doing. Seems to be the same controller as rk3568 so maybe none? | NPU | Needs porting/writing | ? | `rockchip-rknpu` |
|  | USB 2.0 2+ | In review^[Source](https://patchwork.kernel.org/project/linux-rockchip/list/?series=749871)^ | `phy-rockchip-inno-usb2` | Might have more factors than just the PHY |
| USB 3.0 2+ | ? | `?` |  | SATA 2+ |
| Linux Mainline | `ahci-dwc` | Just needs the compatible added to the bindings, done [here](https://patchwork.kernel.org/project/linux-rockchip/list/?series=749876) | Thermal 2+ | In review^[Source](https://patchwork.kernel.org/project/linux-rockchip/list/?series=687619)^ |
| `rockchip-thermal` |  | Wifi & Bluetooth 2+ | ? | `?` |
|  | HWRNG 2+ | Needs porting | `rockchip-rng` | The code & DT work is easy to port & working |
| RTC 2+ | Linux Mainline | `hym8563` | Should only need DT work (see [here](https://patchwork.kernel.org/project/linux-rockchip/list/?series=736799) for an example) | OTP 2+ |
| In review^[Source](https://patchwork.kernel.org/project/linux-rockchip/list/?series=744118)^ | `rockchip-otp`	 |  | SARADC 2+ | In review^[Source](https://patchwork.kernel.org/project/linux-rockchip/list/?series=748188)^ |
