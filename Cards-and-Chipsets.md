In `airgeddon<=8.10`, only `airmon` compatible wireless cards are supported. If your card is unable to change its mode by performing an `airmon` command out of `airgeddon`, it won't work. From `airgeddon>=8.11` any card can be used if the monitor mode is supported, but depending on the driver, some problems may occur.

__Ordered alphabetically, some known compatible and fully working VIF capable chipsets/cards (Whitelist, recommended)__:

Chipset | Card/s using it | Band/s | Interface | Link/Buy | Additional comments
:-------|:--------------------------------|:------:|:---------:|:-----------:|:-------------------
Atheros AR9271 | Alfa AWUS036NHA / TP-Link TL-WN722N v1 | 2.4Ghz | USB | [Link](https://www.amazon.com/gp/product/B004Y6MIXS/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B004Y6MIXS&linkCode=as2&tag=airgeddon-20&linkId=37cb2a63ac233903fc710e3f45abd136) | 
MediaTek MT7610U | TP-Link Archer T2UH | 2.4Ghz/5Ghz | USB | [Link](https://www.amazon.com/gp/product/B00P115WMY/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B00P115WMY&linkCode=as2&tag=airgeddon-20&linkId=a46b257e7b4bc10735108273e1c856ac) | 
MediaTek MT7612U | Alfa AWUS036ACM | 2.4Ghz/5Ghz | USB | [Link](https://www.amazon.com/gp/product/B08BJS8FXD/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B08BJS8FXD&linkCode=as2&tag=airgeddon-20&linkId=56edb5c5dfe7fe46c71584731ad0c443) | Not recommended for Virtual Machines, only Native Linux. Recommended kernel >= 5.3 . For Rpi 2/3 run this command to get it working ```echo "options mt76_usb disable_usb_sg=1" > /etc/modprobe.d/mt76_usb.conf``` 
Ralink RT2770 | Alfa AWUS051NH | 2.4Ghz/5Ghz | USB | | 
Ralink RT3070 | TP-Link TL-WN7200ND / Alfa AWUS036NH | 2.4Ghz | USB | [Link](https://www.amazon.com/gp/product/B016I6DJ5C/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B016I6DJ5C&linkCode=as2&tag=airgeddon-20&linkId=c9c1d4c0b06ae0b63ac24869203ff59f) | 
Ralink RT3572 | Alfa AWUS052NHS / Linksys AE1000 | 2.4Ghz/5Ghz | USB | [Link](https://www.amazon.com/gp/product/B003B20F5E/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B003B20F5E&linkCode=as2&tag=airgeddon-20&linkId=d79f0804ba9e6bb7cf17da395e846f58) | 
Ralink RT5370 | Some unbranded cheap chinese dongles | 2.4Ghz | USB | [Link](https://www.amazon.com/gp/product/B015TCA2EM/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B015TCA2EM&linkCode=as2&tag=airgeddon-20&linkId=868a98c47f44901f1e8ce025715a7128) | 
Ralink RT5372 | D-Link DWA-137 / Panda PAU06 | 2.4Ghz | USB | [Link](https://www.amazon.com/gp/product/B00JDVRCI0/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B00JDVRCI0&linkCode=as2&tag=airgeddon-20&linkId=8443ac110dc1d471411b8505cd0728bc) | 
Ralink RT5378 | Some unbranded cheap chinese dongles | 2.4Ghz | USB | | 
Ralink RT5572 | Panda PAU07 / Panda PAU09 | 2.4Ghz/5Ghz| USB | [Link](https://www.amazon.com/gp/product/B01LY35HGO/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B01LY35HGO&linkCode=as2&tag=airgeddon-20&linkId=bd3d75a045577ef11ea17ccb3fe2cb2c) | 
Realtek RTL8187 | Alfa AWUS036H / Alfa AWUS036EW | 2.4Ghz | USB | [Link](https://www.amazon.com/gp/product/B003V0I22O/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B003V0I22O&linkCode=as2&tag=airgeddon-20&linkId=d185d31be9bfae4a2b262771a96f050e) | May require patched driver
Realtek RTL8723BE | Realtek RTL8723BE card | 2.4Ghz | PCIe | [Link](https://www.amazon.com/gp/product/B00URB0HEQ/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B00URB0HEQ&linkCode=as2&tag=airgeddon-20&linkId=5530b8ee2a6c6f2aafa8630dbb70a2ad) | 

Of course, there are more compatible and fully working chipsets, these are only some examples. Moreover, there are more cards and devices using the chipsets listed here as well. We list only some examples of cards to buy which are using fully compatible working chipsets.

__Ordered alphabetically, chipsets with known problems (Blacklist, not recommended)__:

 - Intel Centrino Advanced-N 6205 <- _present integrated in many laptops (2.4Ghz/5Ghz - PCIe)_
 - MediaTek MT7601U <- _present in some unbranded cheap chinese dongles (2.4Ghz - USB)_
 - Realtek RTL8188EU/S <- _present in TP-Link TL-WN722N v2/v3 (2.4Ghz - USB)_
 - Realtek RTL8811AU <- _present in some unbranded cheap chinese dongles (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8812AU <- _present in Alfa AWUS036ACH (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8812BU <- _present in Comfast CF-913AC (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8814AU <- _present in Alfa AWUS1900 (2.4Ghz/5Ghz - USB)_
 - Realtek RTL8821CE <- _present in Realtek RTL8821CE card (2.4Ghz/5Ghz - PCIe)_

These cards are causing problems when working with `airmon`. As a consequence there are problems when working with `airgeddon` too. There are some reasons: airmon compatibility and available drivers. There are some closed issues discussing different problems while using them. We recommend to don't use these cards.

__Realtek fix__

One community member worked hard in a solution for Realtek chipset based cards creating a plugin to fix the different behavior of these cards due the drivers. It was already released. Check [Wiki Plugins Hall of Fame Section] for more info. The plugin is valid for `airgeddon=v10.0` but if you have `airgeddon>=10.01` the plugin is not needed anymore because the fix was already included in the core code. Anyway, the plugin fixes the known problems for mode switching but there still are other problems not related to airgeddon that may consist in WPS failure, errors creating fake APs or non effective DoS during Evil Twin attacks. That problems are directly related to the driver and airgeddon can't do anything to deal with that.

Evil Twin attacks can't be performed well due the lack of VIF (Multiple Virtual Interface) support by the driver. For more information about VIF compatibility, check [this](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/FAQ%20&%20Troubleshooting#my-fake-ap-is-not-working-on-any-evil-twin-attack-why). But it is known that there are some working kernel/driver combinations for WPS. Kernel 5.6.x and [aircrack-ng driver](https://github.com/aircrack-ng/rtl8812au) version v5.6.4.2 seems to work. Old 4.x kernel and [aircrack-ng driver](https://github.com/aircrack-ng/rtl8812au) version v5.2.20 was also working for WPS (both combinations tested only on RTL8812AU)

[Wiki Plugins Hall of Fame Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20Hall%20of%20Fame
