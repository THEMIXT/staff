# Introduction

Staff++supports Trello integration. Whenever reports are created, or they change status it can by synchronized with Trello.
However this a one way synchronization, if you change the cards created by Staff++ in Trello it will not be updated in game.

Install the Staff++ Trello Integration plugin: https://www.spigotmc.org/resources/staff-trello-integration.84552/

## Configuration
```yaml
StaffPlusPlusTrello:
    reports:
        # Your api key
        apiKey: ""
        # Your user token
        userToken: ""
        # The id of your board, can be found in the url
        boardId: ""

        # The list names in which the cards should be placed when moved to this status
        openListName: "open"
        rejectedListName: "rejected"
        acceptedListName: "accepted"
        resolvedListName: "resolved"
```

### Obtaining the API key
I recommend creating a new Trello user purely for the purpose of the Staff++ integration, but you can also use your existing user.

Log in into Trello with the user you want to use for the integration. The user needs access to the board where the reports should be added on.

Go to: **https://trello.com/app-key** <br />
Your api Key is displayed here.

Add your API key to the config file.

### Obtaining the User Token
Make sure you first obtain the API key as explained in the previous section<br />
Visit the following url: (Change {your-api-key} with the API key)

https://trello.com/1/authorize?expiration=never&name=StaffPlusPlusToken&scope=read,write&response_type=token&key={your-api-key}

This page gives you the user token. _**Keep this token a secret as anyone with this token can access your board.**_

Add your User Tokento the config file.

### Obtaining the board ID
The board ID can be found inside the url when navigating to your board<br />
For example: https://trello.com/b/WkCJeuKv/staffplusplus<br />
The board ID in this case is **WkCJeuKv**

Add your Board ID to the config file.

### The lists
Lastly map the Staff++ statuses to the correct Lists on your Trello board. The match is done based on the List name and it must be an exact match.
If the plugin can't find any of the configured lists on the board, an error message will be thrown at startup of the plugin


## Example:

[[/images/trello_integration.gif|Trello Integration Gif]]