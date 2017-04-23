# airgeddon [![Version-shield]](CHANGELOG.md) [![Bash4.2-shield]](http://tldp.org/LDP/abs/html/bashver4.html#AEN21220) [![License-shield]](LICENSE.md) [![Docker-shield]](https://hub.docker.com/r/v1s1t0r1sh3r3/airgeddon/) [![Paypal-shield]](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=7ELM486P7XKKG) [![Bitcoin-shield]](https://blockchain.info/address/1AKnTXbomtwUzrm81FRzi5acSSXxGteGTH)

> This is a multi-use bash script for Linux systems to audit wireless networks.

![Banner]
---
<strong>Table of contents</strong>
<ul>
	<strong>I. Content & Features</strong>
	<ul>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki">Content</a></li>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Features">Features</a></li>
	</ul>
	<br/>
	<strong>II. Requirements</strong>
	<ul>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Requirements">Requirements</a></li>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Compatibility">Compatibility</a></li>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Essential%20Tools">Essential Tools</a></li>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Optional%20Tools">Optional Tools</a></li>
		<ul>
			<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/BeEF%20Tips">BeEF Tips</a></li>
			<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Hashcat%20Tips">Hashcat Tips</a></li>
		</ul>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Update%20Tools">Update Tools</a></li>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Internal%20Tools">Internal Tools</a></li>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Known%20incompatibilities">Known incompatibilities</a></li>
	</ul>
	<br/>
	<strong>III. Getting started</strong>
	<ul>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Installation%20&%20Usage">Installation & Usage</a></li>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Docker">Docker</a></li>
		<ul>
			<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Docker%20Linux">Linux</a></li>
			<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Docker%20Mac%20OSX">Mac OSX</a></li>
			<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Docker%20Windows">Windows</a></li>
		</ul>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Other%20Sources">Other Sources</a></li>
	</ul>
	<br/>
	<strong>IV. Project & Development</strong>
	<ul>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Supported%20Languages">Supported Languages</a></li>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Contributing">Contributing</a></li>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Changelog">Changelog</a></li>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Disclaimer%20&%20License">Disclaimer & License</a></li>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Contact">Contact</a></li>
	</ul>
	<br/>
	<strong>V. Acknowledgments & References</strong>
	<ul>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Hat%20Tip%20To">Hat Tip To</a></li>
		<li><a href="https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Inspiration">Inspiration</a></li>
	</ul>
</ul>
<!-- Links to Wiki -->
[Content]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki
[Features]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Features
[Requirements]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Requirements
[Requirements]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Compatibility
[Requirements]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Essential%20Tools
[Requirements]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Optional%20Tools
[Requirements]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/BeEF%20Tips
[Requirements]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Hashcat%20Tips
[Update Tools]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Update%20Tools
[Update Tools]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Update%20Tools
[Update Tools]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Update%20Tools
[Update Tools]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Update%20Tools
[Update Tools]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Update%20Tools
[Update Tools]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Update%20Tools
[Update Tools]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Update%20Tools
[Update Tools]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Update%20Tools
[Update Tools]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Update%20Tools
[Update Tools]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Update%20Tools
<!-- Links To Images -->
[Banner]: https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/master/imgs/banners/airgeddon_banner.png "We will conquer the earth!!"
<!-- Badges URLs -->
[Version-shield]: https://img.shields.io/badge/version-6.2-blue.svg?style=flat-square&colorA=273133&colorB=0093ee "Latest version"
[Bash4.2-shield]: https://img.shields.io/badge/bash-4.2%2B-blue.svg?style=flat-square&colorA=273133&colorB=00db00 "Bash 4.2 or later"
[License-shield]: https://img.shields.io/badge/license-GPL%20v3%2B-blue.svg?style=flat-square&colorA=273133&colorB=bd0000 "GPL v3+"
[Docker-shield]: https://img.shields.io/docker/automated/v1s1t0r1sh3r3/airgeddon.svg?style=flat-square&colorA=273133&colorB=f9ff5a "Docker rules!"
[Paypal-shield]: https://img.shields.io/badge/donate-paypal-blue.svg?style=flat-square&colorA=273133&colorB=b008bb "Show me the money!"
[Bitcoin-shield]: https://img.shields.io/badge/donate-bitcoin-blue.svg?style=flat-square&colorA=273133&colorB=f7931a "Show me the money!"