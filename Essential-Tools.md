#### The script doesn't work if you don't have installed all of them

 Command     | Possible package name | &#8901; | Command     | Possible package name           
:------------|:----------------------|:-------:|:------------|:--------------------------------
 iw          | iw                    | &#8901; | awk         | awk \| gawk                     
 airmon-ng   | aircrack-ng           | &#8901; | airodump-ng | aircrack-ng                     
 aircrack-ng | aircrack-ng           | &#8901; | xterm       | xterm                           
 ip          | iproute2              | &#8901; | tmux        | tmux                            
 ps          | procps \| procps-ng   | &#8901; |             |                                  

Without the tools above, airgeddon **won't work** at all.
Appropriate checks are done at the beginning, if you have those tools installed, you will be able to use airgeddon.

**NOTE**: Regarding xterm and tmux, only one of them is really needed. `airgeddon` will use only one of them, which you configure in its options file and only the selected one will be validated on dependency checks. Options file can be located as _.airgeddonrc_ usually in the same dir as the main script but for some distros like Pentoo it is located at _/etc/airgeddonrc_.