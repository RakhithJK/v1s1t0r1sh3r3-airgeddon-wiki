In `airgeddon<=8.10`, only `airmon` compatible wireless cards are supported. If your card is unable to change its mode by performing an `airmon` command out of `airgeddon`, it won't work. From `airgeddon>=8.11` any card can be used if the monitor mode is supported but depending of the driver some problems can be found.

__Some known full compatible and fully working chipsets/cards__:

 - Ralink RT3070 <- _present at TP-Link TL-WN7200ND or Alfa AWUS036NH (2.4Ghz - USB)_
 - Ralink RT3572 <- _present at Alfa AWUS052NHS (2.4Ghz/5Ghz - USB)_
 - Ralink RT2770 <- _present at Alfa AWUS051NH (2.4Ghz/5Ghz - USB)_
 - Atheros AR9271 <- _present at TP-Link TL-WN722N or Alfa AWUS036NHA (2.4Ghz - USB)_
 - Realtek RTL8723BE <- _present at Realtek RTL8723BE card (2.4 Ghz - PCIe)_

Of course, there are more compatible and fully working chipsets, these are only some examples.

__Chipsets with known problems__:

 - Realtek RTL8812AU <- _present at Alfa AWUS036ACH (2.4Ghz/5Ghz - USB)_
 - MediaTek MT7610U <- _present at TP-Link Archer T2UH (2.4Ghz/5Ghz - USB)_

These cards are causing problems in order to work with `airmon`. As a consequence there are problems also to work with `airgeddon`. There are some reasons: airmon compatibility and available drivers. There are some closed issues talking about the different problems using them. Some people got it working using the driver package available by apt on some Linux distributions like Kali or Parrot Security (`apt install realtek-rtl88xxau-dkms`), but we can't assure that they will work because it depends of many factors (your kernel, version of the driver package, your firmware, etc). We recommend to don't use these cards.

As far as we know, RTL88xx chipsets have similar behavior so they are not recommended to be used with `airgeddon`. This includes RTL8811AU, RTL8814AU and others similar.
