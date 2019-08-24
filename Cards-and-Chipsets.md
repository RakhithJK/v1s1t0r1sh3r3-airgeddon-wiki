In `airgeddon<=8.10`, only `airmon` compatible wireless cards are supported. If your card is unable to change its mode by performing an `airmon` command out of `airgeddon`, it won't work. From `airgeddon>=8.11` any card can be used if the monitor mode is supported but depending of the driver some problems can be found.

__Some known full compatible and fully working chipsets/cards__:

 - Ralink RT3070 <- _present at TP-Link TL-WN7200ND or Alfa AWUS036NH (2.4Ghz)_
 - Ralink RT3572 <- _present at Alfa AWUS052NHS (2.4Ghz/5Ghz)_
 - Atheros AR9271 <- _present at Alfa AWUS036NHA (2.4Ghz)_

Of course, there are more compatible and fully working chipsets, these are only some examples.

__Chipsets with known problems__:

 - Realtek RTL8812AU <- _present at Alfa AWUS036ACH (2.4Ghz/5Ghz)_
 - MediaTek MT7610U <- _present at TP-Link Archer T2UH (2.4Ghz/5Ghz)_

These cards are causing problems in order to work with `airmon`. As a consequence there are problems also to work with `airgeddon`. There are some reasons: airmon compatibility and available drivers. There are some closed issues talking about the different problems using them. Some people got it working using the driver package available by apt on some Linux distributions like Kali or Parrot Security (`apt install realtek-rtl88xxau-dkms`), but we can't assure that they will work because it depends of many factors (your kernel, version of the driver package, your firmware, etc).