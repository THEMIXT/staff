# Introduction

We introduced new teleport commands. These very basic commands can be used to teleport yourself or other players.

## Configuration 

Make sure the following section is present in your configuration file:

```yaml
############################################################
# +------------------------------------------------------+ #
# |                       Locations                        | #
# +------------------------------------------------------+ #
############################################################
# Used to predefine certain locations in the world which can be used in other commands
# Type in the location identifier and location using format: x;y;z
# ex. config
# locations:
#     spawn: 14;45;62
# ex. /freeze myplayer -Tspawn
# This will freeze the player and teleport him to spawn location.
locations:
```

You can define multiple locations underneath the `locations` section.
Example:
```yaml
locations:
     spawn: 14;45;62
     jail: 58,789,70
```

## Commands:

##### Teleport a player to a location:

The `teleportToLocation` command can also be used as an argument `-T` to enhance other commands.

```
/teleportToLocation thatplayer spawn
```

##### Teleport yourself to a player:

```
/teleportToPlayer thatplayer
```

##### Teleport a player to your location:

```
/teleportHere thatplayer
```

##### Teleport a player back to his original location:
This only works if the player has been teleported at least ones before.
Previous locations are lost when the server restarts.
```
/teleportBack thatplayer
```