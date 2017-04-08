##### Important tips about hashcat

`hashcat` is used by `airgeddon` to perform various attacks against captured files using the **CPU**. If your `hashcat` version is v3.0 or higher, in order to execute it you'll need to install an **OpenCL** runtime compatible with your hardware. This is the reason why in Docker container, the `hashcat` version used is v2.0. In this way errors are avoided.

<p align="center">
	<img src="https://raw.githubusercontent.com/v1s1t0r1sh3r3/airgeddon/docker/imgs/wiki/hashcat_logo.png" title="Hashcat"/>
</p>