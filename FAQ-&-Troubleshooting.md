This section is to clarify some common doubts (Frequently Asked Questions) and the typical problems as well (Troubleshooting). Here you can find answers for them. Remember that you can join to our Discord channel clicking on the [Public Invitation link](https://discord.gg/sQ9dgt9) where you can find more help.

____

## Common problems and doubts

#### I am missing some dependencies. What can I do?

You should try to install it. How? It depends of your Linux distribution.

For example, let's suppose that you saw during dependencies check this message:

`dhcpd .... Error (Possible package name : isc-dhcp-server / dhcp-server / dhcp)`

It means that you are missing command/binary `dhcpd` and airgeddon is suggesting that the package you need to install could be named `isc-dhcp-server`, `dhcp-server` or `dhcp`. The name of the package depends on your Linux distribution. Remember that airgeddon is compatible with many of them.

Now let's suppose that you are running Ubuntu Linux. It is a Debian based Linux distribution so you should try first to install it using `apt` tool. For Debian based, the right package name is `isc-dhcp-server`. So, as simple as launching this command to install the dependency: `apt install isc-dhcp-server`.

In addition, if you are running one of these three Linux distributions: `Kali, Parrot-Security, BlackArch`, airgeddon will prompt you to let it try installing the missing dependencies automatically. This is done by a plugin already included in airgeddon. Why only on these three Linux variants is because they are unique containing all the needed packages on their repositories. Is the auto dependency install plugin 100% effective? No, sometimes there could be connectivity problems or maybe the repositories could be down, so airgeddon can't assure you 100% to be able to install always, all the dependencies successfully. Anyway, most of the time, they do get installed automatically.

Here is a repository which will help many people to install missing dependencies manually and it's _ONLY_ for Debian based Linux distributions. It contains all the needed airgeddon dependency deb packages and some of the sub dependencies. They can be easily isntalled using `dpkg -i <file.deb>` in the right order to avoid dependencies problems: https://github.com/v1s1t0r1sh3r3/airgeddon_deb_packages

____

#### My fake AP is not working on any Evil Twin attack. Why?

You should see on fake AP hostapd (xterm upper left) window "AP-ENABLED". If you can see "AP-DISABLED", then something went wrong.

Probably the chipset of your card is not compatible or you have one of the "blacklisted" cards with known problems (mainly Realtek RTL chipsets). Check the list of fully working cards and the cards with known problems [on this link](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Cards%20and%20Chipsets).

Or maybe you just need to reboot. Seems obvious but sometimes, if your card is frozen for some reason, it works.

____

#### DoS (Deauth) is not working. What can I do?

First of all you must be sure about that. Sometimes it is hard to detect that it's not working. The best option is to test DoS on your own network before performing the real audit. Anyway, Denial Of Service is tricky, it is not an exact science.

Not all attacks work against every APs and its clients. Sometimes, clients are taken down only partially, while others remain unaffected even on the same AP. It depends of many factors and variables: Chipset used to perform the attack, type of client (Android, computer, Apple device, etc), Access Point, distance and signal to the target, etc. The signal is of greater significance, which must be powerful enough. If you think it is not working, you should try a different mode of attack: mdk4, aireplay or even mdk3 modifying the configuration options ".airgeddonrc" file. More info about the available options [on this link](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Options).

____

#### Can be the Evil Twin Captive Portal page be customized? How?

Yeah it can be done to perform a more tailored attack over the wireless network you are auditing. There are two ways to do this.

The genetic captive portal page files (html, css and js) are created during the attack in `/tmp/www` dir. You can get that files, perform an offline customization and then when they are ready, launch the attack again and while the attack is running, copy your customized files to that `/tmp/www` location to overwrite the existing ones. The portal will load showing your custom web page.

The second (more elegant) method is to create a plugin to perform this task. You can hook the _set_captive_portal_page_ function overriding the content to create your custom webpage. Just fill the plugin template file (plugin_template.sh) in plugins dir. More info about plugin creation [on this link](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20System).

____

#### Once connected to the Evil Twin fake network, captive portal is not triggered. What am I doing wrong?

Once connected to the fake network, it depends on the type of your device. On mobile devices (Android and Apple iOS) it should be triggered automatically showing a push notification.

Then (for standard computers and mobile devices), opening a browser and trying to open a page should make the captive portal to be opened while you don't try to open a SSL page. If you try to open a page that starts with "https" or if you try a very famous page like Google, Facebook or similar (they are opened using SSL by default even if you don't type https) it will not work and is completely normal. You must try to open "http" pages.

The reason for this behavior is that, to trigger captive portal for SSL pages, a SSL certificate is needed at the portal. And the free self-signed certificates are not an option due to the warning messages they generate when a page using them is visited. The free Let's encrypt 90 days valid SSL certificate is not also an option due the constant need of renewal and the maintenance it needs. So airgeddon staff decided to let it as it is. It's better to have a "page not shown" error than a "insecure page warning" message shown because of a self-signed SSL certificate.

____

#### What is DoS Pursuit Mode exactly?

During a standard Evil Twin attack, your wireless physical card is split into two logical interfaces. One to create the fake Access Point and another to perform the DoS in monitor mode. During the attack, if the target AP is configured in channel "Auto" and if the victim resets it due to lack of connectivity resulting from the DoS attack, once rebooted, it may switch to another channel rendering our attack perform DoS over a wrong channel and the victim re-establish the connectivity.

To avoid the situation explained above, airgeddon implemented the DoS Pursuit Mode. To enable this mode for Evil Twin attacks you'll need an additional (a second one) wireless card that supports monitor mode. The first card will be used as normal and the second one will be used to scan in background looking for the target AP changing channel. If the situation described before happens and the target AP switch its channel, it will be detected by airgeddon and the attack will re-launch the DoS over the new channel alerting us about this. In this way, the target AP is "pursued" even on channel hopping making the Evil Twin a much more effective attack.

____

#### My linux has weird interface names like `wlx00c0ca9208dc` instead of `wlan0` and I'm getting erros. What can I do?

For some Linux distributions like Ubuntu or Debian since some versions, the default naming for network devices is using the new nomenclature which is causing errors while using `airgeddon`. To fix it, follow the instructions [on this link](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Consistent-Network-Device-Naming).

____

#### When I start airgeddon, I see this message "A graphical X window system has not been detected. If you already have one, check it's working properly. It's essential for airgeddon. The script can't continue"

That message is shown when airgeddon is not able to connect to your X Windows System for some reason. Maybe you have a restricted configuration. Try to launch the command `xhost +` before launching airgeddon. That should fix the problem.

Maybe your system is headless (without X Window System), or maybe you just want to not use it. In that case, other option is available. Tmux can be used instead of xterm. It can be set in hidden options `.airgeddonrc` file. More info about it [on this link](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Options).