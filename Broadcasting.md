# Introduction
Staff++ added a "broadcast" command. This allows a staff member to send a member across the server.
If you are in a bungee network the message will be send to all servers or only to the ones specified in the config.

## Configuration
Make sure the following section is present in your config file:

```
############################################################
# +------------------------------------------------------+ #
# |                      Broadcast                       | #
# +------------------------------------------------------+ #
############################################################

# Requires "permissions.broadcast" permission.
broadcast-module:
  # Whether or not the plugin will use "/broadcast" features.
  enabled: true
  # The servers to which the broadcasting is applied "CURRENT" is the default value and broadcasts only on the current server.
  # This also prevents staff members from broadcasting to other servers
  # "ALL" broadcasts to all known servers on the network.
  # Alternatively you can provide a list of semicolon separated server names to which the broadcasting should be applied.
  # Example: lobby;survival;skyblock
  enabled-servers: CURRENT
```

The enabled-servers option allows us to restrict the receiving servers. 
- CURRENT: only the current server is allowed to receive message. Use this when you are not on a bungee network
- ALL: The message will be send to all servers on the network.
- list: The message will only be send to the servers in the list