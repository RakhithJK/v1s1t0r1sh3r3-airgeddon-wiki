This section is to help clarify some common doubts and problems (Frequently Asked Questions) along with some common troubleshooting steps. Remember that you can also join our **Discord server** by clicking on the public invitation link [here](https://discord.gg/sQ9dgt9) to find and receive more help not answered here.

____

## Common problems and doubts

#### I am missing some dependencies. What can I do?

You should try installing it. How? It depends on your Linux distribution.

For example, let's suppose that you saw during dependencies check this message:

`dhcpd .... Error (Possible package name: isc-dhcp-server / dhcp-server / dhcp)`

It means you are missing the command/binary `dhcpd` and `airgeddon` suggested the package you need to install could be named `isc-dhcp-server`, `dhcp-server`, or `dhcp`. The name of the package depends on your Linux distribution. Remember that `airgeddon` is compatible with many of them. See the list of supported and tested Linux distros [here](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Compatibility).  

Now let's suppose that you are running Ubuntu Linux. It is a Debian-based Linux distribution, so you should try installing it using the `apt` command. For Debian based, the correct package name is `isc-dhcp-server`. So, it's as simple as launching this command to install the dependency: `sudo apt install isc-dhcp-server`.

In addition, if you are running one of these three Linux distributions: `Kali, Parrot-Security, BlackArch`, `airgeddon` will prompt you to allow it to try installing the missing dependencies automatically. This is done by a plugin included in `airgeddon`. Why only on these three Linux variants? It's because they are unique and contain all the needed packages in their repositories out of the box. Is the auto dependency install plugin 100% effective? No, there could be connectivity problems, or repositories could be down. So `airgeddon` can't assure you a 100% installation on the dependencies. Anyway, most of the time, they do get installed automatically.

Here is a repository that will help many people to install missing dependencies manually, and it's _ONLY_ for Debian-based Linux distributions. It contains all the needed `airgeddon` dependencies in a .deb package and some sub-dependencies. They can easily be installed using `sudo dpkg -i <file.deb>` in the right order to avoid dependencies problems: https://github.com/v1s1t0r1sh3r3/airgeddon_deb_packages

____

#### What is VIF?

VIF (Virtual Interface) is the ability to split one physical card into 2 logical cards. This is used during the Evil Twin attack to keep one acting as an AP and the other performing DoS in monitor mode. From `airgeddon>=10.42` there is an integrated check for this before launching any Evil Twin attack. 

To check manually if your card is supporting VIF, launch this command `sudo iw list | grep "Supported interface modes" -A 8` (this command is case sensitive and typed wrong will result in the wrong output or none at all) and you should see in the output AP/VLAN (just AP is not enough), otherwise, your card is not supporting the required VIF. 

Usually, Realtek (RTL) chipsets are non-VIF capable and not recommended for wireless hacking. Don't confuse them with Ralink chipsets (RT), these last are usually VIF capable and recommended. Check the list of fully working VIF capable chipsets/cards [here](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Cards-and-Chipsets).

If you have more than one wifi card and neither support VIF and or are a blacklisted card or chipset but at least one supports AP mode and both support monitor mode you can try using this [plugin](https://github.com/xpz3/airgeddonplugins/blob/main/multint.sh) to use 2 cards in `airgeddon` instead of one VIF capable card. One for the fake AP and one to perform DoS. Information on using plugins can be found [here](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20System).

____

#### My fake AP is not working on any Evil Twin attack. Why?

You should see on the fake AP hostapd (xterm upper left) window "AP-ENABLED". If you can see "AP-DISABLED", then something went wrong.

Your wifi chipset probably is not compatible or you have one of the "blacklisted" cards with known problems (mainly Realtek RTL chipsets). To perform an Evil Twin attack, VIF (Virtual Interface) and AP mode features are required on your wifi chipset. Not all wifi chipsets support these modes. You can check what VIF is and how to check if your card is supporting it [here](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/FAQ%20&%20Troubleshooting#what-is-vif).

If your card is supporting VIF and AP mode and it is still not working for you, maybe it has become buggy and you need to unplug the card and then plug it in again, or maybe you just need to reboot your whole computer. Seems obvious, but sometimes, if your card becomes frozen for some reason, it works.

____

#### DoS (Deauth) is not working. What can I do?

First of all, you must be sure about that. Sometimes it is hard to detect that it's not working. The best option is to test DoS on your own network before performing the real assessment. Anyway, Denial Of Service is tricky, it is not an exact science.

If the target network is using pure WPA3 encryption (SAE), deauth attacks will not work. WPA3 includes by default 802.11w (PMF, Protected Management Frames). You can find also 802.11w protections against deauth on WPA2 but that kind of protections on WPA2 are very uncommon unless you are on a corporate environment (devices supporting this are usually expensive).

Regarding WPA/WPA2, not all attacks work against every APs and its clients. Sometimes, clients are taken down only partially, while others remain unaffected even on the same Access Point. It depends on many factors and variables: Chipset used to perform the attack, type of client (Android, computer, Apple device, etc), Access Point, distance and signal to the target, etc. The signal strength is of greater significance, which must be powerful enough. If you think it is not working, you should try a different DoS attack: mdk4, aireplay, or even mdk3 which can be set instead of mdk4 modifying the configuration options. More info about the available options can be found [here](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Options).

If your DoS is not effective only during Evil Twin attacks and using one wifi adapter, this probably is because your wifi chipset does not support VIF (Virtual Interface). This can also happen if you have a "blacklisted" card with known problems (mainly Realtek RTL chipsets). A list of supported and also blacklisted cards can be found [here](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Cards%20and%20Chipsets). To properly perform an Evil Twin attack with one wifi adapter, a wifi chipset supporting VIF mode is needed. Not all wifi chipsets support this. For more information about what VIF is, check this [link](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/FAQ%20&%20Troubleshooting#what-is-vif). From `airgeddon>=10.42` there is an integrated check for this before launching any Evil Twin attack.

If your wifi chipset supports VIF and it is still not working for you and is not a blacklisted chipset, maybe it is buggy and you need to unplug the card and then plug it in again, or maybe you just need to reboot your whole computer. Seems obvious but sometimes, if your card is frozen for some reason, it works.

If your problem happens only over 5Ghz networks, maybe it's because your reg domain is not properly set. From `airgeddon>=11.11` there is an integrated check for this before launching any Evil Twin attack. Use the command `iw reg get` to check what is configured, and `iw reg set XX` to set it where XX is your country code. Example: for Spain, the command should be `iw reg set ES`. After setting it, check again using `iw reg get` and if is set correctly, then try again to deauth on your 5Ghz target network. Bear in mind that even with the country code set, the 5Ghz band has several channels that may not be available for operation due to country restrictions (DFS channels). If the target network uses one of these channels, the attack may not be successful.

____

#### Can the Evil Twin Captive Portal page be customized? If so how?

`airgeddon` is using by default a neutral and "less suspicious as possible" captive portal, and from `airgeddon>=11.20` there is also the possibility to use the advanced captive portal which will change color of the portal (but using always the same colour for a target) and showing also a vendor logo based on target AP's BSSID. Anyway, yes, the captive portal page can be customized which can help with tailored attacks. There are two ways to do this.

The generic captive portal page files (HTML, CSS, and JS) are created during the attack in the `/tmp/www` dir. You can get that files during an attack, perform offline customization and then when they are ready, launch the attack again and while the attack is running, copy your customized files to that `/tmp/www` location to overwrite the existing ones. The portal will load showing your custom web page. Of course you need to know what you are doing, some basic knowledge about HTML, CSS and JS is needed.

The second (more elegant) method is to create a plugin to perform this task. You can hook the _set_captive_portal_page_ function overriding the content to create your custom webpage. Just fill the plugin template file (plugin_template.sh) in the plugins dir. More info about plugins creation and creating custom captive portals can be found [here](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20System), [here](https://github.com/KeyofBlueS/airgeddon-plugins/blob/master/custom_portals.sh) and [here](https://github.com/KeyofBlueS/airgeddon-plugins/issues/15).

____

#### Once connected to the fake AP created by an Evil Twin attack the captive portal is not automatically triggered or asked for. What am I doing wrong?

Once connected to the fake network, most devices and operating systems (Windows, Mac, iOS, Linux, and Android) should automatically populate the captive portal or prompt that a login to the AP is needed. But there can be varying factors (OS version and manufacture) why some will not, which may be beyond the control of `airgeddon`.

For devices and operating systems that do not automatically open or ask for the captive portal one may need to open a browser to a non https:// (eg. http://example.com) page. Going to an https:// page (google.com, facebook.com, etc...) will not work and is normal because they are https:// by default and do not support http://.

The reason for this behaviour is that to trigger a captive portal for SSL/TLS (https://) pages, an SSL/TLS certificate is needed at the portal. And the free self-signed certificates are not an option due to the warning messages they generate when a page using them is visited making the captive portal untrusted. The free Let's Encrypt 90 days valid SSL/TLS certificate is also not an option due to the constant need for renewal and the maintenance required. So `airgeddon` staff decided to let it as it is. It's better to have a "page not shown" error than an "insecure page warning" message shown because of a self-signed SSL/TLS certificate.

____

#### What is DoS Pursuit Mode exactly?

During a standard Evil Twin attack, your wireless VIF capable card is split into two logical interfaces. One to create the fake Access Point and another to perform the DoS in monitor mode. During the attack, if the target AP is configured in channel "Auto" and if the victim resets/reboots it due to lack of connectivity resulting from the Denial of Service (DoS) attack, once reset/rebooted, it may switch to another channel rendering our attack performing DoS over the wrong channel and the victim re-establish the connectivity.

To avoid the above situation, `airgeddon` implemented DoS Pursuit Mode. To enable this mode in Evil Twin attacks you'll need an additional (second) wireless card that supports monitor mode. The first card will be used as normal (DoS and fake AP) and it needs to be VIF capable. For more information about what VIF is, check [here](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/FAQ%20&%20Troubleshooting#what-is-vif). The second one (no need to be VIF capable) will be used to scan in the background and check if the target AP changed the channel it's on. If the situation described before happens and the target AP switches its channel, it will be detected by `airgeddon`, and the attack will re-launch the DoS and the fake AP over the new channel alerting us about this. In this way, the target AP is "pursued" even on channel hopping making the Evil Twin a much more effective attack. DoS Pursuit Mode is also available in the DoS attack menu. 

____

#### My Linux has a weird wireless interface name like `wlx00c0ca9208dc` instead of `wlan0`, and I'm getting errors. What can I do?

For some Linux distributions like Ubuntu, Parrot OS, and Debian, the default naming for network devices uses the new nomenclature. This can cause errors while using `airgeddon` because some third-party tools that `airgeddon` uses aren't compatible with this wireless device name nomenclature. 

It's better to use the old wifi interface naming that is fully compatible with all the dependencies in `airgeddon`. From `airgeddon>=11.20` there is an integrated check showing a warning and the recommendation for the change upon interface selection. Information on this can be found [here](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Consistent-Network-Device-Naming).

____

#### When I start airgeddon, I see this message "No graphics system was detected"

This message appears when `airgeddon` can't connect to your X Windows System for whatever reason. Maybe you have a restricted configuration. From `airgeddon>=11.11` the message is self-explanatory. The tool will detect if there is an existing graphics system (X windows or Wayland) and it will suggest a command to be executed before launching `airgeddon`.

Try; launching the command `xhost +` before launching `airgeddon` if you have an X Windows system. Try; to launch the command `xhost +SI:localuser:root` before launching `airgeddon` if you have Wayland graphics. That should fix the problem. More details are available here: [Wayland section at wiki](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Wayland).

Maybe your system is headless (without a graphical system), or maybe you just want not to use it. In that case, other options are available. Tmux can be used instead of xterm. It can be set in the hidden `.airgeddonrc` file. More info about it [here](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Options).

____

#### When I scan for wireless networks, no networks are found

This can happen to anybody due to a frozen wireless adapter and is usually solved by unplugging and replugging your USB wireless card. Sometimes could mean that the chipset of your adapter is not a good one. But it can also happen for well working and compatible chipsets under special circumstances: the most probable scenario where this is happening while using a working and compatible chipset is when you are using `airgeddon` inside a VM (Virtual Machine) and typically this happens in VirtualBox for some adapters (typically some Ralink RTxxxx chipsets).

Quick (and painful) fixes:
 - Use native Linux
 - Use VMware

This problem does not usually occur in VMWare or using native Linux running on hardware, not in a VM.

Another workaround would be to try changing the USB speed. Either plug your USB wifi card into a different USB port (from 2.0 to 3.0, or to 1.1 or vice versa if available) or change the USB speed settings within your VM (from 2.0 to 3.0 or vice versa). It's also recommended to power off the VM to do these changes. If using VirtualBox, its also recommended to install the Extension Pack from [here](https://www.virtualbox.org/wiki/Downloads).

____

#### When I use a non-latin-chars language like chinese, I see odd chars on xterm windows

This happens due to your xterm configuration. It has a very easy fix. Edit `/etc/X11/app-defaults/XTerm` file and add this line to the end of the file:

```
xterm*faceName: DejaVu Sans Mono:antialias=True:pixelsize=10
```
