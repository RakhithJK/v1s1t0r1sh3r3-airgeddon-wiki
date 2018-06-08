##### Important tips about bettercap

`bettercap` is used by `airgeddon` to perform a special Evil Twin attack on Evil Twin. The last supported `bettercap` version is 1.6.2. It was updated on most popular Linux distributions repositories to 2.x version which is not compatible. On this 2.x versions, the program suffered major changes which make it uncompatible to `airgeddon`.

The last compatible version (1.6.2) can be downloaded and compiled from the official author's page. Anyway, there is an available **deb** package ready to be installed on a Debian based Linux distribution. Here is the link: https://github.com/v1s1t0r1sh3r3/bettercap1.6.2

More info at [Bettercap official's page].
<p align="center">
	<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/dev/imgs/wiki/bettercap_logo.png" title="Bettercap"/>
</p>

#### Donwgrade instructions

If you have chosen the legacy deb package, follow this instructions to install it:

<sub>Requirements: <code>wget</code></sub>
<ul>
	<li>Uninstall latest 2.x bettercap package</li>
	<ul>
		<li><code>apt remove bettercap</code></li>
	</ul>
	<li>Install the ruby dependencies</li>
	<ul>
		<li><code>apt install ruby-packetfu ruby-colorize ruby-net-dns ruby-em-proxy ruby-network-interface</code></li>
	</ul>
	<li>Download the legacy **deb** bettercap package</li>
	<ul>
		<li><code>wget https://github.com/v1s1t0r1sh3r3/bettercap1.6.2/raw/master/bettercap_1.6.2-0parrot1_all.deb</code></li>
	</ul>
	<li>Install the downloaded package</li>
	<ul>
		<li><code>dpkg -i bettercap_1.6.2-0parrot1_all.deb</code></li>
	</ul>
</ul>

##### Important note. This downgrade method was tested only on Kali and Parrot Security Linux.

[Bettercap official's page]: https://www.bettercap.org/