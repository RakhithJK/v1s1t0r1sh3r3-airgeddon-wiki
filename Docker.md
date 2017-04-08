<a href="LICENSE.md"><img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/docker/imgs/banners/airgeddon_docker.png" align="left" hspace="10" vspace="6"></a>
To run a container based on a Docker image to execute `airgeddon`, bear in mind that it should be run on a system running X Window (for example Xorg for Linux or XQuartz for Mac) because it runs xterm windows used for some features. `airgeddon` Docker image is based on Kali Linux.

Below, there are docker run commands as example (for Linux and Mac OSX. Not tested yet in Windows). The image is going to be automatically downloaded from [airgeddon's Dockerhub]/[airgeddon's Dockercloud] and then a Docker container will be be run launching automatically `airgeddon` script inside the container:

**Linux**
```
docker run --rm -ti --name airgeddon --net=host --privileged -p 3000:3000 -v /path/to/some/dir/on/your/host:/io v1s1t0r1sh3r3/airgeddon
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

**Mac OSX**
```
docker run --rm -ti --name airgeddon --net=host --privileged -p 3000:3000 -v /path/to/some/dir/on/your/host:/io -e DISPLAY=$(ifconfig en0 | grep inet | awk '$1=="inet" {print $2}') v1s1t0r1sh3r3/airgeddon
```

Mac Parameters explanation:

 - `--rm` -> Ephemeral containter. It will be removed on exit.
 - `-ti` -> Attach pseudo-TTY terminal to the container as interactive.
 - `--name airgeddon` -> Name for the container.
 - `--net=host` -> Is needed to have access to the host network interfaces inside the container.
 - `--privileged` -> Needed to have permissions over network interfaces (mode switching).
 - `-p 3000:3000` -> Open port to access to BeEF control panel from the host.
 - `-v /path/to/some/dir/on/your/host:/io` -> It maps a directory from host to the container. Useful to use external files like dictionaries or whatever.
 - `-e DISPLAY=$(ifconfig en0 | grep inet | awk '$1=="inet" {print $2}')` -> It overwrites the needed var to connect to local X Window system (It's understood you installed XQuartz for mac). This is not needed for Linux because the Dockerfile already has set DISPLAY=:0 as default which is valid for Linux.
 - `v1s1t0r1sh3r3/airgeddon` -> Is the name and tag of the image. `v1s1t0r1sh3r3/airgeddon` is the stable version and is the same as `v1s1t0r1sh3r3/airgeddon:latest`. Alternatively you can use `v1s1t0r1sh3r3/airgeddon:beta` or `v1s1t0r1sh3r3/airgeddon:alpha` for development versions.

**General Tips**

Don't forget to replace "/path/to/some/dir/on/your/host" with a path of an existing directory of your choice on your host machine. That directory will be the "input/output" point for the script. For example, if you place a dictionary.txt file there, inside the script you must access to it as "/io/dictionary.txt". If you capture a trophy or a Handshake file, save it at "/io/" dir to access it from the host.

The default language for docker image is English. Once inside, it can be changed as normal using menu option for that.

If you prefer to build your own image, there is a [Dockerfile] present in the project.

**Mac OSX Tips**

You'll need a X window system running. You can install [XQuartz]. And after installing, be sure of allowing connections for network clients in preferences as shown on next image:

![XQuartz Config](https://fredrikaverpil.github.io/blog/assets/docker/xquartz_preferences.png)

After that, you'll need to disable access control or add your ip to the authorized clients list:

`xhost +` -> to disable completely the restriction.

or

`xhost $(ifconfig en0 | grep inet | awk '$1=="inet" {print $2}')` -> to allow only local ip. This is more restrictive and recommended.

[airgeddon's Dockerhub]: https://hub.docker.com/r/v1s1t0r1sh3r3/airgeddon/
[airgeddon's Dockercloud]: https://cloud.docker.com/app/v1s1t0r1sh3r3/repository/docker/v1s1t0r1sh3r3/airgeddon/general
[Dockerfile]: https://github.com/v1s1t0r1sh3r3/airgeddon/blob/docker/docker/Dockerfile
[XQuartz]: https://www.xquartz.org/