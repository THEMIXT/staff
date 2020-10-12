# Introduction
Staff++ provides a way to be notified when it thinks a user is using alternative accounts.
The detection is really simple so don't expect miracles. It will detect the most basic and obvious alt accounts.
Alt detection is disabled by default

## Configuration
```
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

70% similarity --> score 3
50% similarity --> score 2
30% similarity --> score 1

### Detection trust levels (score)
