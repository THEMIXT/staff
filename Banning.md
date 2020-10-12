#Introduction
Staff++ overrides the default ban command with its own `ban` command. Next to the permanent ban command it also adds the `tempban` command.
With every ban a reason must be given why this player is getting banned.

## Configuration
```
ban-module:
  # Whether or not the plugin will use Staff++ "/ban" features.
  enabled: true
```


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

### Unbanning
`/unban [player] [reason]`
```
/unban playername We are friends now
```