# Introduction

Staff++ does not have an internal authentication system.

The main reason for this decision is that there are other better plugins out there to support authentication.
We do however cover the following scenarios:

## Online server mode + permissions. 
In this case the official Minecraft authentication system is used. This system in combination with the correct permission setup allows for a secure authentication mechanism.

## Offline server mode + AuthMe Authentication. Everyone needs to login. 
When we use AuthMe we can enforce all players to login. Using this system every player has to login before being able to execute commands. Using this + permissions is enough to block other users from using the commands.

## Offline server mode + AuthMe Authentication. Only Staff needs to log in.
AuthMe can be configured to have optional registration. Players can choose if they want to register or not. However this allows any player who joins with the same name as a staff member to have the staff member's permissions. To prevent any player to execute the Staff++ commands we have integrated the AuthMe plugin. Configure the authentication provider inside the Staff++ config to "authme". This will make sure any player who tries to execute a Staff++ must be logged in and have the correct permissions. In other words we force authentication before you can use Staff++ commands even if AuthMe registration is optional.

# Configuration
Inside the configuration file make sure the following section is present:
```
# Chooses the authentication provider. Default "noop", no authentication will be done.
# AuthMe is supported. When the provider is authMe, Staff++ will enforce that the user is authenticated through AuthMe before being able to execute the commands.
authentication:
    provider: authme
```
The provider must be configured to `authme`. If `noop` is configured no authentication check will be done by StaffPlusPlus.
Permissions are off-course still validated

### Authme Plugin https://github.com/AuthMe/AuthMeReloaded