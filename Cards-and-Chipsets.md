In `airgeddon<=8.10`, only `airmon` compatible wireless cards are supported. If your card is unable to change its mode by performing an `airmon` command out of `airgeddon`, it won't work. From `airgeddon>=8.11` any card can be used if the monitor mode is supported, but depending on the driver, some problems may occur.

__Some known compatible and fully working chipsets/cards__:

 - Atheros AR9271 <- _present in TP-Link TL-WN722N v1 or Alfa AWUS036NHA (2.4Ghz - USB)_
 - MediaTek MT7612U <- _present in Alfa AWUS036ACM (2.4Ghz/5Ghz - USB) (not recommended to be used on Virtual Machines, but it works very well on native Linux. The recommended Linux kernel version is 5.3 or greater). For Rpi 2/3 run this command to get the card working ```echo "options mt76_usb disable_usb_sg=1" > /etc/modprobe.d/mt76_usb.conf```_
 - Ralink RT2770 <- _present in Alfa AWUS051NH (2.4Ghz/5Ghz - USB)_
 - Ralink RT3070 <- _present in TP-Link TL-WN7200ND or Alfa AWUS036NH (2.4Ghz - USB)_
 - Ralink RT3572 <- _present in Alfa AWUS052NHS (2.4Ghz/5Ghz - USB)_
 - Ralink RT5372 <- _present in D-Link DWA-137 (2.4Ghz - USB)_
 - Ralink RT5572 <- _present in Panda PAU07 or Panda PAU09 (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8187 <- _present in Alfa AWUS036H (2.4Ghz - USB) (may require patched driver)_
 - Realtek RTL8723BE <- _present in Realtek RTL8723BE card (2.4Ghz - PCIe)_

Of course, there are more compatible and fully working chipsets, these are only some examples. Moreover, there are more cards and devices using the chipsets listed here as well. We list only some examples of cards to buy which are using fully compatible working chipsets.

__Chipsets with known problems__:

 - Intel Centrino Advanced-N 6205 <- _present integrated in many laptops (2.4Ghz/5Ghz - PCIe)_
 - MediaTek MT7601U <- _present in some unbranded cheap chinese dongles (2.4Ghz - USB)_
 - MediaTek MT7610U <- _present in TP-Link Archer T2UH (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8188EU/S <- _present in TP-Link TL-WN722N v2 (2.4Ghz - USB)_
 - Realtek RTL8812AU <- _present in Alfa AWUS036ACH (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8812BU <- _present in Comfast CF-913AC (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8814AU <- _present in Alfa AWUS1900 (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8821CE <- _present in Realtek RTL8821CE card (2.4Ghz/5Ghz - PCIe)_

These cards are causing problems when working with `airmon`. As a consequence there are problems when working with `airgeddon` too. There are some reasons: airmon compatibility and available drivers. There are some closed issues discussing different problems while using them. We recommend to don't use these cards.

__Realtek fix__

One community member worked hard in a solution for Realtek chipset based cards creating a plugin to fix the different behavior of these cards due the drivers. It was already released. Check [Wiki Plugins Hall of Fame Section] for more info. The plugin is valid for `airgeddon=v10.0` but if you have `airgeddon>=10.01` the plugin is not needed anymore because the fix was already included in the core code. Anyway, the plugin fixes the known problems for mode switching but there still are other problems not related to airgeddon that may consist in WPS failure, errors creating fake APs or non effective DoS during Evil Twin attacks. That problems are directly related to the driver and airgeddon can't do anything to deal with that.

Evil Twin attacks can't be performed well due the lack of VIF (Multiple Virtual Interface) support by the driver. But it is known that there are some working kernel/driver combinations for WPS. Kernel 5.6.x and [aircrack-ng driver](https://github.com/aircrack-ng/rtl8812au) version v5.6.4.2 seems to work. Old 4.x kernel and [aircrack-ng driver](https://github.com/aircrack-ng/rtl8812au) version v5.2.20 was also working for WPS (both combinations tested only on RTL8812AU)

[Wiki Plugins Hall of Fame Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20Hall%20of%20Fame
