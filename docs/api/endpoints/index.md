# v1

These are the currently-supported endpoints that the Hydro API allows you to use. Note that all v1 endpoints are served at `/api/v1`; this allows you to have a grace period of upgrading your client when we release new versions.

!!! tip
    When a path starts with `:`, it's a variable parameter. An example includes getting servers: the path is `/api/v1/resources/servers/:id`. We'd need to replace `:id` with a server ID, like so: `/api/v1/resources/servers/711913852161359972`.

    The `r` in `30r/10s (G)` (a ratelimit specification) means requests, and `s` means seconds. `G` means global; the ratelimit carries on from other endpoints and also causes you to be blocked from the rest.
