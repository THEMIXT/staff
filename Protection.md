# Introduction

The protection system allows a Staff Member to protect a player or protect an entire area.

## Configuration
Inside the config file make sure this section is added:

```
############################################################
# +------------------------------------------------------+ #
# |                      Protection                      | #
# +------------------------------------------------------+ #
############################################################

protect-module:
  # Whether or not the plugin will use "/protectplayer" features.
  player-enabled: true
  # Whether or not the plugin will use "/protectarea" features.
  area-enabled: true
  # The max area size that can be protected.
  area-max-size: 40
```

## Protecting a player
This is pretty simple. `/protectplayer playername` toggles protection for a player, when protected the player takes no damage at all.
Protection wears off after the players logs out or if the staff members turns it off.

## Protecting an area
A Staff member can decide to quickly protect an area from non Staff Members. This can be useful when something needs to be investigated.
Once protection for an area is turned on, players cannot open chests, break blocks, place blocks, press buttons, switch levers, place water/lava.
In general we try to protect everything inside the area from other players. If the feature is useful we can see if other protection measures must be taken.

To protect an area type `/protectarea create 40 My new area`. 
- action: create
- size: a square of 40x40
- name: My new area
- The center point of the area is where you are standing.

To delete a protected `/protectarea delete My new area`. 
- action: delete
- name: My new area

### Staff Mode
In addition to the command line tool. There is also an overview of protected areas when in staff mode.

#### This can be accessed through the GUI HUB:
[[/images/protect_hub.png|Protected area hub screen]]

#### All areas are displayed here:
[[/images/protect_overview.png|Protected area overview screen]]

#### When clicking on an item we can delete(red) the protected area or teleport(orange) to it.
[[/images/protect_manage.png|Protected area manage screen]]

