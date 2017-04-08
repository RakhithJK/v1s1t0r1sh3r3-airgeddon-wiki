- Incompatible with native _Mac OSX_ at the moment.
  - *Bash version* &#8592; At first sight, _Mac OSX_ has an older Bash version. It can be avoided by upgrading it using `brew` or whatever, this is not the real problem :smile:
  - *Aircrack suite* &#8592; this suite does not support `airodump` and `aireplay` for OSX
  - *Wireless tools* &#8592; `iwconfig` does not exist in OSX, and `airport` command cannot be used. It generates different outputs

Anyway, you can launch `airgeddon` from _Mac OSX_ using Docker container. Take a look at the [Docker] Wiki section.
<p align="center">
	<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/docker/imgs/wiki/apple_airgeddon_docker.png" title="Mac OSX docker">
</p>

- Incompatible with native _OpenBSD_ and _FreeBSD_. They are Unix systems but they have some differences with Linux
  - *Bash* &#8592; By default, they have no Bash. It can be installed, so this is not the real problem again :sweat_smile:
  - *Wireless tools* &#8592; `iwconfig` does not exist in these systems, they use `ifconfig` instead and it generates different outputs

[Docker]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Docker