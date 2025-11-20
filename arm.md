## Current UEFI Arm products on the market:
- Thinkpad x13s: https://fedoraproject.org/wiki/Thinkpad_X13s (first arm thinkpad, good Linux support, $300 on ebay)
- Surface laptop: https://www.microsoft.com/en-us/store/b/buy-surface-laptop (not good Linux support [yet](https://github.com/linux-surface/linux-surface/issues/1590))
- Thinkpad T14s Gen 6 Snapdragon: https://www.lenovo.com/us/en/p/laptops/thinkpad/thinkpadt/lenovo-thinkpad-t14s-gen-6-14-inch-snapdragon/len101t0099 (extremely expensive)
- Dell Inspiron: https://a.co/d/cPkW4Aj https://www.xda-developers.com/dell-inspiron-14-530-deal/ (cheapest, $611)
- System76: https://www.jeffgeerling.com/blog/2025/system76-built-fastest-windows-arm-pc (Ampere)
- Orion O6: https://radxa.com/products/orion/o6/
- Steam Frame https://store.steampowered.com/sale/steamframe (?)

# Not UEFI
- Rockchip RK3688: https://www.cnx-software.com/2025/07/18/rockchip-unveils-rk3668-10-core-arm-cortex-a730-cortex-a530-soc-with-16-tops-npu-rk182x-llm-vlm-co-processor/
- Raspi 5 laptop: https://www.kickstarter.com/projects/argonforty/upton-one-the-true-raspberry-pi-compute-module-5-laptop

---
# Technical Details

## Ampere
- Brief datasheet: https://amperecomputing.com/briefs/ampereone-m-product-brief
- Ampere has upstreamed UEFI support: https://github.com/tianocore/edk2-platforms/tree/master/Platform/Ampere
- ACPI only (?)
## Cix (Radxa Orion O6)
- Cix Sky1 device tree: https://gitlab.com/cix-linux/cix_opensource/linux/-/blob/874c4/bbdf2/cix_beta2_radxa_dev/arch/arm64/boot/dts/cix/sky1.dtsi
- Orion O6 device tree: https://gitlab.com/cix-linux/cix_opensource/linux/-/blob/874c4/bbdf2/cix_beta2_radxa_dev/arch/arm64/boot/dts/cix/sky1-orion-o6.dts
- Implements `gic700`, USB controller is `cix,sky1-usbssp`
- Radxa/Cix have done a poor job getting drivers upstreamed
## Snapdragon 8cx
- 8cx device tree: https://github.com/torvalds/linux/blob/master/arch/arm64/boot/dts/qcom/sc8280xp.dtsi
- ~1520 geekbench single core score
- Ubuntu works out of the box on thinkpad x13s (suspend and webcam don't work)
## Snapdragon X Elite
- x1e80100 device tree: https://github.com/torvalds/linux/blob/master/arch/arm64/boot/dts/qcom/x1e80100.dtsi
- USB controller is `snps,dwc3`, touchpad/keyboard is `hid-over-i2c`
- Microsoft, Lenovo, Dell, Samsung, Asus, HP, Acer
- ~2823 geenbench single core score
- Linux support not working well yet (trackpad is broken)
- TRM available if you sign your rights away
## RK3588
- Cheapest ($20)
- 739 geekbench single core
- ArmV8, Cortex-A76
- Used by Radxa, CoolPi, OrangePi, TuringPi, WayPonDev, FriendlyElec
- Rockchip does a bad job upstreaming drivers
- SBC vendors require custom kernels and blobs in order to run a desktop
- Rockchip SBCs are released as open-source products but community is forced to do the heavy lifting
- Will eventually be replaced by RK3688 (ArmV9.3, Cortex-A730)
- IP is complicated (maybe overcomplicated)
## NXP iMX
- TRMs are available but you need to create an account
## Allwinner
- Starting to become more open-source: https://www.cnx-software.com/2025/07/07/allwinner-a527-t527-and-a733-datasheets-user-manuals-and-linux-sdk-released/

Last updated: Nov 2025
