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