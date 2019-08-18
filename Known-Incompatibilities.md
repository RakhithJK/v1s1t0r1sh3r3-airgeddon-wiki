- __Incompatible__ with Apple __OSX__/__MacOS__.
  - *Bash version* &#8592; OSX/MacOS has older Bash versions. It can be avoided by upgrading it using `brew` or whatever, this is not the real problem :smile:
  - *Aircrack suite* &#8592; this suite does not support `airodump` and `aireplay` for OSX/MacOS
  - *Wireless tools* &#8592; `iwconfig` does not exist in OSX/MacOS, and `airport` command cannot be used. It generates different outputs

Anyway, you can try to run airgeddon on OSX/MacOS using Docker container (is in alpha phase, not working yet). Take a look at the [Docker] Wiki section.
<p align="center">
	<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/master/imgs/wiki/apple_airgeddon_docker.png" title="Mac OSX airgeddon docker">
</p>

- __Incompatible__ with native __OpenBSD__ and __FreeBSD__. They are Unix systems but they have some differences with Linux
  - *Bash* &#8592; By default, they have no Bash. It can be installed, so this is not the real problem again :sweat_smile:
  - *Wireless tools* &#8592; `iwconfig` does not exist in these systems, they use `ifconfig` instead and it generates different outputs

- __Incompatible__ with any Linux distribution run under __Windows subsystem__.

[Docker]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Docker