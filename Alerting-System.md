# Introduction
Staff++ kept the same alerting system that was already present in the old Staff+ plugin.
Using this system staff members can subscribe to be notified when certain events happen.
The notification is done through a message send in-game. If the staff member is not online he will miss the notification.

## Configuration

```yaml
alerts-module:
  # Whether or not staff will be notified when a user changes their name.
  name-notify: true

  # Whether or not staff will be notified when they are mentioned.
  mention-notify: true

  # The sound that is played to staff when notified.
  sound: ORB_PICKUP

  # Notifies staff when a player mines blocks listed in "blocks".
  xray-alerts:
    # Whether or not this module is enabled.
    enabled: true

    # Block type that, when mined, will invoke an alert.
    blocks: SPAWNER, EMERALD_ORE, DIAMOND_ORE, GOLD_ORE, IRON_ORE, COAL_ORE, LAPIS_ORE, REDSTONE_ORE

  # Notifies staff when a player is detected to use alt accounts.
  alt-detect-notify:
    enabled: true
    # Trust levels for which an alert should be triggered
    # POSITIVE;FAIRLY_POSITIVE;POSSIBLE;NOT_LIKELY
    trust-levels: POSITIVE;FAIRLY_POSITIVE
```

Enable all the alerts you want to be able to have your staff members receive.


## Subscribing to alerts
A staff member can subscribe to or unsubscribe from these events manually using the `/alerts [type]` command.

Keep in mind a staff member can only receive an alert if he has the correct permission.

```yaml
  # Permission for managing the alerts you will get
  alerts: "staff.staffplus.alerts"
  # Permission for receiving mention alerts.
  mention: "staff.alerts.mention"
  # Permission for receiving name change alerts.
  name-change: "staff.alerts.namechange"
  # Permission for receiving xray alerts.
  xray: "staff.alerts.xray"
  # Permission for receiving alt detect alerts.
  alerts-alt-detect: "staff.alerts.alt-detects"
```

### Example
(Un)Subscribe yourself to alt account detection alerts
```
/alerts ALT_DETECT
```

