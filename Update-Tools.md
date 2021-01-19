#### Not necessary to work, only used for auto-update

 Command | Possible package name
:--------|:----------------------
 curl    | curl                  

airgeddon uses `curl` to update itself and to update also the WPS PIN database. It will be checked at the beginning to determine if updates are possible. It's not mandatory to have it but it's highly recommended.

##### Important tips about curl and auto-update

Binary packages have the auto-update feature disabled. The package manager of your distribution, will take care of the updates. 