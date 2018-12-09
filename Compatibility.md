###### This page lists all Linux distributions compatible with airgeddon. It's an alphabetically sorted and up-to-date list.

***

<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/master/imgs/wiki/alien_tux.png" align="left" hspace="10" vspace="6" title="airgeddon Linux"/>

**tux** and **v1s1t0r** used to play together since they were little, so they teamed up and created the tool called `airgeddon`

It is developed on Linux and designed for Linux :alien::green_heart::penguin:

It can run on any Linux distribution that passes the tools validations. Some of them have already been tested and listed here.

***

#### Tested on these compatible Linux distributions
- Arch 4.6.2-1 to 4.18.16-arch1-1-ARCH
- Backbox 4.5.1 to 5.x
- BlackArch 2016.01.10 to 2018.06.01
- CentOS 6 and 7
- Cyborg Hawk 1.1
- Debian 7 (Wheezy) to 9 (Stretch)
- Fedora 24 to 28
- Gentoo 20160514 to 20180206
- Kali 2.0, 2016.1 to 2018.4 and arm versions (Raspberry Pi)
- Mint 18.x (Serena to Sylvia)
- OpenMandriva LX3
- OpenSUSE Leap 42.1 to 42.3
- Parrot Security 2.2.1 or higher (3.x, 4.x) and arm versions (Raspberry Pi)
- Raspbian 7 (Wheezy) to 9 (Stretch) (Raspberry Pi)
- Red Hat 7 (Maipo)
- Ubuntu/Xubuntu 15.10 to 18.04
- Wifislax 4.11.1 to 64-1.1

If you wish to run airgeddon in any different Operating System, you can use a [Docker] container.

#### Important compatibility notes
 - Any Linux distribution run under Windows subsystem is **NOT** supported.
 - In `airgeddon<=8.10`, only `airmon` compatible wireless cards are supported. If your card is unable to change its mode by performing an `airmon` command out of `airgeddon`, it won't work. From `airgeddon>=8.11` any card can be used if the monitor mode is supported.
 - In order to work with Wayland graphic system (instead on using X window system), you must add permissions to root user in this way: `~$ xhost si:localuser:root`. Doing that, root user (or using `airgeddon` as sudo) is able to detect the screen resolution.

[Docker]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Docker