From `airgeddon>=9.0` a new options system is available. It is based on bash substitution fallback environment vars. Options can be set in three different ways:

#### From the `.airgeddonrc` file

Any variable available on this file can be changed to alter the behavior of the script. Changes on this file will take effect on next launch.

 - Examples

Modifying the file with these settings will disable all colorization and the ascii intro animation will be skipped on next launch.
```
AIRGEDDON_BASIC_COLORS=false
AIRGEDDON_SKIP_INTRO=true
```

#### Using "_on the fly_" flags on command line

The changes on the options set on the command line will apply only for that session and they will override the settings on `.airgeddonrc` file.

 - Examples

Setting these flags on the command line, there will be no updates for airgeddon and 5Ghz will be disabled on next launch.
```
~/airgeddon# AIRGEDDON_AUTO_UPDATE=false AIRGEDDON_5GHZ_ENABLED=false bash airgeddon.sh
```
 
#### From the options menu

Any change done from the menu is applied instantly. No examples required, menus are intuitive.

## List of available options

```
#Enabled true / Disabled false - Auto update feature (it has no effect on development mode) - Default value true
AIRGEDDON_AUTO_UPDATE=true

#Enabled true / Disabled false - Skip intro (it has no effect on development mode) - Default value false
AIRGEDDON_SKIP_INTRO=false

#Enabled true / Disabled false - Allow colorized output - Default value true
AIRGEDDON_BASIC_COLORS=true

#Enabled true / Disabled false - Allow extended colorized output (ccze needed, it has no effect on disabled colors) - Default value true
AIRGEDDON_EXTENDED_COLORS=true

#Enabled true / Disabled false - Auto change language feature - Default value true
AIRGEDDON_AUTO_CHANGE_LANGUAGE=true

#Enabled true / Disabled false - Dependencies, root and bash version checks are done silently (it has no effect on development mode) - Default value false
AIRGEDDON_SILENT_CHECKS=false

#Enabled true / Disabled false - Print help hints on menus - Default value true
AIRGEDDON_PRINT_HINTS=true

#Enabled true / Disabled false - Enable 5Ghz support (it has no effect if your cards are not 5Ghz compatible cards) - Default value true
AIRGEDDON_5GHZ_ENABLED=true

#Enabled true / Disabled false - Development mode for faster development skipping intro and all initial checks - Default value false
AIRGEDDON_DEVELOPMENT_MODE=false

#Enabled true / Disabled false - Debug mode for development printing debug information - Default value false
AIRGEDDON_DEBUG_MODE=false
```
##### Important note. The last two options `AIRGEDDON_DEVELOPMENT_MODE`and `AIRGEDDON_DEBUG_MODE` are special. Their purpose is development so they are not present on menus to be set. They can be set only modifying the `.airgeddonrc` file or using command line flags.
