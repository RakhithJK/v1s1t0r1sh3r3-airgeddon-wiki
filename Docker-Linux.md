The recommended docker run command to be run under Linux host is:

```
~# docker run \
          --rm \
          -ti \
          --name airgeddon \
          --net=host \
          --privileged \
          -p 3000:3000 \
          -v /path/to/some/dir/on/your/host:/io \
          -e DISPLAY=$(env | grep DISPLAY | awk -F "=" '{print $2}') \
          v1s1t0r1sh3r3/airgeddon
```

Parameters explanation:

 - `--rm` &#8594; Ephemeral containter. It will be removed on exit.
 - `-ti` &#8594; Attach pseudo-TTY terminal to the container as interactive.
 - `--name airgeddon` &#8594; Name for the container.
 - `--net=host` &#8594; Is needed to have access to the host network interfaces inside the container.
 - `--privileged` &#8594; Needed to have permissions over network interfaces (mode switching).
 - `-p 3000:3000` &#8594; Open port to access to BeEF control panel from the host.
 - `-v /path/to/some/dir/on/your/host:/io` &#8594; It maps a directory from host to the container. Useful to use external files like dictionaries or whatever.
 - `-e DISPLAY=$(env | grep DISPLAY | awk -F "=" '{print $2}')` &#8594; It overwrites the needed var to connect to local X Window system. DISPLAY=:0 is used by default so you can avoid this parameter if you already have set DISPLAY=:0 var on your host system.
 - `v1s1t0r1sh3r3/airgeddon` &#8594; Is the name and tag of the image. `v1s1t0r1sh3r3/airgeddon` is the stable version and is the same as `v1s1t0r1sh3r3/airgeddon:latest`. Alternatively you can use `v1s1t0r1sh3r3/airgeddon:beta` for development version.

### Linux Tips

#### Volume mapping

Don't forget to replace on docker command the string "/path/to/some/dir/on/your/host" with a path of an existing directory of your choice on your host machine. That directory will be the "input/output" point for the script. For example, if you place a dictionary.txt file there, inside the script you must access to it as "/io/dictionary.txt". If you capture a trophy or a Handshake file, save it at "/io/" dir to access it from the host.

#### Display problems (resolution detection)

On some distros like Ubuntu, in order to open the possibility of connecting `airgeddon` xterm windows to your host X Window system, you must launch first `~# xhost +` command. You can check if you need it easily. The resolution should be detected inside `airgeddon` on initial checks. If not is detected, you have a problem with your DISPLAY var. You should launch `~# xhost +` command or adjust DISPLAY var on docker run command.

#### Hostapd possible conflict with host network-manager

Evil Twin attacks are using `hostapd` to create fake AP which usually are in conflict with `network-manager`. In native mode `airgeddon` handle this to solve process conflicts, but when launched in a Docker container is not possible because the conflicting network-manager is on the Linux host (not on container). Anyway, `airgeddon` will show you a warning as a reminder of this while running on Docker before launch `hostapd`. So, before launching any Evil Twin Attack, be sure of killing conflicting processes or disabling/stopping `network-manager` if you have it installed on Linux host or you'll get an error like this:

    Configuration file: /tmp/ag.hostapd.conf
    nl80211: Could not configure driver mode
    nl80211: deinit ifname=wlan0 disabled_11b_rates=0
    nl80211 driver initialization failed.
    wlan0: interface state UNINITIALIZED->DISABLED
    wlan0: AP-DISABLED 
    hostapd_free_hapd_data: Interface wlan0 wasn't started

The easiest way is to launch on host this command:

`~# airmon-ng check kill` &#8594; This will kill conflicting processes.

Or if you prefer, you can directly disable `network-manager`. To do this there are several ways. Depending on your Linux distribution the command may vary. Some of them are:

`~# service network-manager stop` &#8594; Valid for Kali, Backbox, Ubuntu, Debian, Raspbian, Parrot and Cyborg.<br/>
`~# service NetworkManager stop` &#8594; Valid for SuSE, CentOS, Fedora, Gentoo and Red Hat.<br/>
`~# systemctl stop NetworkManager.service` &#8594; Valid for Arch, BlackArch and OpenMandriva.<br/>
`~# rc-service NetworkManager ` &#8594; Valid for Pentoo.<br/>

The goal is to see at `hostapd` window something like this:

    Configuration file: /tmp/ag.hostapd.conf
    Using interface wlan0 with hwaddr 00:11:22:33:44:55 and ssid "airgeddon-test"
    wlan0: interface state UNINITIALIZED->ENABLED
    wlan0: AP-ENABLED

#### Kernel and drivers

It's understood that your Linux host has the needed drivers for your wireless card and its kernel support all the needed features for wireless operations (changing mode managed/monitor) in the same way as is needed to run it in native mode on any Linux system.