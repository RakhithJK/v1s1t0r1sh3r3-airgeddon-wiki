### Plugins System

The plugins system is a new ambitious feature to provide to users the ability to perform custom modifications on `airgeddon` in an easy and quick way. It is available from `airgeddon>=10.0`.

It is based on a "hook" system which can be used to modify parts of airgeddon with custom content to enhance or create features.

#### Basic Overview

Existing files with **.sh** extension inside _plugins_ dir will be parsed and treated as a plugin. Only a file called `plugin_template.sh` will be ignored. The reason is that this file is not a real plugin, it's just a template to be used for plugins development. Plugins dir can be located as `plugins/` usually at the same dir as the main script but for some distros like Pentoo alternatively can be located at `$HOME/.airgeddon/plugins/`.

There are three basic "hooking" operations:
 - Prehooking a function: this will execute code before target function starts its execution
 - Overriding a function: this will execute code instead of the original target function thereby completely replacing it
 - Posthooking a function: this will execute right after the target function finishes its execution

So basically, to create a plugin, you should follow these three steps:

1. The plugin developer should choose which airgeddon function from the main script should be modified. To know that, it would be a good idea to use the debug mode available at options `AIRGEDDON_DEBUG_MODE=true` in order to identify the function to be hooked and modified to achieve desired enhancement or feature. More info about how to use this option at [Wiki Options Section].
2. After selecting a function to interact with, the developer should decide which action will take over that function (prehook, override, posthook).
3. Then, create the function, "hooking" it inside the plugin file.

#### Can I develop a plugin using other programming languages?

Sure you can! just follow the steps to add a plugin adding the bash template and then from bash file you can perform calls to external stuff in python, ruby or whatever.

#### How can I install a plugin already done by somebody?

Easy task, just take the `.sh` file and place it at plugins dir. Be sure that the plugin will match your airgeddon version and your Linux distribution. You can find that info inside the plugin itself at the beginning of the file set in some vars. This is an example on which a plugin will support only some Linux distributions and airgeddon v10.0 or higher: 

```
plugin_minimum_ag_affected_version="10.0"
plugin_maximum_ag_affected_version=""
plugin_distros_supported=("Kali" "Parrot" "BlackArch")
```

Another example on which a plugin will support only a specific version v10.0 for any Linux:

```
plugin_minimum_ag_affected_version="10.0"
plugin_maximum_ag_affected_version="10.0"
plugin_distros_supported=("*")
```

If the plugin is not supporting your Linux or version it is just ignored.

#### More information

More info and technical details about how to develop a plugin at [Wiki Plugins Development Section].

Best known plugins at [Wiki Plugins Hall of Fame Section].

[Wiki Options Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Options
[Wiki Plugins Development Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20Development
[Wiki Plugins Hall of Fame Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20Hall%20of%20Fame
