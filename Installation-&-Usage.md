It is essential to run this script as **root**, otherwise `airgeddon` won't work properly.

***

### Generic installation

<details open>
	<summary><strong>Installation method 1</strong></summary>
	<sub>(easiest) Requirements: <code>git</code></sub>
	<ul>
		<li>Clone the repository</li>
		<ul>
			<li><code>~$ git clone --depth 1 https://github.com/v1s1t0r1sh3r3/airgeddon.git</code></li>
		</ul>
		<li>Go to the newly created directory</li>
		<ul>
			<li><code>~$ cd airgeddon</code></li>
		</ul>
		<li>Run it (remove <strong>sudo</strong> if you already have root permissions)</li>
		<ul>
			<li><code>~$ sudo bash airgeddon.sh</code></li>
		</ul>
	</ul>
</details>
<details open>
	<summary><strong>Installation method 2</strong></summary>
	<sub>(alternative) Requirements: <code>wget</code> <code>unzip</code></sub>
	<ul>
		<li>Download files</li>
		<ul>
			<li><code>wget https://github.com/v1s1t0r1sh3r3/airgeddon/archive/master.zip</code></li>
		</ul>
		<li>Unzip the downloaded file</li>
		<ul>
			<li><code>unzip master.zip</code></li>
		</ul>
		<li>Go to the newly created directory</li>
		<ul>
			<li><code>cd airgeddon-master</code></li>
		</ul>
		<li>Run it (remove <strong>sudo</strong> if you already have root permissions)</li>
		<ul>
			<li><code>sudo bash airgeddon.sh</code></li>
		</ul>
	</ul>
</details>

airgeddon should be launched with **bash** `bash /path/to/airgeddon.sh` and not with **sh** or any other kind of shell


If you launch the script using another shell, there will be *Syntax errors* and faulty results.
Even with no initial errors, they will appear later. Always launch with **bash**!

### Binary installation

This section lists the binaries that are available for you to download and install airgeddon.

- Arch Linux
  1. Download the [latest tarball for Arch Linux]
  2. Install it using `pacman -U airgeddon-git-x.x-y-any.pkg.tar.xz`

- Kali Linux
  1. Download the [latest deb package for Kali Linux]
  2. Install it using `dpkg -i airgeddon_x.x-x_all.deb`

[latest tarball for Arch Linux]: https://github.com/v1s1t0r1sh3r3/airgeddon/tree/master/binaries/arch
[latest deb package for Kali Linux]: https://github.com/v1s1t0r1sh3r3/airgeddon/tree/master/binaries/kali