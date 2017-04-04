`airgeddon` is a live project growing day by day. This is the list of features so far:
<!-- Each sub list needs 2 additional followed spaces -->
- Interface mode switcher (Monitor-Managed) keeping selection even on interface name changing
- DoS over wireless networks using different methods
- Assisted Handshake file capturing
- Cleaning and optimizing Handshake captured files
- Offline password decrypting on WPA/WPA2 captured files (dictionary, bruteforce and rule based)
- Evil Twin attacks (Rogue AP)
  - Only Rogue/Fake AP version to sniff using external sniffer (Hostapd + DHCP + DoS)
  - Simple integrated sniffing (Hostapd + DHCP + DoS + Ettercap)
  - Integrated sniffing, sslstrip (Hostapd + DHCP + DoS + Ettercap + Sslstrip)
  - Integrated sniffing, sslstrip2 and BeEF browser exploitation framework (Hostapd + DHCP + DoS + Bettercap + BeEF)
  - Captive portal with "DNS blackhole" to capture wifi passwords (Hostapd + DHCP + DoS + Dnsspoff + Lighttpd)
  - Optional MAC spoofing for all Evil Twin attacks
- WPS features
  - WPS scanning (wash). Self parameterization to avoid *"bad fcs"* problem
  - Custom PIN association (bully and reaver)
  - Pixie Dust attacks (bully and reaver)
  - Bruteforce PIN attacks (bully and reaver)
  - Parameterizable timeouts
  - Known WPS PINs attack (bully and reaver), based on online PIN database with auto-update
  - Integration of the most common PIN generation algorithms
- WEP All-in-One attack (combining different techniques: Chop-Chop, Caffe Latte, ARP Replay, Hirte, Fragmentation, Fake association, etc.)
- Compatibility with many Linux distributions (see [Requirements] section)
- Easy targeting and selection in every section
- Drag and drop files on console window for entering file paths
- Dynamic screen resolution detection and windows auto-sizing for optimal viewing
- Controlled Exit. Cleaning tasks and temp files. Option to keep monitor mode if desired
- Multilanguage support and autodetect OS language feature (see [Supported Languages] section)
- Help hints in every zone/menu for easy use
- Auto-update. Script checks for newer version if possible
- Docker container for easy and quick deployment

<!-- Anchors -->
[Requirements]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Requirements
[Supported Languages]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Supported%20Languages