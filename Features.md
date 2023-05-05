`airgeddon` is an alive project growing day by day. This is the list of features so far:
<!-- Each sub list needs 2 additional preceding spaces -->
- Interface mode switcher (Monitor-Managed) keeping selection even on interface name changing
- DoS over wireless networks using different methods (mdk3, mdk4, aireplay-ng). "DoS Pursuit mode" available to avoid AP channel hopping (available also on DoS performed on Evil Twin attacks)
- Full support for 2.4Ghz and 5Ghz bands
- Assisted WPA/WPA2 personal networks Handshake file and PMKID capturing
- Cleaning and optimizing Handshake captured files
- Offline password decrypting on WPA/WPA2 captured files for personal networks (Handshakes and PMKIDs) using dictionary, bruteforce and rule based attacks with aircrack, crunch and hashcat tools. Enterprise networks captured password decrypting based on john the ripper, crunch, asleap and hashcat tools. GPU support available for hashcat.
- WPA3 online dictionary attack ([plugin](https://github.com/OscarAkaElvis/airgeddon-plugins) based) 
- Evil Twin attacks (Rogue AP) - WPA/WPA2/WPA3
  - Only Rogue/Fake AP mode to sniff using external sniffer (Hostapd + DHCP + DoS)
  - Simple integrated sniffing (Hostapd + DHCP + DoS + Ettercap)
  - Integrated sniffing, sslstrip2 (Hostapd + DHCP + DoS + Bettercap)
  - Integrated sniffing, sslstrip2 and BeEF Browser Exploitation Framework (Hostapd + DHCP + DoS + Bettercap + BeEF)
  - Captive portal with "DNS blackhole" to capture wifi passwords (Hostapd + DHCP + DoS + Dnsspoff + Lighttpd)
  - Optional MAC spoofing for all Evil Twin attacks
- WPS features
  - WPS scanning (wash). Self parameterization to avoid *"bad fcs"* problem
  - Custom PIN association (bully and reaver)
  - Pixie Dust attacks (bully and reaver)
  - Bruteforce PIN attacks (bully and reaver)
  - Null PIN attack (reaver)
  - Known WPS PINs attack (bully and reaver), based on online PIN database with auto-update
  - Integration of the most common PIN generation algorithms (ComputePIN, EasyBox, Arcadyan, etc.)
  - Offline PIN generation and the possibility to search PIN results on database for a target
  - Parameterizable timeouts for all attacks
- Enterprise networks attacks - WPA/WPA2/WPA3
  - Fake AP using "smooth" and "noisy" modes capturing enterprise hashes and plain passwords
  - Custom certificates creation
- WEP All-in-One attack (combining different techniques: Chop-Chop, Caffe Latte, ARP Replay, Hirte, Fragmentation, Fake association, etc.)
- Adaptation of WPA2 attacks to work with WPA2/WPA3 networks working in "Mixed Mode"
- Compatibility with many Linux distributions (see [Requirements] section)
- Easy targeting and selection in every section
- Drag and drop files on console window for entering file paths or autocomplete using tab key on every path input for easier use
- Dynamic screen resolution detection and windows auto-sizing for optimal viewing
- Controlled Exit. Cleaning tasks and temp files. Restoring nftables/iptables after an attack that require changes on them. Option to keep monitor mode if desired on exit
- Multilanguage support and autodetect OS language feature (see [Supported Languages] section)
- Help hints in every zone/menu for easy use
- Auto-update. Script checks for newer version if possible
- [Docker] image for easy and quick container deployment. Use already built image on [Docker Hub] or build your own
- Http proxy auto detection for updates
- Wayland graphic system supported (not only X window system)
- Tmux support for headless (systems without X window) environments
- Multiple configurable options based on fallback substitution variables options system which allow to configure many enhancements like enable/disable: colors, 5Ghz band, auto updates, hint printing, etc.
- Full compatibility with iptables and nftables with autodetection and possibility to force iptables by setting an option
- Available plugins system to let the community create their own content in an easy and flexible way using the created function hooking system. More info at [Plugins System] section

<!-- Anchors -->
[Requirements]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Requirements
[Supported Languages]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Supported%20Languages
[Docker]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Docker
[Docker Hub]: https://hub.docker.com/r/v1s1t0r1sh3r3/airgeddon/
[Plugins System]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20System