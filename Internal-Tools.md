#### Internal tools &#8592; These are internally checked. Not necessary to work, good to have

 Command  | Possible package name                  
:---------|:---------------------------------------
 xdpyinfo | x11-utils \| xdpyinfo \| xorg-xdpyinfo
 ethtool  | ethtool                                
 lspci    | pciutils                               
 rfkill   | rfkill                                 

It is highly recommended to have the internal tools installed. They improve functionality and performance. For example, `xdpyinfo` allows the script to detect the display resolution in order to print on windows in a better way (size and position).

Of course, the script also uses many standard basic tools that are supposed to be included in any Linux distribution, so they are not checked (cp, rm, grep, pgrep, egrep, md5sum, uname, echo, hash, cat, sed, etc.).

A command could be included in different packages, depending on the distribution.