# Endpoints (v1)

These are the currently-supported endpoints that the Hydro API allows you to use. Note that all v1 endpoints are served at `/api/v1`; this allows you to have a grace period of upgrading your client when we release new versions.

!!! tip
    When a path starts with `:`, it's a variable parameter. An example includes getting servers: the path is `/api/v1/resources/servers/:id`. We'd need to replace `:id` with a server ID, like so: `/api/v1/resources/servers/711913852161359972`.

    The `r` in `30r/10s (G)` (a ratelimit specification) means requests, and `s` means seconds. `G` means global; the ratelimit carries on from other endpoints and also causes you to be blocked from the rest.

## Resources

The main thing that the API serves is resources like server data. The full list includes servers, users, strikes, merits and giveaways.

### `GET` /api/v1/resources/servers/:id

| Returns          | Public | Ratelimits  |
|------------------|--------|-------------|
| application/json | true   | 30r/10s (G) |

#### Request

=== "cURL"
    ```bash
    $ curl https://api.hydrobot.me/api/v1/resources/servers/my_server_id
    ```
=== "JavaScript"
    !!! info
        This example uses [window.fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)/[node-fetch](https://github.com/node-fetch/node-fetch). Try pasting it in your browser console!
    ```js  
    const url = "https://api.hydrobot.me/api/v1/resources/servers/my_server_id";
    const resp = await (await window.fetch(url)).json();
    console.log(resp);
    ```
=== "Python"
    !!! info
        This example uses [requests](https://pypi.org/project/requests).
    ```py
    import requests

    url = 'https://api.hydrobot.me/api/v1/resources/servers/my_server_id'
    resp = requests.get(url=url).json()
    print(resp)
    ```

#### Response

```json
{
  "data": {
    "agreeMethod": "reaction",
    "antiAbuse": true,
    "antiInvite": true,
    "antiSpam": true,
    "appealsChannel": "channel_id",
    "approveChannel": "channel_id",
    "id": "server_id",
    "leaveMessage": "%user% just left %server%!",
    "logChannel": "channel_id",
    "mainChannel": "channel_id",
    "memberRole": "role_id",
    "messagesToday": 95,
    "mutedRole": "role_id",
    "prefix": "$",
    "reactionChannel": "channel_id",
    "reactionID": "reaction_id",
    "reportsChannel": "channel_id",
    "staffRole": "role_id",
    "verifiedRole": "role_id",
    "welcomeMessage": "Welcome %user% to %server!"
  }
}
```

### `GET` /api/v1/resources/users/:id

| Returns          | Public | Ratelimits  |
|------------------|--------|-------------|
| application/json | true   | 30r/10s (G) |

#### Request

=== "cURL"
    ```bash
    $ curl https://api.hydrobot.me/api/v1/resources/users/my_user_id
    ```
=== "JavaScript"
    !!! info
        This example uses [window.fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)/[node-fetch](https://github.com/node-fetch/node-fetch). Try pasting it in your browser console!
    ```js  
    const url = "https://api.hydrobot.me/api/v1/resources/users/my_user_id";
    const resp = await (await window.fetch(url)).json();
    console.log(resp);
    ```
=== "Python"
    !!! info
        This example uses [requests](https://pypi.org/project/requests).
    ```py
    import requests

    url = 'https://api.hydrobot.me/api/v1/resources/users/my_user_id'
    resp = requests.get(url=url).json()
    print(resp)
    ```

#### Response

```json
{
  "data": {
    "age": "18",
    "country": "United Kingdom",
    "gayMsg": "not smh",
    "gayPercentage": "0",
    "gender": "Male",
    "id": "user_id",
    "msgs": { "a_guild_id": 66 /* message count */, "a_guild_id": 131 },
    "points": 40,
    "quote": "my name jef"
  }
}
```

### `GET` /api/v1/resources/strikes/:id

| Returns          | Public | Ratelimits  |
|------------------|--------|-------------|
| application/json | true   | 30r/10s (G) |

#### Request

=== "cURL"
    ```bash
    $ curl https://api.hydrobot.me/api/v1/resources/strikes/a_strike_id
    ```
=== "JavaScript"
    !!! info
        This example uses [window.fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)/[node-fetch](https://github.com/node-fetch/node-fetch). Try pasting it in your browser console!
    ```js  
    const url = "https://api.hydrobot.me/api/v1/resources/strikes/a_strike_id";
    const resp = await (await window.fetch(url)).json();
    console.log(resp);
    ```
=== "Python"
    !!! info
        This example uses [requests](https://pypi.org/project/requests).
    ```py
    import requests

    url = 'https://api.hydrobot.me/api/v1/resources/strikes/a_strike_id'
    resp = requests.get(url=url).json()
    print(resp)
    ```

#### Response

```json
{
  "data": {
    "id": "strike_id",
    "guildID": "guild_id",
    "offender": "user_id",
    "staffMember": "user_id",
    "reason": "strike reason"
  }
}
```

### `GET` /api/v1/resources/merits/:id

| Returns          | Public | Ratelimits  |
|------------------|--------|-------------|
| application/json | true   | 30r/10s (G) |

#### Request

=== "cURL"
    ```bash
    $ curl https://api.hydrobot.me/api/v1/resources/merits/a_merit_id
    ```
=== "JavaScript"
    !!! info
        This example uses [window.fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)/[node-fetch](https://github.com/node-fetch/node-fetch). Try pasting it in your browser console!
    ```js  
    const url = "https://api.hydrobot.me/api/v1/resources/merits/a_merit_id";
    const resp = await (await window.fetch(url)).json();
    console.log(resp);
    ```
=== "Python"
    !!! info
        This example uses [requests](https://pypi.org/project/requests).
    ```py
    import requests

    url = 'https://api.hydrobot.me/api/v1/resources/merits/a_merit_id'
    resp = requests.get(url=url).json()
    print(resp)
    ```

#### Response

```json
{
  "data": {
    "id": "giveaway_id",
    "enabled": true /* boolean */,
    "guildID": "guild_id",
    "host": "user_id",
    "item": "item name",
    "messageID": "message_id",
    "participants": ["user_id", "user_id"] /* user_id[] */,
    "winner": "user_id",
  }
}
```