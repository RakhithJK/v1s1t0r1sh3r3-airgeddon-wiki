#### These are internally checked. Not necessary to work, good to have

 Command     | Possible package name                  | &#8901; | Command     | Possible package name           
:------------|:---------------------------------------|:-------:|:------------|:--------------------------------
 xdpyinfo    | x11-utils \| xdpyinfo \| xorg-xdpyinfo | &#8901; | ethtool     | ethtool                         
 lsusb       | usbutils                               | &#8901; | rfkill      | rfkill                          
 wget        | wget                                   | &#8901; | ccze        | ccze                            
 xset        | x11-xserver-utils \| xorg-xset         | &#8901; |             |                                 

It is highly recommended to have the internal tools installed. These tools are not checked as validation at the  beginning, `airgeddon` will check internally if they are available before using them. They improve functionality and performance. For example, `xdpyinfo` allows the script to detect the display resolution in order to print on windows in a better way (size and position). Or `ccze`, package that will colorize some outputs for a better user experience.

Of course, the script also uses many standard basic tools that are supposed to be included in any Linux distribution, so they are not checked (`cp`, `rm`, `grep`, `md5sum`, `uname`, `echo`, `hash`, `cat`, `sed`, etc).

##### Important tips about ccze

`ccze` decreases performance. It is NOT recommended for **arm** devices.
  * Version 9.0 or later
    * Disable from menu, now called extended colorization, it can also be disabled setting `AIRGEDDON_EXTENDED_COLORS=false` in options file (check [Options] section for further info)
  * Version 7.2 or later
    * Disable colorization from menu
  * Version 7.11
    * Disable colorization by replacing the flag `allow_colorization=1` with `allow_colorization=0` at the beginning of the script
  * Older versions
    * Colorization feature with `ccze` does not exist

[Options]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Options