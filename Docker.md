<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/docker/imgs/banners/airgeddon_docker.png" align="left" hspace="10" vspace="6" title="airgeddon loves docker"/>

To run a container based on a Docker image to execute `airgeddon`, bear in mind that it should be run on a system running X Window (for example Xorg for Linux, XQuartz for Mac or XMing for Windows) because it runs xterm windows used for some features. `airgeddon` Docker image is based on Kali Linux.

Depending of the Operating System of your host, check the corresponding section to see the recommended docker run command. The image is going to be automatically downloaded from [airgeddon's Dockerhub] and then a Docker container will be be run launching automatically `airgeddon` script inside it:

 - [Linux]
 - [Mac OSX]
 - [Windows]

The default language for docker image is English. Once inside, it can be changed as normal using menu option for that.

If you prefer to build your own image, there is a [Dockerfile] present in the project.

[Linux]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Docker%20Linux
[Mac OSX]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Docker%20Mac%20OSX
[Windows]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Docker%20Windows
[airgeddon's Dockerhub]: https://hub.docker.com/r/v1s1t0r1sh3r3/airgeddon/
[Dockerfile]: https://github.com/v1s1t0r1sh3r3/airgeddon/blob/docker/docker/Dockerfile