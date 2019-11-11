In `airgeddon<=8.10`, only `airmon` compatible wireless cards are supported. If your card is unable to change its mode by performing an `airmon` command out of `airgeddon`, it won't work. From `airgeddon>=8.11` any card can be used if the monitor mode is supported, but depending on the driver, some problems may occur.

__Some known compatible and fully working chipsets/cards__:

 - Atheros AR9271 <- _present in TP-Link TL-WN722N or Alfa AWUS036NHA (2.4Ghz - USB)_
 - Ralink RT2770 <- _present in Alfa AWUS051NH (2.4Ghz/5Ghz - USB)_
 - Ralink RT3070 <- _present in TP-Link TL-WN7200ND or Alfa AWUS036NH (2.4Ghz - USB)_
 - Ralink RT3572 <- _present in Alfa AWUS052NHS (2.4Ghz/5Ghz - USB)_
 - Ralink RT5372 <- _present in D-Link DWA-137 (2.4Ghz - USB)_
 - Ralink RT5572 <- _present in Panda PAU09 (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8723BE <- _present in Realtek RTL8723BE card (2.4 Ghz - PCIe)_

Of course, there are more compatible and fully working chipsets, these are only some examples. Moreover, there are more cards and devices using the chipsets listed here as well. We list only some examples of cards to buy which are using fully compatible working chipsets.

__Chipsets with known problems__:

 - MediaTek MT7610U <- _present in TP-Link Archer T2UH (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8812AU <- _present in Alfa AWUS036ACH (2.4Ghz/5Ghz - USB)_

These cards are causing problems when working with `airmon`. As a consequence there are problems when working with `airgeddon` too. There are some reasons: airmon compatibility and available drivers. There are some closed issues discussing different problems while using them. Some people got it working using the driver package available by apt on some Linux distributions like Kali or Parrot Security (`apt install realtek-rtl88xxau-dkms`), but we can't assure that they will work because it depends on many factors (your kernel, version of the driver package, your firmware, etc). We recommend not to use these cards.

As far as we know, RTL88xx chipsets have similar behavior so they are not recommended to be used with `airgeddon`. This includes RTL8811AU, RTL8814AU and other similar.

__Realtek fix__

One community member is working in a solution for Realtek chipset based cards creating a plugin. It is still under development but it will be released soon. Check [Wiki Plugins Hall of Fame Section] for more info.

[Wiki Plugins Hall of Fame Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20Hall%20of%20Fame
