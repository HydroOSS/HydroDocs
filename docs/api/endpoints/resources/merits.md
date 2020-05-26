# `GET` /api/v1/resources/merits/:id

| Returns          | Public | Ratelimits  |
|------------------|--------|-------------|
| application/json | true   | 30r/10s (G) |

## Request

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

## Response

```json
{
  "data": {
    "id": "merit_id",
    "guildID": "guild_id",
    "offender": "user_id",
    "staffMember": "user_id",
    "reason": "merit reason"
  }
}
```