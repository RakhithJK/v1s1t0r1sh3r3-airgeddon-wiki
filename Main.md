# :satellite: airgeddon [![Version-shield]](CHANGELOG.md) [![Bash4.2-shield]](http://tldp.org/LDP/abs/html/bashver4.html#AEN21220) [![License-shield]](LICENSE.md) [![Docker-shield]](https://cloud.docker.com/app/v1s1t0r1sh3r3/repository/docker/v1s1t0r1sh3r3/airgeddon/general) [![Paypal-shield]](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=7ELM486P7XKKG) [![Bitcoin-shield]](https://blockchain.info/address/1AKnTXbomtwUzrm81FRzi5acSSXxGteGTH)

> This is a multi-use bash script for Linux systems to audit wireless networks.

![Banner]

<summary><strong>Table of Contents</strong></summary>
	<ul>
		<li><a href="#features">Features</a></li>
		<li><a href="#requirements">Requirements</a></li>
		<ul>
			<li><a href="#essential-tools--the-script-does-not-work-if-you-dont-have-installed-all-of-them">Essential Tools</a></li>
			<li><a href="#optional-tools--not-necessary-to-work-only-needed-for-some-features">Optional Tools</a></li>
			<ul>
				<li><a href="#important-tips-about-beef">BeEF Tips</a></li>
				<li><a href="#important-tips-about-hashcat">Hashcat Tips</a></li>
			</ul>
			<li><a href="#update-tools--not-necessary-to-work-only-used-for-auto-update">Update Tools</a></li>
			<li><a href="#internal-tools--these-are-internally-checked-not-necessary-to-work-good-to-have">Internal Tools</a></li>
		</ul>
		<li><a href="#usage">Usage</a></li>
		<li><a href="#docker">Docker</a></li>
		<li><a href="#supported-languages">Supported Languages</a></li>
		<li><a href="#known-incompatibilities">Known Incompatibilities</a></li>
		<li><a href="#contributing">Contributing</a></li>
		<li><a href="#changelog">Changelog</a></li>
		<li><a href="#disclaimer--license">Disclaimer & License</a></li>
		<li><a href="#acknowledgments--license">Acknowledgments</a></li>
		<ul>
			<li><a href="#hat-tip-to">Hat Tip To</a></li>
			<li><a href="#inspiration">Inspiration</a></li>
		</ul>
	</ul>

<!-- Links To Images -->
[Banner]: https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/master/imgs/banners/airgeddon_banner.png "We will conquer the earth!!"
<!-- Badges URLs -->
[Version-shield]: https://img.shields.io/badge/version-6.2-blue.svg?style=flat-square&colorA=273133&colorB=0093ee "Latest version"
[Bash4.2-shield]: https://img.shields.io/badge/bash-4.2%2B-blue.svg?style=flat-square&colorA=273133&colorB=00db00 "Bash 4.2 or later"
[License-shield]: https://img.shields.io/badge/license-GPL%20v3%2B-blue.svg?style=flat-square&colorA=273133&colorB=bd0000 "GPL v3+"
[Docker-shield]: https://img.shields.io/docker/automated/v1s1t0r1sh3r3/airgeddon.svg?style=flat-square&colorA=273133&colorB=f9ff5a "Docker rules!"
[Paypal-shield]: https://img.shields.io/badge/donate-paypal-blue.svg?style=flat-square&colorA=273133&colorB=b008bb "Show me the money!"
[Bitcoin-shield]: https://img.shields.io/badge/donate-bitcoin-blue.svg?style=flat-square&colorA=273133&colorB=f7931a "Show me the money!"