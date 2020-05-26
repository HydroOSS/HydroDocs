# Limits

Due to the fact that Hydro's API is free, it has *some* limits.

Currently, the only limit that's in place is ratelimiting; you'll receive the following response:

```json
{
  "data": null,
  "isBoom": true,
  "isServer": false,
  "output": {
    "statusCode": 429,
    "payload": {
      "statusCode": 429,
      "error": "Too Many Requests",
      "message": ">30 requests in 10s; ratelimited"
    },
    "headers": {}
  }
}
```

As can be seen, the ratelimiter doesn't allow you to make more than 30 requests in 10 seconds. This is relatively generous, so you really won't be reaching it unless you're abusing the API. In the case that you *will* be exceeding that, please [request an increase](mailto:alexeek@protonmail.com?Subject=Hydro%20API%20Ratelimits).