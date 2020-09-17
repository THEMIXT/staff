# Introduction
Staff++ created a new way of warning players.
This system is available since versions: 1.13.7, 1.14.7, 1.15.8, 1.16.13

## Configuration changes when upgrading to the new system
[Example configuration file](https://github.com/garagepoort/StaffPlusPlus/blob/master/StaffPlusCore/src/main/resources/config.yml)

Remove the following properties from the `warnings-module`:
* `maximum`
* `ban-command`

The old system is no longer supported so the above properties can be removed.

Underneath the warning modules add the following:
```
severity-levels:
  - name: MINOR
    score: 1
  - name: MAJOR
    score: 3
  - name: CRITICAL
    score: 5
# Define thresholds for the warning system. Whenever the player reaches a threshold the actions are triggered
thresholds:
  - score: 6
    actions:
      - command: "ban %player% &4Met three warnings. Appeal @ &7www.shithcf.net&4."
        run-strategy: DELAY
```

The above is the default setup and you can change it as you'd like.

In the end the warning module should look like this:

```
# Requires "permissions.warn" permission.
warnings-module:
  # Whether or not the plugin will use "/warn" features.
  enabled: true

  # The sound that is played to the player when warned.
  # Set to "NONE" to disable.
  sound: ORB_PICKUP

  # The amount of time, in seconds, that it will take for a warning to be removed.
  # Set to zero to disable.
  clear: 604800

  # Whether or not the player issued the warning will be visible in GUIs.
  show-issuer: true

  severity-levels:
    - name: MINOR
      score: 1
    - name: MAJOR
      score: 3
    - name: CRITICAL
      score: 5
  # Define thresholds for the warning system. Whenever the player reaches a threshold the actions are triggered
  thresholds:
    - score: 6
      actions:
        - command: "ban %player% &4Met three warnings. Appeal @ &7www.shithcf.net&4."
          run-strategy: DELAY
```

Underneath the commands section add the following command:
```
warns: "warns"
teleport: "teleport"
```

That's it, try starting up the server and see if everything runs as expected.

    Should you still encounter problems please do compare your configuration file with the example config file


## Severity Levels and Thresholds

In the configuration file we defined severity levels. These can be as many as you want but it's preferably to have at least one.
We define a `name` and `score`. The score determines how serious an offence the player has committed. An example configuration could be:

```
severity-levels:
  - name: STEALING
    score: 1
  - name: GRIEFING
    score: 3
  - name: BULLYING
    score: 6
```
As you can see in the above config, griefing is a more serious offence than stealing. And bullying is the most serious offence. 
Once the levels are defined we can define thresholds.

Thresholds can be reached by players if they receive too many warnings. An example configuration:
```
thresholds:
  - score: 3
    actions:
      - command: "tempban %player% 4 days"
        run-strategy: DELAY
  - score: 6
    actions:
      - command: "ban %player%"
        run-strategy: ALWAYS
```

We defined two thresholds. When the player reaches the first threshold of a total warning score of 3 he will be temporarily banned.
Keep in mind that his total score wont be reset. Which means that if he gets another warning for stealing for example, his total score will be 4 and he will immediately get temporarily banned again. So once you reach a threshold you will be punished more severely on subsequent warnings.

## Run strategy
As you can see in the above configuration, we can define a run strategy for each command. This is useful when we want to only execute the command in a certain situation.

Possible strategies:
- `ALWAYS` Run the command regardless if the player is on- or offline. This will always try to run the command immediatly
- `ONLINE` Run the command only if the player is online. Should the player be offline when the threshold is reached the configured command wont be executed.
- `DELAY` If the player is online, run the command immediately. If the player is offline, delay the command until his next login.

