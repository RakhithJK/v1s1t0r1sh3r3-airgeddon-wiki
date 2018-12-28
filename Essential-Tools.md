#### The script doesn't work if you don't have installed all of them

 Command     | Possible package name | &#8901; | Command     | Possible package name           
:------------|:----------------------|:-------:|:------------|:--------------------------------
 ifconfig    | net-tools             | &#8901; | iwconfig    | wireless-tools \| wireless_tools
 iw          | iw                    | &#8901; | awk         | awk \| gawk                     
 airmon-ng   | aircrack-ng           | &#8901; | airodump-ng | aircrack-ng                     
 aircrack-ng | aircrack-ng           | &#8901; | xterm       | xterm                           
 ip          | iproute2              | &#8901; |                                               

Without the tools above, airgeddon **won't work** at all.
Appropriate checks are done at the beginning, if you have those tools installed, you will be able to use airgeddon.