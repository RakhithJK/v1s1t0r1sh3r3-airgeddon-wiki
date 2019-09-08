In order to work with Wayland graphic system (instead on using X window system), you must add permissions to root user in this way:

`~$ xhost si:localuser:root`

Doing that, root user (or using `airgeddon` as sudo) is able to detect the screen resolution flawlessly.

More info about Wayland graphics system at [Wayland official's page].

<p align="center">
	<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/master/imgs/wiki/wayland_logo.png" title="Wayland"/>
</p>

[Wayland official's page]: https://wayland.freedesktop.org/