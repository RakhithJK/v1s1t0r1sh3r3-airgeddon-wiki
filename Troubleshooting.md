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