For some Linux distributions like Ubuntu or Debian, and Parrot OS, the default naming for network devices is using the new nomenclature which is causing errors while using `airgeddon`. This is because of a bug in airmon-ng which is already solved in modern versions. But if you are still using an old airmon-ng version and or you are experiencing problems, you can just change your interface names to "old" style. Just keep reading.

__How to know if I am affected?__

If you see your wireless card named as _wlx00c0ca9208dc_ or any similar name, yeah you are affected and probably you'll face some issues using `airgeddon` while changing the mode of your card (it can happen depending on your airmon-ng version). It's better to have them using the classic naming style (_wlan0_, _wlan1_, etc.).

__How to change them to the classic names style?__

To do that you must modify the grub configuration. You should modify your `/etc/default/grub` file in order to add this `net.ifnames=0 biosdevname=0` to your `GRUB_CMDLINE_LINUX` line.

__I don't have that  `/etc/default/grub` file, now what?__

On some Linux, the path could be different like in modern Parrot Linux where you can locate the right file to modify here: `/etc/default/grub.d/parrot.cfg`.

On other Linux like installed on Raspberries, the file `/etc/default/grub` is not existing. In this case you can edit the file `/boot/cmdline.txt` to add there the needed `net.ifnames=0 biosdevname=0` options.

__Examples__

 - `GRUB_CMDLINE_LINUX="net.ifnames=0 biosdevname=0"`
 - `GRUB_CMDLINE_LINUX="find_preseed=/preseed.cfg auto noprompt priority=critical locale=en_US net.ifnames=0 biosdevname=0"`.

Just add `net.ifnames=0 biosdevname=0` to your existing options keeping what you already have there.

Now just need to apply changes following the last point of this section.

__After modification, to apply changes (IT WILL NOT BE EFFECTIVE WITHOUT THIS LAST STEP!!)__

After modifying the `/etc/default/grub` file, execute `update-grub` and then reboot or directly reboot if you modified `/boot/cmdline.txt` as explained above (used usually for Raspberries). After that, your wireless interface cards will be named again as always (_wlan0_, _wlan1_, etc.) and you'll be able to make them work correctly in `airgeddon`.

__Using Parrot OS and the above options do not work__

Run this in a terminal `sudo ln -s /dev/null /etc/udev/rules.d/80-net-setup-link.rules` then reboot