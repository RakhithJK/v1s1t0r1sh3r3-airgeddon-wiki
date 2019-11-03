## This section is still under construction until v10.0 is released

### Plugins Development

First of all, to understand what is discussed on this Section, is mandatory to read first the section called [Plugins System]. Otherwise you'll miss the basics and probably will not understand what is explained here. On that section there is a simple explanation and an overview about how the plugins system works. **After reading that, you can continue reading here...**

On this Wiki section, we assume you've read the overview and you know about the existence of the different "hooking" methods.

Here, we'll provide the needed info to be able to create a custom plugin for `airgeddon`. The explanations will be based on an example plugin which was already created and is existing on this repository. The plugin was created as a PoC (Proof Of Concept) on how to develop a plugin. It is called [Missing Dependencies] and it is included directly into `airgeddon`. You can check it anytime if you have doubts about how a plugin should be developed. It is available from `airgeddon>=10.0`.

#### 1. Where to start

A plugin creation template will be provided in order to ease the task. The [Plugin Creation Template] can be used as a "skeleton" of your plugin. Rename or copy it to any other name on the same plugins directory keeping the _.sh_ extension.

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

##### 2.4 Function Hooking: Override

This kind of hooking will prevent the original code from an `airgeddon` function to be executed. The defined code here will be executed instead.

```
###### FUNCTION HOOKING: OVERRIDE ######

#To override airgeddon functions, just define them following this nomenclature name: <plugin_short_name>_override_<function_name>
#plugin_short_name: This is the name of the plugin filename without extension (.sh)
#function_name: This is the name of the airgeddon function you want to rewrite with new content

#Overridden function example
#This will replace an existing function in main airgeddon script to change its behavior in order to execute this content instead of the original
#In this template the existing function is called "somefunction" but of course this is not existing in airgeddon. You should replace "somefunction" with the real name of the function you want to override
#Remember also to modify the starting part of the function "plugin_template" to set your plugin short name (filename without .sh) "my_super_pr0_plugin" if you renamed this template file to my_super_pr0_plugin.sh
#Example name: function my_super_pr0_plugin_override_set_chipset() { <- this will override the content of the chosen function
function plugin_template_override_somefunction() {

	echo "Here comes my custom code content which will replace the original source code of the overridden function"
}
```

___

##### 2.5 Function Hooking: Prehook

Using prehooking, the custom code will be executed just before the target function execution.

```
###### FUNCTION HOOKING: PREHOOK ######

#To prehook airgeddon functions, just define them following this nomenclature name: <plugin_short_name>_prehook_<function_name>
#plugin_short_name: This is the name of the plugin filename without extension (.sh)
#function_name: This is the name of the airgeddon function where you want to launch your stuff before

#Prehook function example
#This will execute this content before the chosen function
#In this template the existing function is called "somefunction" but of course this is not existing in airgeddon. You should replace "somefunction" with the real name of the function you want to prehook
#Remember also to modify the starting part of the function "plugin_template" to set your plugin short name (filename without .sh) "my_super_pr0_plugin" if you renamed this template file to my_super_pr0_plugin.sh
#Example name: function my_super_pr0_plugin_prehook_clean_tmpfiles() { <- this will execute the custom code just before executing the content of the chosen function
function plugin_template_prehook_somefunction() {

	echo "Here comes my custom code which will be executed just before starting to execute the content of the chosen function"
}
```

___

##### 2.6 Function Hooking: Posthook

Using posthooking, the custom code will be executed just after the target function execution.

```
###### FUNCTION HOOKING: POSTHOOK ######

#To posthook airgeddon functions, just define them following this nomenclature name: <plugin_short_name>_posthook_<function_name>
#plugin_short_name: This is the name of the plugin filename without extension (.sh)
#function_name: This is the name of the airgeddon function where you want to launch your stuff after

#Posthook function example
#This will execute this content just after the chosen function
#In this template the existing function is called "somefunction" but of course this is not existing in airgeddon. You should replace "somefunction" with the real name of the function you want to posthook
#Remember also to modify the starting part of the function "plugin_template" to set your plugin short name (filename without .sh) "my_super_pr0_plugin" if you renamed this template file to my_super_pr0_plugin.sh
#Example name: function my_super_pr0_plugin_posthook_clean_tmpfiles() { <- this will execute the custom code just after executing the content of the chosen function
function plugin_template_posthook_somefunction() {

	echo "Here comes my custom code which will be executed just after finish executing the content of the chosen function"
}
```

__Important notes about returning codes on posthooking__

If the function you are posthooking has a returning code, that value is available on the posthook function as `${1}`. The return done on the posthook function will be the final return value for the function. If there is no return value on the posthook function, then the return value will be the original one.

___

#### 3. Troubleshooting

Here you can find some tips about how to get help on development.

##### 3.1 Security Mechanisms and Validations

`airgeddon` has some mechanisms to avoid errors during plugins development. It can detect if you try to "hook" a non existing function and an error will be shown.

If you try to "hook" to perform same action over a function (prehook for example) from two different plugins, `airgeddon` will show you an error alerting you about that untenable situation.

Remember that it is a good practice to always encode your plugin file using UTF-8 and keeping Linux ending lines style (use _LF_ and never _CRLF_). If you edit your `.sh` plugin file from Windows O.S. maybe you could be using _CRLF_ as line ending line style and of course that will generate errors during the execution. It's recommended to develop using Linux O.S. to avoid errors.

##### 3.2 Help on Development

If you have problems during your plugin development, please consider to contact us on [IRC] or [Discord] channel. More info at Wiki [Contact Section]. The staff can guide you or give you advice about what to do or which function should be modified for your plugin, but in no case we are going to develop for you.

**Don't open an issue for this! Remember that we are not going to teach you about how to be a developer!**

[Missing Dependencies]: https://github.com/v1s1t0r1sh3r3/airgeddon/blob/dev/plugins/missing_dependencies.sh
[Plugins System]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Plugins%20System
[Plugin Creation Template]: https://github.com/v1s1t0r1sh3r3/airgeddon/blob/dev/plugins/plugin_template.sh
[Options Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Options
[Contact Section]: https://github.com/v1s1t0r1sh3r3/airgeddon/wiki/Contact
[Discord]: https://discord.gg/sQ9dgt9
[IRC]: https://webchat.freenode.net/