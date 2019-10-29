## This section is still under construction until v10.0 is released

### Plugins Development

First of all, to understand what is discussed on this Section, is mandatory to read first the section called [Plugins System]. Otherwise you'll miss the basics and probably will not understand what is explained here. On that section there is a simple explanation and an overview about how the plugins system works. **After reading that, you can continue reading here...**

On this Wiki section, we assume you've read the overview and you know about the existence of the different "hooking" methods.

Here, we'll provide the needed info to be able to create a custom plugin for `airgeddon`. The explanations will be based on an example plugin which was already created and is existing on this repository. The plugin was created as a PoC (Proof Of Concept) about how to develop a plugin. It is called [Missing Dependencies] and it is included directly into `airgeddon`. You can check it anytime if you have doubts about how a plugin should be developed. It is available from `airgeddon>=10.0`.

#### Where to start

A plugin creation template will be provided in order to ease the task. The [Plugin Creation Template] can be used as "skeleton" of your plugin. Rename or copy it to any other name on the same plugins directory keeping the _.sh_ extension.

The plugin template contains detailed instructions about how to proceed. Read them carefully. It is separated by sections.

#### Sections of the Plugin Template

First lines of the template are to set some basic vars which will be used by the plugin or to disable it (so each plugin can be enabled/disabled setting `plugin_enabled` var):

```
###### GENERIC PLUGIN VARS ######

plugin_name="Set your plugin name here"
plugin_description="Set a short description of your plugin"
plugin_author="Set your nick/name here"

#Enabled 1 / Disabled 0 - Set this plugin as enabled - Default value 1
plugin_enabled=1
```

Then, next section will be used to set some requirements for the plugin. It means that the plugin will be active only if the requirements are met:

```
###### PLUGIN REQUIREMENTS ######

#Set airgeddon versions to apply this plugin (leave blank to set no limits, minimum version recommended is 10.0 on which plugins feature was added)
plugin_minimum_ag_affected_version="10.0"
plugin_maximum_ag_affected_version=""

#Set only one element in the array "*" to affect all distros, otherwise add them one by one with the name which airgeddon uses for that distro (examples "BlackArch", "Parrot", "Kali")
plugin_distros_supported=("*")
```

Next section is just to create your new custom functions. We must differentiate between new custom functions and "hooked" functions. 

```
###### CUSTOM FUNCTIONS ######

#Just create here new custom functions if they are needed
#They can be called from the plugin itself. They are different than the "hooked" functions (explained on the next section)
```

## Under construction


[Missing Dependencies]: https://github.com/v1s1t0r1sh3r3/airgeddon/blob/dev/plugins/missing_dependencies.sh
[Plugins System]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20System
[Plugin Creation Template]: https://github.com/v1s1t0r1sh3r3/airgeddon/blob/dev/plugins/plugin_template.sh