# about this library

use this library, You can use osu!api v1's Getuser easily!!
This lirary written in javascript

and for Node.js

# How to use this library in your project

just type this in your console

```
npm i get-osu-profile
```

This library uses axios library

```
npm i axios
```

This library has one function

```javascript
getplayersdata(API key, username, mode)
```

and return
```javascript
{
    "user_id"              : "1",
    "username"             : "User name",
    "join_date"            : "2014-07-13 06:26:30", // In UTC
    "count300"             : "1337",      // Total amount for all ranked, approved, and loved beatmaps played
    "count100"             : "123",       // Total amount for all ranked, approved, and loved beatmaps played
    "count50"              : "69",        // Total amount for all ranked, approved, and loved beatmaps played
    "playcount"            : "42",        // Only counts ranked, approved, and loved beatmaps
    "ranked_score"         : "666666",    // Counts the best individual score on each ranked, approved, and loved beatmaps
    "total_score"          : "999999998", // Counts every score on ranked, approved, and loved beatmaps
    "pp_rank"              : "2442",
    "level"                : "50.5050",
    "pp_raw"               : "3113",      // For inactive players this will be 0 to purge them from leaderboards
    "accuracy"             : "98.1234",
    "count_rank_ss"        : "54",
    "count_rank_ssh"       : "54",
    "count_rank_s"         : "81",        // Counts for SS/SSH/S/SH/A ranks on maps
    "count_rank_sh"        : "81",
    "count_rank_a"         : "862",    
    "country"              : "DE",        // Uses the ISO3166-1 alpha-2 country code naming. See this for more information: https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)
    "total_seconds_played" : "1823790",
    "pp_country_rank"      :"1337",  
    "iconurl" :  `https://a.ppy.sh/${data.user_id}`
    "playerurl" : `https://osu.ppy.sh/users/${data.user_id}`
}
```

If username was not found
```js
return 0
```
# Example

```javascript
const { getplayersdata } = require("get-osu-profile")
const apikey = "Your osu!api v1 key here"
const username = "username(like Hoshino1, 13673007)"
const mode  = "mode" //standard = 0, taiko = 1, ctb = 2, mania = 3
let user_id
let username_osu
const Getuser = async () => {
    const userdata = await getplayersdata(apikey, username, mode)
    user_id = userdata.user_id
    username_osu = userdata.username
    console.log(user_id) //13673007
    console.log(username_osu) //Hoshino1
}

Getuser()
```
