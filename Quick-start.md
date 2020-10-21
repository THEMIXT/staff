## Installation

Download the latest version from the Spigot page. https://www.spigotmc.org/resources/staff.83562/history
You should download the version corresponding to your MC version.

Place the jar file inside the plugins folder of your server and start your server. This will create the necessary files in the `plugins/StaffPlus` folder.

## Basic configuration
Open the config.yml file location in the `plugins/StaffPlus` folder. If you mess up the config file you can always take a look at the [default file](https://github.com/garagepoort/StaffPlusPlus/blob/master/StaffPlusCore/src/main/resources/config.yml).

The config file contains the command and permission configuration.
It also contains the different modules configuration. Different functionalities of Staff++ are configured as separate modules which can be enabled or disabled.

These are the modules:

| module| Description | Enabled by default |
|---|---|---|
| reports-module| Allow players to create reports. Staff members can pickup and resolve the reports. | true |
| warns-module| Allow Staff members to warn players. | true |
| staff-chat-module | Enable staffchat | true |
| vanish-module | Allow staffmembers to vanish | true |
| chat-module | Enable StaffMembers to slow or clear chat. Allow blacklisting certain words | true |
| broadcast-module | Enable StaffMembers broadcast messages. | true |
| ban-module | Enable StaffMembers to /ban or /tempban players. | true |
| protect-module | Enable StaffMembers to protect players or areas from damage. | true |
| alt-detect-module | Enable an alt account detection system. | false |
| alerts-module | Enable an alerting system. This can notify staff members in-game when certain events transpire. | true |
| trace-module | Enable Staff members to start a trace on a player. This records actions the specified player is executing | true |

## Database configuration
We support 2 types of database `sqlite` and `mysql`. By default `sqlite` is configured.
If you want to use mysql database configuration change this part of the config file:

```yaml
storage:
  type: 'mysql'
  mysql:
    host: 'localhost'
    user: 'root'
    database: 'root'
    password: 'mypass'
    port: 3306
```

## Adding players as Staff Members
There is not one command to add players as Staff members. Everything in Staff++ is permission based, if you have the correct permissions you can access the Staff++ commands. If you are OP you can access all commands by default.

All permissions are listed [here](https://github.com/garagepoort/StaffPlusPlus/wiki/Permissions).
This means you need some permission plugin to enable staff mode for your staff members. A commonly used permissions plugins is [luckperms](https://www.spigotmc.org/resources/luckperms.28140/).

Once you have installed the permission plugin you can assign your player the correct permissions.
All permissions in Staff++ start with a 'staff.' prefix. luckperms supports wildcards so you could give your player the permission `staff.*` and it will enable all Staff++ permissions for that player.