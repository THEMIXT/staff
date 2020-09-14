## Introduction

Discord integration lets StaffPlusPlus notify certain events to you discord server using discord webhooks.

To Enable integration you need to install a separate **plugin:**
**https://www.spigotmc.org/resources/staff-discord-integration.83871/**

Supported Staff++ version:

* >= 1.13.6
* >= 1.14.6
* >= 1.15.7
* >= 1.16.12

## Configuration
The configuration of the discord integration plugin is fairly simple.

```
StaffPlusPlusDiscord:
  # The discord webhook url. This can be found in you discord server settings
  webhookUrl: ""
 # Trigger a discord message when some player opens a new report
  notifyOpen: true
 # Trigger a discord message when a staff member for some reason decides to not handle a report and he unassigns himself
  notifyReopen: true
  # Trigger a discord message when a staff member assigns himself to an open report
  notifyAccept: true
  # Trigger a discord message when a staff member rejects a report
  notifyReject: true
  # Trigger a discord message when a staff member resolves a report
  notifyResolve: true
```

Make sure you create a webhook on your discord server. This can be done by following this guide: https://support.discord.com/hc/en-us/articles/228383668-Intro-to-Webhooks
Once you created the webhook paste it inside the configuration file.