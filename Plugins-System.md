## This section is still under construction until v10.0 is released

### Plugins System

The plugins system is an ambitious feature to provide to users the ability to perform custom modifications to `airgeddon` in an easy and quick way. It is available from `airgeddon>=10.0`.

It is based in a "hook" system which can be used to modify parts of airgeddon with custom content to enhance or create features.

#### Basic Overview

Existing files with **.sh** extension inside _plugins_ dir will be parsed an treated as a plugin. Only a file called `plugin_template.sh` will be ignored. The reason is this file is not a real plugin, just a template to be used for plugins development.

There are three basic operations:
 - Prehooking a function: this will execute code before target function start its execution
 - Overriding a function: this will execute code instead of the original target function
 - Posthooking a function: this will execute after target function finish its execution

So basically, as a first step, the plugin developer should choose which airgeddon function from the main script want to modify. To know that, is a good idea to use the debug mode available at options `AIRGEDDON_DEBUG_MODE=true` in order to identify the function that applies to the desired part of the script. More info about how to use this at [Wiki Options Section]. After selecting a function to interact with, the developer should decide wich action will take over that function (prehook, override, posthook) and then create the appropiate function inside the plugin file.

#### More information

More info and technical details about how to develop a plugin at [Wiki Plugins Development Section].

Best known plugins at [Wiki Plugins Hall of Fame Section]

[Wiki Options Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Options
[Wiki Plugins Development Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20Development
[Wiki Plugins Hall of Fame Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20Hall%20of%20Fame
