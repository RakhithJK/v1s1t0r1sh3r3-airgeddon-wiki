Some people don't even know if they are using Wayland instead of X window system. If that is your case, how to check? usually is as simple as check the output of the command `echo $XDG_SESSION_TYPE`. The output will be `x11` if you are using X window system, `wayland` if you are using Wayland graphics or `tty` if you are running a headless system. Sometimes this var can also be empty, but in that case probably you are not using Wayland.

In order to work with Wayland graphic system (instead on using X window system), you must add permissions to root user in this way:

`~$ xhost +SI:localuser:root`

Doing that, root user (or using `airgeddon` as sudo) is able to detect the screen resolution flawlessly.

More info about Wayland graphics system at [Wayland official's page].

<p align="center">
	<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/master/imgs/wiki/wayland_logo.png" title="Wayland"/>
</p>

[Wayland official's page]: https://wayland.freedesktop.org/