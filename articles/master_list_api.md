# Master list API

The master list api allow you to fetch data from the alt:V master list service.

## Information

* GET only
* Return JSON Object
* If abused you can be banned from using the API

## API Links

|                   URL                      |                                        Description                                                      |
| :----------------------------------------: | :-----------------------------------------------------------------------------------------------------: |
| https://api.alt-mp.com/servers/info              | Statistics - Player Count across all servers & The amount of servers online                             |
| https://api.alt-mp.com/servers              | Servers - All information known about all servers (Name, Description, IP, Language, Website, Etc.)      |
| https://api.alt-mp.com/servers/SERVERID       | Specific Server - Filters server list for a specific one. Uses "id" which is unique to the server token |
| https://api.alt-mp.com/servers/SERVERID/avg/TIME | Averages - Returns averages data about the specified server (TIME = 1d, 7d, 31d)                        |
| https://api.alt-mp.com/servers/SERVERID/max/TIME | Maximum - Returns maximum data about the specified server (TIME = 1d, 7d, 31d)                          |

## Response example
### Statistics

```json
{ "ServersCount": 64, "playersCount": 1582 }
```

### Server list
It's a fragment of API's response.

```json
[
    {
        "id":"ceaac3d1cc22761223beac38386f5ab2",
        "maxPlayers":128,
        "players":0,
        "name":"Simple Freeroam Server | by PlebMasters.de",
        "locked":false,
        "host":"116.203.227.203",
        "port":7791,
        "gameMode":"Freeroam",
        "website":"discord.gg/86uqkqc",
        "language":"en",
        "description":"A simple game mode to test the performance of alt:V, but also to move freely around the map without any rules.",
        "verified":false,
        "promoted":false,
        "useEarlyAuth":false,
        "earlyAuthUrl":"",
        "useCdn":false,
        "cdnUrl":"",
        "useVoiceChat":false,
        "tags":
            [
                "No Rules",
                "All Weapons",
                "All Vehicles"
            ],
        "bannerUrl":null,
        "branch":"release",
        "build":1181,
        "lastUpdate":1596840894273
    }
]
```

### Specific server
```json
{
    "active":true,
    "info":{
        "id":"ceaac3d1cc22761223beac38386f5ab2",
        "maxPlayers":128,
        "players":0,
        "name":"Simple Freeroam Server | by PlebMasters.de",
        "locked":false,
        "host":"144.91.81.134",
        "port":7791,
        "gameMode":"Freeroam",
        "website":"discord.gg/86uqkqc",
        "language":"en",
        "description":"A simple game mode to test the performance of alt:V, but also to move freely around the map without any rules.",
        "verified":false,
        "promoted":false,
        "useEarlyAuth":false,
        "earlyAuthUrl":"",
        "useCdn":false,
        "cdnUrl":"",
        "useVoiceChat":false,
        "tags":[
            "No Rules",
            "All Weapons",
            "All Vehicles",
            "Enabled Cayo Perico"
        ],
        "bannerUrl":null,
        "branch":"release",
        "build":-1,
        "version":"2.8",
        "lastUpdate":1612571971068
    }
}
```

### Average / Maximum
```json
[
    { "t":1612562230,"c":4 },
    { "t":1612562280,"c":4 },
    { "t":1612562341,"c":4 }
]
```

Description: t = Timestamp in UTC, c = Player Count.
