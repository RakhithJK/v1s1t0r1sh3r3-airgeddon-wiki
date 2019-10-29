For some Linux distributions like Ubuntu or Debian since some versions, the default naming for network devices is using the new nomenclature which is causing errors while using `airgeddon`.

__How to know if I am affected?__

If you see your wireless card named as _wlx00c0ca9208dc_ or any similar name, yeah you are affected and probably you'll face some issues using `airgeddon` while changing mode of your card. It's better to have them using the classic naming style (wlan0, wlan1, etc.).

__How to change them to the classic names style?__

To do that you must modify grub configuration. You should modify your `/etc/default/grub` file in order to add this `net.ifnames=0 biosdevname=0` to your `GRUB_CMDLINE_LINUX` line.

For example:
 - `GRUB_CMDLINE_LINUX="net.ifnames=0 biosdevname=0"`
 - `GRUB_CMDLINE_LINUX="find_preseed=/preseed.cfg auto noprompt priority=critical locale=en_US net.ifnames=0 biosdevname=0"`.

Just add `net.ifnames=0 biosdevname=0` to your existing options keeping what you already have there.

After modifying the file, execute `grub-update` and then reboot. After that, your wireless interface cards will be named again as always (wlan0, wlan1, etc.) and you'll be able to make them work with `airgeddon`.