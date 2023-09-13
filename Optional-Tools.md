#### Not necessary to work, only needed for some features

 Command      | Possible package name    | &#8901; | Command       | Possible package name                                
:-------------|:-------------------------|:-------:|:-------------:|:-----------------------------------------------------
 wpaclean     | aircrack-ng              | &#8901; | ettercap      | ettercap \| ettercap-text-only \| ettercap-graphical 
 crunch       | crunch                   | &#8901; | etterlog      | ettercap \| ettercap-text-only \| ettercap-graphical 
 aireplay-ng  | aircrack-ng              | &#8901; | tshark        | tshark \| wireshark-cli                              
 mdk3/mdk4    | mdk3/mdk4                | &#8901; | dhcpd         | isc-dhcp-server \| dhcp-server \| dhcp               
 hashcat      | hashcat                  | &#8901; | dnsmasq       | dnsmasq                                              
 hostapd      | hostapd                  | &#8901; | wash/reaver   | reaver                                               
 lighttpd     | lighttpd                 | &#8901; | tcpdump       | tcpdump                                              
 nft/iptables | nftables/iptables        | &#8901; | bully         | bully                                                
 bettercap    | bettercap                | &#8901; | pixiewps      | pixiewps                                             
 beef         | beef-xss \| beef-project | &#8901; | asleap        | asleap                                               
 hostapd-wpe  | hostapd-wpe              | &#8901; | openssl       | openssl                                              
 hcxdumptool  | hcxdumptool              | &#8901; | hcxpcapngtool | hcxtools                                             

Appropriate checks are done at the beginning to determine if you are able to use some features. Optional but recommended to have. `airgeddon` will block the ability to use some features if the needed optional tool is not present.