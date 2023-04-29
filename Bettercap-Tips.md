##### Important tips about bettercap

`bettercap` is used by `airgeddon` to perform a special Evil Twin attack. Until `airgeddon<=10.30`, the unique supported version was `bettercap 1.x`. After the release of `airgeddon>=10.31` now `bettercap 2.x` is supported since _2.28_ was released fixing the sslstrip problems. So you can choose to use the oldest `bettercap<=1.6.2` or the newest `bettercap>=2.28`.

<p align="center">
	<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/master/imgs/wiki/bettercap_logo.png" title="Bettercap"/>
</p>

##### Bettercap 2.x (>=2.28)

The easiest choice. Just download it from [Bettercap official's Github repo] or install it from repositories of your Linux distribution as always. If you are experiencing some kind of problem and bettercap is showing errors like `error while running caplet` or similar, it also could be related to the Golang version installed in your system. Users reported that using go1.20.1 or higher, it should be fine.

##### Bettercap 1.x (<=1.6.2)

If you are going to use old `bettercap 1.x`, the recommended version is _1.6.2_. If you have already `bettercap 2.x` installed, probably you'll need to downgrade it. Here, a method to do it is explained.

###### Donwgrade instructions for Debian based Linux distributions

There is an available **deb** package ready to be installed on a Debian based Linux distribution. Here is the link: https://github.com/v1s1t0r1sh3r3/airgeddon_deb_packages/blob/master/amd64/bettercap_1.6.2-0parrot1_all.deb

If you have chosen the legacy deb package, follow this instructions to install it:

<sub>Requirements: <code>wget</code></sub>
<ul>
	<li>Uninstall bettercap 2.x package</li>
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

###### Important note. This downgrade method was tested only on Kali and Parrot Security Linux. If you have another non-Debian based Linux distribution and want to downgrade, then keep reading...

Bettercap was migrated from _ruby_ to _go_ programming language. Last ruby based version was released as _1.6.2_ so it can be installed as ruby gem. Just uninstall your `bettercap 2.x` using yum, emerge, yast, pacman or any package manager depending on your Linux distribution, and then execute `gem install bettercap`. This will install _1.6.2_ version.

[Bettercap official's Github repo]: https://github.com/bettercap/bettercap