## Overview

|Command|Description|Available Arguments|Example usages|
|---|---|---|---|
|`/staff`|Turns on/off Staff mode for the current user. Only available if the user has the correct permissions.||`/staff`|
|`/freeze`|Freezes/unfreezes a player. Either you specify enabled/disabled or you just freeze and freezemode will be toggled|`-T` `-S` `-H` `-D`|`/freeze player1` `/freeze enabled player1` `/freeze player1 -Tspawn -S`|
|`/examine`|Opens the examine GUI. The gui can be used to check a players IP address, check his gamemode, etc||`/examine player1`|
|`/notes`|Add/clear/list notes on different players.||`/notes get player1` `/notes clear player1` `/notes player1 This is a note`|
|`/cps`|Run a clicks per second test on a player||`/cps player1`|
|`/sc`|Enables/disables staffchat. All messages send in staff chat mode will only be readable by other staff members||`/sc`|
|`/reports`|Command used by staff to manage reports: list current reports or remove all player reports||`/reports get player1`|
|`/report`|Command to report something. Used when the player wants to report something but doesn't know who was the culprit or there was no culprit||`/report Some reason`|
|`/reportPlayer`|Command for players to report another player||`/reportPlayer player1 For some reason`|
|`/warn`|Command to give a player a warning. Severity should be configured inside the configuration file and provided as first argument to the warn command||`/warn MAJOR player1 For some reason`|
|`/warns`|Command to manage warnings. You can list current warnings or remove all player warnings||`/warns clear player1` `/warns get player1`|
|`/vanish`|Toggle vanish on/off||`/vanish`|
|`/chat`|Manage in game chat. Disable/Enable chat completely. Clear the chat history. Enable slow chat||`/chat clear` `/chat toggle` `/chat slow`|
|`/ticket`|This system is not working properly. Will be updated in the next releases||`Do not use`|
|`/alerts`|Subscribe/Unsubscribe yourself to be notified when certain events happen in StaffPlusPlus. Currently following events are supported: XRAY, MENTION, NAME_CHANGE||`/alerts player1 NAME_CHANGE`|
|`/follow`|Start following a player. This will attach you to the player and follow him where he goes||`/follow player1`|
|`/revive`|Revive let's you restore a player's inventory after a players has died.|`-T` `-S` `-H`|`/revive player1`|
|`/personnel`|Lists online staff members||`/personnel`|
|`/strip`|Takes off the player's armor and places it in his inventory. If there are no free spaces left in the player's inventory the armor is not taken off.||`/strip player1`|
|`/clear`|Clear the given player's inventory|`-T` `-H` `-D`|`/clear player1`|
|`/teleport`|Teleports a player to a given location. Location should be configured inside the configuration file|`-D`|`/teleport player1 spawn`|

## Arguments
StaffPlusPlus supports an argument system which can be used to enhance the default commands.
We list below the arguments we currently support.
In the commands table you can see which commands can use which arguments

### -T Teleport
Teleport let's us enhance a command by teleporting the target to a predefined location.
You can setup locations in the configuration file. See **Locations**

Example:
`/freeze player1 -Tspawn`

Description:
Teleports player1 to the predefined location "spawn" and immediately freezes him.

### -S Strip
-S does the same as the strip command:
Takes off the player's armor and places it in his inventory. If there are no free spaces left in the player's inventory the armor is not taken off.

Example:
`/freeze player1 -S`

Description:
Freezes the player and strips his armor.

### -H Health
Sets the player's health to the given percentage.

Example:
`/freeze player1 -H100`

Description:
Freezes the player and gives the player full health.

### -D Delay a command
When provided with a base command. The command will be delayed until the player joins the server.
This is useful when we want to for example clear the inventory of a player, but he's offline. With the -D argument we can still run the 'clear' command.
It will not be executed immediately, but it will be executed the next time the player joins the server. 

Example:
`/clear player1 -D`

Description:
Clear the players inventory the next time he joins the server