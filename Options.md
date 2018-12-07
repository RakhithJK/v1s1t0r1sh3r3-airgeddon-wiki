 From `airgeddon>=9.0` a new options system is available. It is based on bash substitution fallback environment vars. Options can be set in three different ways:

 - From the `.airgeddonrc` file

Any variable available on this file can be changed to alter the behavior of the script. Changes on this file will take effect on next launch.

 - From the options menu

Any change done from the menu is applied instantly.

 - Using "_on the fly_" flags on command line

The changes on the options set on the command line will apply only for that session and they will override the settings on `.airgeddonrc` file.
