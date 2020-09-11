# Staff++ Documentation

## Introduction
I created this repository as an attempt to add new features to StaffPlus and revitalize it.
The first difference from StaffPlus is that I dropped support for the older versions, this will hopefully allow me to add new features to the newer version easily and help in bug fixing more targeted.

## Configuration

An example of the config file is always present in the repository.
https://github.com/garagepoort/StaffPlusPlus/blob/master/StaffPlusCore/src/main/resources/config.yml

All the properties are explained within the config file but we will list and explain the most important configuration properties here.

## Commands

|Command|Description|Available Arguments|Example usages|
|---|---|---|---|
|`/staff`|Turns on/off Staff mode for the current user. Only available if the user has the correct permissions.||`/staff`|
|`/freeze`|Freezes/unfreezes a player. Either you specify enabled/disabled or you just freeze and freezemode will be toggled||`/freeze player1` `/freeze enabled player1` `/freeze player1 -Tspawn -S`|
|`/examine`|Opens the examine GUI. The gui can be used to check a players IP address, check his gamemode, etc||`/examine player1`|
|`/notes`|Add/clear/list notes on different players.||`/notes get player1` `/notes clear player1` `/notes player1 This is a note`|
|`/cps`|Run a clicks per second test on a player||`/cps player1`|
|`/sc`|Enables/disables staffchat. All messages send in staff chat mode will only be readable by other staff members||`/sc`|
|`/report`|Command to report a player. Staff can also list current reports or remove all player reports||`/report player1 For some reason`|
|`/warn`|Command to give a player a warning. You can also list current warnings or remove all player warnings||`/warn player1 For some reason`|
|`/vanish`|Toggle vanish on/off||`/vanish`|
|`/chat`|Manage in game chat. Disable/Enable chat completely. Clear the chat history. Enable slow chat||`/chat clear` `/chat toggle` `/chat slow`|
|`/ticket`|This system is not working properly. Will be updated in the next releases||`Do not use`|
|`/alerts`|Subscribe/Unsubscribe yourself to be notified when certain events happen in StaffPlusPlus. Currently following events are supported: XRAY, MENTION, NAME_CHANGE||`/alerts player1 NAME_CHANGE`|
|`/follow`|Start following a player. This will attach you to the player and follow him where he goes||`/follow player1`|
|`/revive`|Revive let's you restore a player's inventory after a players has died.||`/revive player1`|
|`/personnel`|Lists online staff members||`/personnel`|
|`/strip`|Takes off the player's armor and places it in his inventory. If there are no free spaces left in the player's inventory the armor is not taken off.||`/strip player1`|
|`/clear`|Clear the given player's inventory||`/clear player1`|

## Arguments
StaffPlusPlus supports an argument system which can be used to enhance the default commands.
The below table shows which arguments can enhance which commands.

|     | StaffMode  | Freeze  | examine  |  notes |  cps  | staffchat| report | warn  | vanish  | chat | tickets |  alerts  |  follow  | revive  | stafflist | login | register  | strip  | clearInventory  |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| TELEPORT  ||X||||||||||||X|||||X|
| STRIP     ||X||||||||||||X||||||