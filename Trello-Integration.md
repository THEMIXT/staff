# Introduction

Staff++supports Trello integration. Whenever reports are created, or they change status it can by synchronized with Trello.
However this a one way synchronization, if you change the cards created by Staff++ in Trello it will not be updated in game.

## Configuration
```
StaffPlusPlusTrello:
    reports:
        # Your api key
        apiKey: ""
        # Your user token
        userToken: ""
        # The id of your board, can be found in the url
        boardId: ""

        # The list name in which the cards should be place when moved to this status
        openListName: "open"
        rejectedListName: "rejected"
        acceptedListName: "accepted"
        resolvedListName: "resolved"
```

### obtaining the api key
I recommend creating a new Trello user purely for the purpose of the Staff++ integration, but you can also use your existing user.
