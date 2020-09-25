# Introduction

StaffPlusPlus implemented a new reporting system. The new system is a bit different from the old StaffPlus reporting system.
We now support reporting online and offline players. Reporting events can be triggered to discord using the StaffPlusPlus Discord Integration plugin. Below I will explain how to set up and use the reporting system.

## Configuration

The configuration is pretty self-explanatory.
Make sure you have this section inside your configuration file and enable the reporting module by setting `enabled` to `true`

```
# No permission required for regular users, requires "permissions.report" permission for moderator commands.
reports-module:
  # Whether or not the plugin will use "/report" features.
  enabled: true

  # The sound that is played to staff when someone is reported.
  # Set to "NONE" to disable.
  sound: ORB_PICKUP

  # The cooldown, in seconds, for using "/report".
  # This is disabled for players with the "permissions.report" permission.
  cooldown: 10

  # Whether or not the player that reported another player will be visible in GUIs.
  show-reporter: true

  # Whether or not a staff member must provide a reason when resolving/rejecting a report
  closing-reason-enabled: true
```

## Report commands

* `/reports` Used to manage reports. You can list or clear all the reports of a player
* `/reportplayer [playerName] [message]` Report a specific player.
* `/report [message]` Report something but don't link a specific player to it.

## Report lifecycle

### OPEN
When a report first gets created is get the stats `OPEN`, open reports can be picked up by any staff member with the correct permission.

### IN_PROGRESS
After a staff member picks up a report it gets placed into the status `IN_PROGRESS`. When one member of staff picks up a report no other member can handle this report.

### RESOLVED
A staff member can manage reports assigned to him. If he deems the report to be completely handled he can resolve the report. 
When a report is resolved, other staff members can view it in the closed reports GUI.

### REJECTED
A staff member can manage reports assigned to him. If he deems the report to be incorrect, or spam, or just not enough information he can reject the report. When a report is rejected, other staff members can view it in the closed reports GUI.


[Reporting system video](https://www.youtube.com/watch?v=laP10VM29TM) 