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


Severity Levels and Thresholds