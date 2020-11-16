# Introduction

Staff++ re-enabled to "reload" command. The reload command allows reloading the configuration file.
However the reload command is still in an experimental phase. So keep below warnings in mind when executing it.

## Warnings
When executing the reload, player sessions won't be reverted. This means that for example if we disable the freeze command and reload the configuration
the freeze command will no longer work. **But players that were frozen before reloading, will remain frozen.**

When we are changing staff mode configuration it's preferable that staff members exit staff mode before reloading. Staff members that are in staff mode won't see all the config changes made to until they exit and re-enter.

Changing the database connection parameters and reloading does not reset the database connection. To do so a restart is still required.

## Known issues
- Autocompletion of the commands does not change when reloading. The commands do no longer work but it's possible players will still see the commands being autocompleted.