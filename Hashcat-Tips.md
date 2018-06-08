##### Important tips about hashcat

`hashcat` is used by `airgeddon` to perform various attacks against captured files using the **CPU**. In order to execute it you'll need to install an **OpenCL** runtime compatible with your hardware.

If your `hashcat` version is 3.40 or higher, you'll need in addition the package called hashcat-utils. `airgeddon` will do the required check before using it.

If you are having problems with your **OpenCL** drivers, you can use the old legacy `hashcat` v2.0. Available at official page and already compiled for amd64 at this repository (just for copy and directly be executed): https://github.com/v1s1t0r1sh3r3/hashcat2.0

More info at [Hashcat official's page].
<p align="center">
	<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/master/imgs/wiki/hashcat_logo.png" title="Hashcat"/>
</p>

[Hashcat official's page]: https://hashcat.net/hashcat/