# Authentication

Staff++ does not have an internal authentication system.

The main reason for this decision is that there are other better plugins out there to support authentication.
We do however cover the following scenarios:

## Online server mode + permissions. 
In this case the official Minecraft authentication system is used. This system in combination with the correct permission setup allows for a secure authentication mechanism.

## Offline server mode + AuthMe Authentication. Everyone needs to login. 
When we use AuthMe we can enforce all players to login. Using this system every players has to login before being able to execute commands. Using this + permissions is enough to block other users from using the commands.

## Offline server mode + AuthMe Authentication. Only Staff needs to log in.
AuthMe can be configured to have optional registration. This allows any player who joins with the same name as a staff member to have the staff members permissions. To prevent any player to execute the Staff++ commands we have integrated the AuthMe plugin. Configure the authentication provider inside the Staff++ config to "authme". This will make sure any player who tries to execute a Staff++ must be logged in and have the correct permissions.
 