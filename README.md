# Simple-Steam-API-Wrapper
Simple Node.js wrapper for the [Steam API](https://developer.valvesoftware.com/wiki/Steam_Web_API#GetNewsForApp_.28v0001.29)

This file requires the Axios package to make the API requests:
```
npm i axios
```

#### Helper Functions:
`getGameIDByName` scrapes the steamcommunity site to get a user's id by their _username_ *not* _nickname_ to simplify the use of the API functions.

`getUserIDByName` scrapes the steamcommunity site to get an app's id by its name, The app name must be exact with the exception of any of ©, ©, ®, or ™ symbols. If you run into any other problematic special characters let me know.

#### API Endpoints:
All functions return JSON objects for follow up parsing.

```js
getNewsForApp(app, count, maxLength)
```

Arguments:
 - app
AppID or Name of the game you want the news of.
 - count
How many news enties you want to get returned.
 - maxLength
Maximum length of each news entry.

Result layout:
An appnews object containing:
 - appid, the AppID of the game you want news of
 - newsitems, an array of news item information:
    - An ID, title and url.
    - A shortened excerpt of the contents (to maxlength characters), terminated by "..." if longer than maxlength.
    - A comma-separated string of labels and UNIX timestamp.


`getGlobalAchievementPercentagesForApp`
`getGlobalStatsForGame`
`getPlayerSummaries`
`getFriendList`
`getPlayerAchievements`
`getOwnedGames`
`getSchemaForGame`
`getRecentlyPlayedGames`
`isPlayingSharedGame`
`getPlayerBans`
`getAssetUrl`
