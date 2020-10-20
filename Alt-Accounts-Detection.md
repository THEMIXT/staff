# Introduction
Staff++ provides a way to be notified when it thinks a user is using alternative accounts.
The detection is really simple so don't expect miracles. It will detect the most basic and obvious alt accounts.
Alt detection is disabled by default

## Configuration
```yaml
alt-detect-module:
  enabled: true
```

## How it works

### Ip similarity
When enabled the system will start recording players IP addresses. Every address a player ever connects with gets stored.
If a player connects with the same address as another player his detection score is upped by 1.

### Username similarity
When a player connects we check his username against all other users known to the server.
Similarity is calculated using the Levenshtein Distance Algorithm.
Based on this a score is returned:

- 70% similarity --> score 3
- 50% similarity --> score 2
- 30% similarity --> score 1

### Detection trust levels (score)
The trust level is the result of the above mentioned checks.
We have four levels of trust:

| TrustLevel | score | Description |
|---|---|---|
|POSITIVE|4|Only one case can trigger the POSITIVE level. When a username has an IP match and a username match of at least 70%. We can be fairly certain something is going on with these accounts|
|FAIRLY_POSITIVE|3|Triggered when username match is between 50% and 70% and IP is matching. Or when username match is at least 70% and IP is not matching.|
|POSSIBLE|2|Triggered when username match is between 30% and 50% and IP is matching. Or when username match is between 50% and 70%, and IP is not matching.|
|NOT_LIKELY|1|Triggered when username match is between 30% and 50% and IP is not matching. Or when IP is matching but there is no username similarity. In general I would not recommend listening to alerts with this trustlevel as most likely this will not be a reliable result|

## Listening to events
Currently Staff++ supports 2 ways of being notified when an alt account is detected.
- The [alerting system](https://github.com/garagepoort/StaffPlusPlus/wiki/Alerting-System) (in-game)
- Through Discord ([Integration plugin](https://github.com/garagepoort/StaffPlusPlus/wiki/Discord-Integration))

## Whitelisting Accounts
Since some accounts might actually not be real alt accounts but still trigger the system, a whitelist is added to ensure that staff members can ignore these false positives.

The ignore a match you can use the `/altwhitelist` command.
- `/altwhitelist add playerName1 playerName2`
- `/altwhitelist remove playerName1 playerName2`
- `/altwhitelist list pagenumber` PageNumber is optional.

This will add or remove certain user combinations from the whitelist. When added to the whitelist this users combination will never trigger a detection event.
Adding a combination to the whitelist tells the system that these 2 accounts are not alts.


 