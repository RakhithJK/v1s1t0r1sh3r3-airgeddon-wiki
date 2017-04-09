### This is under development. For now, only image with alpha tag is available at Dockerhub

The recommended docker run command to be run under Linux host is:

```
docker run --rm \
           -ti \
           --name airgeddon \
           --net=host \
           --privileged \
           -p 3000:3000 \
           -v /path/to/some/dir/on/your/host:/io \
           v1s1t0r1sh3r3/airgeddon
```

Parameters explanation:

 - `--rm` -> Ephemeral containter. It will be removed on exit.
 - `-ti` -> Attach pseudo-TTY terminal to the container as interactive.
 - `--name airgeddon` -> Name for the container.
 - `--net=host` -> Is needed to have access to the host network interfaces inside the container.
 - `--privileged` -> Needed to have permissions over network interfaces (mode switching).
 - `-p 3000:3000` -> Open port to access to BeEF control panel from the host.
 - `-v /path/to/some/dir/on/your/host:/io` -> It maps a directory from host to the container. Useful to use external files like dictionaries or whatever.
 - `v1s1t0r1sh3r3/airgeddon` -> Is the name and tag of the image. `v1s1t0r1sh3r3/airgeddon` is the stable version and is the same as `v1s1t0r1sh3r3/airgeddon:latest`. Alternatively you can use `v1s1t0r1sh3r3/airgeddon:beta` or `v1s1t0r1sh3r3/airgeddon:alpha` for development versions.

### Linux Tips

#### Volume mapping

Don't forget to replace on docker command the string "/path/to/some/dir/on/your/host" with a path of an existing directory of your choice on your host machine. That directory will be the "input/output" point for the script. For example, if you place a dictionary.txt file there, inside the script you must access to it as "/io/dictionary.txt". If you capture a trophy or a Handshake file, save it at "/io/" dir to access it from the host.

#### Hostapd possible conflict
Evil Twin attacks are using `hostapd` to create fake AP which usually are in conflict with `network-manager`. Usually (in native mode) `airgeddon` manages all of this stuff to solve process conflicts, but when launched in a Docker container is not possible because the conflicting network-manager is on the Linux host. So, before launching any Evil Twin Attack, be sure of killing conflicting processes or disabling/stopping `network-manager` if you have it installed on Linux host or you'll get an error like this:

    Configuration file: /tmp/ag.hostapd.conf
    nl80211: Could not configure driver mode
    nl80211: deinit ifname=wlan0 disabled_11b_rates=0
    nl80211 driver initialization failed.
    wlan0: interface state UNINITIALIZED->DISABLED
    wlan0: AP-DISABLED 
    hostapd_free_hapd_data: Interface wlan0 wasn't started

The easiest way is to launch on host this command:

`airmon-ng check kill` -> This will kill conflicting processes.

Or if you prefer, you can directly disable `network-manager`. To do this there are several ways. Depending of your Linux distribution the command can change. Some of them:

`service network-manager stop` -> Valid for Kali, Backbox, Ubuntu, Debian, Raspbian, Parrot and Cyborg.<br/>
`service NetworkManager stop` -> Valid for SuSE, CentOS, Fedora, Gentoo and Red Hat.<br/>
`systemctl stop NetworkManager.service` -> Valid for Arch, BlackArch and OpenMandriva.<br/>

The goal is to see at `hostapd` window something like this:

    Configuration file: /tmp/ag.hostapd.conf
    Using interface wlan0 with hwaddr 00:11:22:33:44:55 and ssid "airgeddon-test"
    wlan0: interface state UNINITIALIZED->ENABLED
    wlan0: AP-ENABLED