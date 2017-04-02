<a href="LICENSE.md"><img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/docker/imgs/banners/airgeddon_docker.png" align="left" hspace="10" vspace="6"></a>
To run a container based on a Docker image to execute `airgeddon`, bear in mind that it should be run on a system running X Window because it runs xterm windows used for some features.

Below, there is a docker run command as example. The image is going to be automatically downloaded from [Dockerhub]/[Dockercloud] and then a Docker container is going to be run. It will launch `airgeddon` script automatically inside the container:
<br/>
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

Don't forget to replace "/path/to/some/dir/on/your/host" with a path of an existing directory of your choice on your host machine. That directory will be the "input/output" point for the script. For example, if you place a dictionary.txt file there, inside the script you must access to it as "/io/dictionary.txt".

[Dockerhub]: https://hub.docker.com/r/v1s1t0r1sh3r3/airgeddon/
[Dockercloud]: https://cloud.docker.com/app/v1s1t0r1sh3r3/repository/docker/v1s1t0r1sh3r3/airgeddon/general