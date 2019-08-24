__Kali Nethunter__ for Android __is not officially supported__ by `airgeddon`. Anyway, some users were able to run successfully `airgeddon` on it. First of all, make sure you have a kernel supporting usb drivers for your card. You should be able to set monitor mode on your card before using `airgeddon`.

__Known Evil Twin captive portal problem__: If you experience a problem on webserver's window saying something like `cat: /dev/stdin: No such file or directory` when a client types the password in the captive portal during the attack, there is a fix for that. Just perform these commands in order to make some needed symlinks:

```
~# ln -s /proc/self/fd/0 /dev/stdin
~# ln -s /proc/self/fd/1 /dev/stdout
~# ln -s /proc/self/fd/2 /dev/stderr
```

__Importante note__: If you reboot your Kali Nethunter, these commands should be launched again.

More info about Kali Nethunter at it's official page: [Kali Nethunter]

<p align="center">
	<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/dev/imgs/wiki/kalinethunter_logo.png" title="Kali Nethunter"/>
</p>

[Kali Nethunter]: https://www.kali.org/kali-linux-nethunter/