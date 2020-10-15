# Introduction
Staff++ overrides the default ban command with its own `ban` command. Next to the permanent ban command it also adds the `tempban` command.
With every ban a reason must be given why this player is getting banned.

## Configuration
```
ban-module:
  # Whether or not the plugin will use Staff++ "/ban" features.
  enabled: true
```

## Integration
The [discord integration](https://github.com/garagepoort/StaffPlusPlus/wiki/Discord-Integration) plugin supports notifying to a discord channel whenever a player gets banned/unbanned.

## Examples

### Permanent banning
`/ban [player] [reason]`
```
/ban playername He was bothering me


```

### Temporary banning
`/tempban [player] [amount] [unit] [reason]`
```
/tempban playername 15 MINUTE He was bothering me
```
The duration of the tempban is specified by [amount] [unit]

Amount must be a positive number > 0 and unit must be one of the following:
- SECOND
- MINUTE
- HOUR
- DAY
- WEEK
- MONTH
- YEAR

### Unbanning
`/unban [player] [reason]`
```
/unban playername We are friends now
```

## Another plugin is overriding the `/ban`, `/tempban`
It is possible that another plugin like 'essentialsx' might get priority over the `ban` and `tempban` command.
To prevent this we suggest the same solution as is proposed by [EssentialsX](https://github.com/EssentialsX/Essentials/wiki/Common-Issues#essentialsx-overrides-a-command-from-spigot-or-another-plugin). 

Configure your server aliases in such a way that the ban commands from Staff++ will always be used.
This can be done by editing the `commands.yml` file and specifying your aliases there.

To enable Staff++ ban commands this would be done in this way:
```
aliases:
    ban:
    - "staffplus:ban $1-"
    tempban:
    - "staffplus:tempban $1-"
```
More info on the [bukkit wiki](https://bukkit.gamepedia.com/Commands.yml#aliases)

## GUI
Banned players can be listed and unbanned through the gui hub. 

// TODO add screenshots