#### These are internally checked. Not necessary to work, good to have

 Command  | Possible package name                  
:---------|:---------------------------------------
 xdpyinfo | x11-utils \| xdpyinfo \| xorg-xdpyinfo
 ethtool  | ethtool                                
 lspci    | pciutils                               
 lsusb    | usbutils                               
 rfkill   | rfkill                                 
 wget     | wget                                   
 ccze     | ccze                                   

It is highly recommended to have the internal tools installed. These tools are not checked as validation at the beginning, `airgeddon` will check internally if they are available before using them. They improve functionality and performance. For example, `xdpyinfo` allows the script to detect the display resolution in order to print on windows in a better way (size and position). Or ccze, package that will colorize some outputs for a better user experience.

Of course, the script also uses many standard basic tools that are supposed to be included in any Linux distribution, so they are not checked (cp, rm, grep, pgrep, egrep, md5sum, uname, echo, hash, cat, sed, etc.).

##### Important tips about BeEF

ccze could cause impact in performance. Is not recommended to be used on arm devices. Colorization can be disabled replacing `allow_colorization=1` by `allow_colorization=0` at the beginning of the script.