__Kali Nethunter__ for Android __is not officially supported__ by `airgeddon`. Anyway, some users were able to run `airgeddon` successfully on it. First of all, make sure that you have a kernel supporting usb wifi drivers for your card. You should be able to set monitor mode on your card before using `airgeddon`.

__Known Evil Twin captive portal problem__: If you experience a problem on webserver's window saying something like `cat: /dev/stdin: No such file or directory` when a client types the password in the captive portal during the attack, there is a fix for that. Just perform these commands in order to make some needed symlinks:

```
~# ln -s /proc/self/fd/0 /dev/stdin
~# ln -s /proc/self/fd/1 /dev/stdout
~# ln -s /proc/self/fd/2 /dev/stderr
```

__Important note__: If you reboot your Kali Nethunter, these commands should be launched again. Probably it could be a good idea to set them to be launched automatically on each reboot in some startup script.

__Other Evil Twin captive portal problem on redirection__: If captive portal is not appearing automatically or not redirecting well, probably it is caused by your kernel due to a non-nftables compatibility or it is missing a required module. Just force iptables to be used and it will work smoothly. To do that, enable the option setting it to true `AIRGEDDON_FORCE_IPTABLES=true` in the hidden configuration options ".airgeddonrc" file. More info about the available options in the .airgedonrc file is found [here](https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Options).

More info about Kali Nethunter at it's official page: [Kali Nethunter]

<p align="center">
	<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/master/imgs/wiki/kalinethunter_logo.png" title="Kali Nethunter"/>
</p>

[Kali Nethunter]: https://www.kali.org/kali-linux-nethunter/