##### Important tips about bettercap

`bettercap` is used by `airgeddon` to perform a special Evil Twin attack. The last supported `bettercap` version is 1.6.2. It was updated on most popular Linux distributions repositories to 2.x version which is not compatible. On this 2.x versions, the program suffered major changes which make it uncompatible to `airgeddon`.

The last compatible version (1.6.2) can be downloaded and compiled from the official author's page. More info at [Bettercap official's page].

<p align="center">
	<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/master/imgs/wiki/bettercap_logo.png" title="Bettercap"/>
</p>

Anyway, there is an available **deb** package ready to be installed on a Debian based Linux distribution. Here is the link: https://github.com/v1s1t0r1sh3r3/airgeddon_deb_packages/blob/master/amd64/bettercap_1.6.2-0parrot1_all.deb

#### Donwgrade instructions for Debian based Linux distributions

If you have chosen the legacy deb package, follow this instructions to install it:

<sub>Requirements: <code>wget</code></sub>
<ul>
	<li>Uninstall latest 2.x bettercap package</li>
	<ul>
		<li><code>~# apt remove bettercap</code></li>
	</ul>
	<li>Install the ruby dependencies</li>
	<ul>
		<li><code>~# apt install ruby-packetfu ruby-colorize ruby-net-dns ruby-em-proxy ruby-network-interface</code></li>
	</ul>
	<ul>If you have some troubles with the ruby dependencies, there are also available packages for them here: <a href="https://github.com/v1s1t0r1sh3r3/airgeddon_deb_packages">https://github.com/v1s1t0r1sh3r3/airgeddon_deb_packages</a></ul>
	<li>Download the legacy deb bettercap package</li>
	<ul>
		<li><code>~# wget https://github.com/v1s1t0r1sh3r3/airgeddon_deb_packages/raw/master/arm64/bettercap_1.6.2-0parrot1_all.deb</code></li>
	</ul>
	<li>Install the downloaded package</li>
	<ul>
		<li><code>~# dpkg -i bettercap_1.6.2-0parrot1_all.deb</code></li>
	</ul>
</ul>

Additionally, you may want as optional to mark the package as "hold" to avoid its update in order to keep the downgraded compatible version:

`~# apt-mark hold bettercap`

#### Important note. This downgrade method was tested only on Kali and Parrot Security Linux. If you have another non-Debian based Linux distribution, then keep reading...

Bettercap was migrated from _ruby_ to _go_ programming language. Last ruby based version was released as _1.6.2_ so it can be installed as ruby gem. Just uninstall your bettercap 2.x using yum, emerge, yast, pacman or any package manager depending of your Linux distribution, and then execute `gem install bettercap`. This will install the needed 1.6.2 version for `airgeddon`.

[Bettercap official's page]: https://www.bettercap.org/