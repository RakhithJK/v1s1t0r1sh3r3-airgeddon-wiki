In `airgeddon<=8.10`, only `airmon` compatible wireless cards are supported. If your card is unable to change its mode by performing an `airmon` command out of `airgeddon`, it won't work. From `airgeddon>=8.11` any card can be used if the monitor mode is supported, but depending on the driver, some problems may occur.

_Rating legend_: --- Best --- :heart_eyes: :smile: :relaxed: :neutral_face: :disappointed: --- Worst ---

## Whitelist

__Ordered by users' rating, some known compatible and fully working VIF capable chipsets/cards (Whitelist, recommended)__:

Users' rating | Gen | Chipset | Card/s using it | Band/s | Interface | Link / Buy | Additional comments
:-------------|:----|:--------|:----------------|:------:|:---------:|:--------:|:-------------------
:heart_eyes: | Wifi6e | Mediatek MT7921AUN | Alfa AWUS036AXML | 2.4Ghz / 5Ghz / 6Ghz | USB | [Link](https://amzn.to/3tAFmOz) | Includes bluetooth chipset. Not working on Parrot OS (vm or native) |
:heart_eyes: | Wifi6e | Mediatek MT7921AUN | Alfa AWUS036AXM | 2.4Ghz / 5Ghz / 6Ghz | USB | [Link](https://amzn.to/3MaWW27) | Not working on Parrot OS (vm or native) |
:heart_eyes: | Wifi5 | MediaTek MT7612U | Alfa AWUS036ACM | 2.4Ghz / 5Ghz | USB | [Link](https://amzn.to/3P4wc35) | Not recommended for Virtual Machines if your host is Windows, only Native Linux or Linux VM at Linux host. Recommended kernel >= 5.3 . For Rpi 2/3 run this command to get it working ```echo "options mt76_usb disable_usb_sg=1" > /etc/modprobe.d/mt76_usb.conf``` |
:heart_eyes: | Wifi5 | Ralink RT5572 | Panda PAU07 / Panda PAU09 | 2.4Ghz / 5Ghz| USB | [Link](https://amzn.to/3IYOWgM) |
:smile: | Wifi4 | Atheros AR9271 | Alfa AWUS036NHA / TP-Link TL-WN722N v1 | 2.4Ghz | USB | [Link](https://amzn.to/3sRWE6L) | Works like a charm, but is old stuff |
:smile: | Wifi4 | Ralink RT5370 | Panda PAU04 | 2.4Ghz | USB | [Link](https://amzn.to/3MV7fGf) | Works like a charm, but is old stuff |
:smile: | Wifi4 | Ralink RT5372 | D-Link DWA-137 / Panda PAU06 | 2.4Ghz | USB | [Link](https://amzn.to/3HYJBF0) | Works like a charm, but is old stuff |
:relaxed: | Wifi4 | MediaTek MT7610U | Alfa AWUS036ACHM / TP-Link Archer T2UH | 2.4Ghz / 5Ghz | USB | [Link](https://amzn.to/44tBPic) |
:relaxed: | Wifi4 | Ralink RT3572 | Alfa AWUS052NHS / Linksys AE1000 | 2.4Ghz / 5Ghz | USB | [Link](https://amzn.to/3vRLwc6) | 
:relaxed: | Wifi4 | Ralink RT3070 | TP-Link TL-WN7200ND / Alfa AWUS036NH | 2.4Ghz | USB | [Link](https://amzn.to/3pyO9ii) | 
:neutral_face: | Wifi4 | Ralink RT2770 | Alfa AWUS051NH | 2.4Ghz / 5Ghz | USB | [Link](https://amzn.to/3tBq5JA) | 
:neutral_face: | Wifi5 | Intel L716NA02 | Intel Wireless-AC 9560 card | 2.4Ghz / 5Ghz | PCIe | [Link](https://amzn.to/3iBPb62) |
:neutral_face: | Wifi4 | Realtek RTL8723BE | Realtek RTL8723BE card | 2.4Ghz | PCIe | [Link](https://amzn.to/3JHgNof) | 

Of course, there are more compatible and fully working chipsets, these are only some examples. Moreover, there are more cards and devices using the chipsets listed here as well. We list only some examples of cards to buy which are using fully working VIF (Multiple Virtual Interface) capable chipsets.

## Greylist

__Ordered alphabetically, VIF capable chipsets but they are giving some problems and depending on driver and kernel can work. They require patched drivers (Greylist, not recommended)__:

 - Atheros AR9170 <- _present in TP-Link TL-WN822N v1 (2.4Ghz - USB)_
 - Intel AX201 <- _present integrated in many laptops (2.4Ghz / 5Ghz - PCIe)_
 - Realtek RTL8187 <- _present in Alfa AWUS036H / Alfa AWUS036EW (2.4Ghz - USB)_
 - Realtek RTL8821CE <- _present in Realtek RTL8821CE card (2.4Ghz / 5Ghz - PCIe)_
 - Realtek RTL8822CE <- _present in Realtek RTL8822CE card (2.4Ghz / 5Ghz - PCIe)_

## Blacklist

__Ordered alphabetically, chipsets with known problems or non-VIF capable chipsets/cards (Blacklist, not recommended at all)__:

 - Intel Centrino Advanced-N 6205 <- _present integrated in many laptops (2.4Ghz / 5Ghz - PCIe)_
 - MediaTek MT7601U <- _present in some unbranded cheap chinese dongles (2.4Ghz - USB)_
 - MediaTek MT7921 <- _present integrated in many laptops (2.4Ghz / 5Ghz - PCIe)_
 - Realtek RTL8188EU/S <- _present in TP-Link TL-WN722N v2/v3 / Alfa AWUS036NHV (2.4Ghz - USB)_
 - Realtek RTL8811AU <- _present in some unbranded cheap chinese dongles (2.4Ghz / 5Ghz - USB)_
 - Realtek RTL8812AU <- _present in Alfa AWUS036ACH (2.4Ghz / 5Ghz - USB)_
 - Realtek RTL8812BU <- _present in Comfast CF-913AC (2.4Ghz / 5Ghz - USB)_
 - Realtek RTL8814AU <- _present in TP-LINK Archer T9UH / Alfa AWUS1900 (2.4Ghz / 5Ghz - USB)_

These chipsets/cards are causing problems when working with `airmon`. As a consequence there are problems when working with `airgeddon` too. There are some reasons: airmon compatibility and available drivers. There are some closed issues discussing different problems while using them. We recommend to don't use these cards.

__Realtek partial fix__

One community member worked hard in a solution for Realtek chipset based cards creating a plugin to fix the different behavior of these cards due the drivers. It was already released. Check [Wiki Plugins Hall of Fame Section] for more info. The plugin is valid for `airgeddon=v10.0` but if you have `airgeddon>=10.01` the plugin is not needed anymore because the fix was already included in the core code. Anyway, the plugin fixes the known problems for mode switching but there still are other problems not related to airgeddon that may consist in WPS failure, errors creating fake APs or non effective DoS during Evil Twin attacks due to lack of VIF capability. That problems are directly related to the hardware or the driver and airgeddon can't do anything to deal with that.

[Wiki Plugins Hall of Fame Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20Hall%20of%20Fame
