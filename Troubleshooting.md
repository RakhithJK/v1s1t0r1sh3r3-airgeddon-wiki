## Section still under construction

This section is to clarify the typical problems and some common doubts as well. Here you can find answers for them. Remember that you can join to our Discord channel clicking on the [Public Invitation link](https://discord.gg/sQ9dgt9).

____

## Common problems and doubts

#### My fake AP is not working on any Evil Twin attack. Why?

You should see on fake AP hostapd (xterm upper left) window "AP-ENABLED". If you can see "AP-DISABLED", then something went wrong.

Probably the chipset of your card is not compatible or you have one of the "blacklisted" cards with known problems (mainly Realtek RTL chipsets). Check the list of fully working cards and the cards with known problems [on this link](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Cards%20and%20Chipsets).

#### DoS is not working, what can I do?

#### Can be the Evil Twin Captive Portal page be customized? how?

Yeah it can be done to perform a more tailored attack over the wireless network you are auditing. There are two ways to do this.

The captive portal page files (html, css and js) are created during the attack in `/tmp/www` dir. You can get that files, perform an offline customization and then when they are ready, launch the attack again and while the attack is running, copy your customized files to that `/tmp/www` location to overwrite the existing ones. The portal will look with your custom web page.

The second (more elegant) method is to create a plugin to perform this task. You can hook the _set_captive_portal_page_ function overriding the content to create your custom webpage. Just fill the plugin template file (plugin_template.sh) in plugins dir. More info about plugin creation [on this link](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20System).

#### What is DoS Pursuit Mode exactly?

During a standard Evil Twin attack, your wireless physical card is splitted into two logical interfaces. One to create the fake Access Point and another to perform the DoS in monitor mode. During the attack, if the target AP is configured in channel "Auto" and the victim reset it due the lack of connectivity because of the DoS attack, once rebooted, it may switch to another channel letting our attack performing DoS over a wrong channel and the victim will recover the connectivity.

To avoid the situation explained before, airgeddon implemented the DoS Pursuit Mode. To enable this mode for Evil Twin attacks you'll need an additional (a second one) compatible to monitor mode wireless card. The first card will be used as normal and the second one will be used to scan in background looking for the target AP. If the situation described before happens and the target AP switch its channel, it will be detected by airgeddon and it will re-launch the DoS over the new channel alerting us about this. In this way, the target AP is "pursued" even on channel hopping making the Evil Twin a much more effective attack.