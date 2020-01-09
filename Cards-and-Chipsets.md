In `airgeddon<=8.10`, only `airmon` compatible wireless cards are supported. If your card is unable to change its mode by performing an `airmon` command out of `airgeddon`, it won't work. From `airgeddon>=8.11` any card can be used if the monitor mode is supported, but depending on the driver, some problems may occur.

__Some known compatible and fully working chipsets/cards__:

 - Atheros AR9271 <- _present in TP-Link TL-WN722N or Alfa AWUS036NHA (2.4Ghz - USB)_
 - Intel Centrino Advanced-N 6205 <- _present integrated in many laptops (2.4Ghz/5Ghz - PCIe)_
 - Ralink RT2770 <- _present in Alfa AWUS051NH (2.4Ghz/5Ghz - USB)_
 - Ralink RT3070 <- _present in TP-Link TL-WN7200ND or Alfa AWUS036NH (2.4Ghz - USB)_
 - Ralink RT3572 <- _present in Alfa AWUS052NHS (2.4Ghz/5Ghz - USB)_
 - Ralink RT5372 <- _present in D-Link DWA-137 (2.4Ghz - USB)_
 - Ralink RT5572 <- _present in Panda PAU09 (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8187 <- _present in Alfa AWUS036H (2.4Ghz - USB)_
 - Realtek RTL8723BE <- _present in Realtek RTL8723BE card (2.4Ghz - PCIe)_

Of course, there are more compatible and fully working chipsets, these are only some examples. Moreover, there are more cards and devices using the chipsets listed here as well. We list only some examples of cards to buy which are using fully compatible working chipsets.

__Chipsets with known problems__:

 - MediaTek MT7610U <- _present in TP-Link Archer T2UH (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8188EU <- _present in TP-Link TL-WN722N (2.4Ghz - USB)_
 - Realtek RTL8812AU <- _present in Alfa AWUS036ACH (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8812BU <- _present in Comfast CF-913AC (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8814AU <- _present in Alfa AWUS1900 (2.4Ghz/5Ghz - USB)_

These cards are causing problems when working with `airmon`. As a consequence there are problems when working with `airgeddon` too. There are some reasons: airmon compatibility and available drivers. There are some closed issues discussing different problems while using them. We recommend to don't use these cards.

__Realtek fix__

One community member worked hard in a solution for Realtek chipset based cards creating a plugin to fix the different behavior of these cards due the drivers. It was already released. Check [Wiki Plugins Hall of Fame Section] for more info. The plugin is valid for airgeddon v10.0 but if you have airgeddon v10.01 the plugin is not needed anymore because the fix was already included in the core code.

[Wiki Plugins Hall of Fame Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20Hall%20of%20Fame
