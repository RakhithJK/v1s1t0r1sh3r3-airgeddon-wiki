### Getting Started

It is essential to run this script as **root**, otherwise `airgeddon` won't work properly.

<details open>
	<summary><strong>Installation method 1</strong></summary>
	<i>(easiest). Requirements: git</i>
	<ul>
		<li>Clone the repository</li>
		<ul>
			<li><code>git clone https://github.com/v1s1t0r1sh3r3/airgeddon.git</code></li>
		</ul>
		<li>Go to the newly created directory</li>
		<ul>
			<li><code>cd airgeddon</code></li>
		</ul>
		<li>Run it (remove <strong>sudo</strong> if you already have root permissions)</li>
		<ul>
			<li><code>sudo bash airgeddon.sh</code></li>
		</ul>
	</ul>
</details>
<details open>
	<summary><strong>Installation method 2</strong></summary>
	<i>(alternative). Requirements: wget, unzip</i>
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

`airgeddon` should be launched with **bash** `bash /path/to/airgeddon.sh` and not with `sh` or any other kind of shell. <br/>

If you launch the script using another shell, there will be *Syntax errors* and faulty results.
Even with no initial errors, they will appear later. Always launch with **bash**!

#### Installing from binaries

There are existing binaries. You can download [latest deb package for Kali Linux]. You can install it using `dpkg -i airgeddon_x.x-x_all.deb`. Of course you must change "x" for the right downloaded version file. It will check the dependencies (essential tools) before install.

[latest deb package for Kali Linux]: https://github.com/v1s1t0r1sh3r3/airgeddon/tree/master/binaries/kali
