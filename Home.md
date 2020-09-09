# Staff++ Documentation

## Introduction
I created this repository as an attempt to add new features to StaffPlus and revitalize it.
The first difference from StaffPlus is that I dropped support for the older versions, this will hopefully allow me to add new features to the newer version easily and help in bug fixing more targeted.

## Configuration

An example of the config file is always present in the repository.
https://github.com/garagepoort/StaffPlusPlus/blob/master/StaffPlusCore/src/main/resources/config.yml

All the properties are explained within the config file but we will list and explain the most important configuration properties here.

## Commands
StaffPlusPlus supports an argument system which can be used to enhance the default commands.
The below table shows which arguments can enhance which commands.

|     | StaffMode  | Freeze  | examine  |  notes |  cps  | staffchat| report | warn  | vanish  | chat | tickets |  alerts  |  follow  | revive  | stafflist | login | register  | strip  | clearInventory  |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| TELEPORT  |   | X  |   |   |   |   |   |   |   |   |   |   | X |   |   |   |   |   | X |
| STRIP     |   |    | X |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |   |