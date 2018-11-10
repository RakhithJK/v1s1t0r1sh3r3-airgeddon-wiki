### This is under development. The part of connecting to X Window system is working. Investigating yet how to connect wireless interfaces into docker container. Help wanted!!

The recommended docker run command to be run under Windows host is:

```bash
docker run \
       --rm \
       -ti \
       --name airgeddon \
       --net=host \
       --privileged \
       -p 3000:3000 \
       -v /path/to/some/dir/on/your/host:/io \
       -e DISPLAY=$(route print | grep 0.0.0.0 | awk '{print $4}' | head -n 1):0 \
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
 - `-e DISPLAY=$(route print | grep 0.0.0.0 | awk '{print $4}' | head -n 1):0` &#8594; It overwrites the needed var to connect to local X Window system (It's understood you installed Xming for Windows). awk, grep, etc., are working because even on windows remember you are in a special console.
 - `v1s1t0r1sh3r3/airgeddon` &#8594; Is the name and tag of the image. `v1s1t0r1sh3r3/airgeddon` is the stable version and is the same as `v1s1t0r1sh3r3/airgeddon:latest`. Alternatively you can use `v1s1t0r1sh3r3/airgeddon:beta` for development version.

### Windows Tips

#### Volume mapping

Don't forget to replace on docker command the string "/path/to/some/dir/on/your/host" with a path of an existing directory of your choice on your host machine. That directory will be the "input/output" point for the script. For example, if you place a dictionary.txt file there, inside the script you must access to it as "/io/dictionary.txt". If you capture a trophy or a Handshake file, save it at "/io/" dir to access it from the host.

#### X Window system

You'll need a X Window system running on your Windows. You can install [Xming], and after installing it, be sure of allowing connections from network clients in preferences as shown on next images:
<p align="center">
	<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/master/imgs/wiki/xming1.png" title="Xming config 1">
	<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/master/imgs/wiki/xming2.png" title="Xming config 2">
	<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/master/imgs/wiki/xming3.png" title="Xming config 3">
</p>

It's important to let the display number in 0 as shown in the first image and check the "No access control" checkbox as shown on third image.

[Xming]: http://www.straightrunning.com/XmingNotes/

