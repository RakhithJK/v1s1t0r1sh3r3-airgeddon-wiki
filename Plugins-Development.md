## This section is still under construction until v10.0 is released

### Plugins Development

First of all, to understand what is discussed on this Section, is mandatory to read first the section called [Plugins System]. Otherwise you'll miss the basics and probably will not understand what is explained here. On that section there is a simple explanation and an overview about how the plugins system works. **After reading that, you can continue reading here...**

On this Wiki section, we assume you've read the overview and you know about the existence of the different "hooking" methods.

Here, we'll provide the needed info to be able to create a custom plugin for `airgeddon`. The explanations will be based on an example plugin which was already created and is existing on this repository. The plugin was created as a PoC (Proof Of Concept) about how to develop a plugin. It is called [Missing Dependencies] and it is included directly into `airgeddon`. You can check it anytime if you have doubts about how a plugin should be developed. It is available from `airgeddon>=10.0`.

#### 1. Where to start

A plugin creation template will be provided in order to ease the task. The [Plugin Creation Template] can be used as "skeleton" of your plugin. Rename or copy it to any other name on the same plugins directory keeping the _.sh_ extension.

The plugin template contains detailed instructions about how to proceed. Read them carefully. It is separated by sections.

#### 2. Sections of the Plugin Template

##### 2.1 Generic Plugin Vars

First lines of the template are to set some basic vars. The description of each one is self explanatory:

```
###### GENERIC PLUGIN VARS ######

plugin_name="Set your plugin name here"
plugin_description="Set a short description of your plugin"
plugin_author="Set your nick/name here"

#Enabled 1 / Disabled 0 - Set this plugin as enabled - Default value 1
plugin_enabled=1
```

Each plugin can be enabled/disabled setting `plugin_enabled` var to `1`or `0`, but bear in mind that the plugins system can be enabled/disabled globally using the `AIRGEDDON_PLUGINS_ENABLED` option. More info at Wiki [Options Section].

___

##### 2.2 Plugin Requirements

This section will be used to set some requirements for the plugin. It means that the plugin will be active only if the requirements are met. This is useful to apply plugin effects only to some `airgeddon` versions or to a concrete Linux distribution:

```
###### PLUGIN REQUIREMENTS ######

#Set airgeddon versions to apply this plugin (leave blank to set no limits, minimum version recommended is 10.0 on which plugins feature was added)
plugin_minimum_ag_affected_version="10.0"
plugin_maximum_ag_affected_version=""

#Set only one element in the array "*" to affect all distros, otherwise add them one by one with the name which airgeddon uses for that distro (examples "BlackArch", "Parrot", "Kali")
plugin_distros_supported=("*")
```

The complete list of the available Linux distributions can be found in `airgeddon.sh` file at arrays called `known_compatible_distros` and `known_arm_compatible_distros`.

___

##### 2.3 Custom Functions

The explanation of this section is simple. It's just to create your new custom functions. We must differentiate between new custom functions and "hooked" functions (explained on the next section). 

```
###### CUSTOM FUNCTIONS ######

#Just create here new custom functions if they are needed
#They can be called from the plugin itself. They are different than the "hooked" functions (explained on the next section)
```

This section can be avoided if you only need to hook functions.

___

##### 2.4 Function Overriding (first kind of "hooking")

This kind of hooking will prevent the original code from an `airgeddon` function to be executed. The defined code here will be executed instead.

```
Under construction
```

___

##### 2.5 Function Prehooking (second kind of "hooking")

```
Under construction
```

___

##### 2.6 Function Posthooking (third kind of "hooking")

```
Under construction
```

___

#### 3. Troubleshooting

Here you can find some tips about how to get helped on development.

##### 3.1 Security Mechanisms and Validations

`airgeddon` has some mechanisms to avoid errors during plugins development. It can detect if you try to "hook" a non existing function and an error will be shown.

If you try to "hook" to perform same action over a function (prehook for example) from two different plugins, `airgeddon` will show you an error alerting to you about that untenable situation.

##### 3.2 Help on Development

If you have problems during your plugin development, please consider to contact us on [IRC] or [Discord] channel. More info at Wiki [Contact Section]. The staff can guide you or give you advice about what to do or which function should be modified for your plugin, but in anycase we are going to develop for you.

**Don't open an issue for this! Remember that we are not going to teach you about how to be a developer!**

[Missing Dependencies]: https://github.com/v1s1t0r1sh3r3/airgeddon/blob/dev/plugins/missing_dependencies.sh
[Plugins System]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20System
[Plugin Creation Template]: https://github.com/v1s1t0r1sh3r3/airgeddon/blob/dev/plugins/plugin_template.sh
[Options Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Options
[Contact Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Contact
[Discord]: https://discord.gg/sQ9dgt9
[IRC]: https://webchat.freenode.net/