# Uses

Hydro's API is _public_ and can be used to retrieve the following resources:

- servers;
- users;
- strikes;
- merits; and
- giveaways.

Note that to retrieve documents, you require an _ID_. This is relatively self-explanatory; for servers it's the server ID, for strikes it's the strike ID, and so on.

This may be changed in the future to allow for developers to easily fetch all strikes on a user, for example.

## Example

This is a simple example to show you what can be done with the API.

### Request

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

### Response

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

See the [Limits section](limits) for some error responses.
