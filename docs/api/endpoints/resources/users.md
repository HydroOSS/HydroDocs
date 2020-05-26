# `GET` /api/v1/resources/users/:id

| Returns          | Public | Ratelimits  |
|------------------|--------|-------------|
| application/json | true   | 30r/10s (G) |

## Request

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

## Response

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