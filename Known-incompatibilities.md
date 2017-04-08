- Incompatible with native _Mac OSX_ at the moment.
  - *Bash version* &#8592; it can be avoided by upgrading it using `brew` or whatever, this is not the real problem :smile:
  - *Aircrack suite* &#8592; this suite does not support `airodump` and `aireplay` for OSX
  - *Wireless tools* &#8592; `iwconfig` does not exist in OSX, and `airport` command cannot be used. It generates different outputs

Anyway, you can launch `airgeddon` from Mac OSX using Docker container. Look at the [Docker] Wiki section.

- Incompatible with OpenBSD and FreeBSD. They are Unix systems but they have some differences with Linux
  - *Bash* &#8592; They have no bash. It can be installed, this is not the real problem again :sweat_smile:
  - *Wireless tools* &#8592; `iwconfig` does not exist in these systems, they use `ifconfig` instead and it generates different outputs

[Docker]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Docker