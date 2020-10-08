# Rate Limiting

> Check to see how many requests we have left:

```shell
$ curl -i https://api.coldlead.io/v1/api_endpoint_here

HTTP/1.1 200 OK
Date: Thu, 08 Oct 2020 15:08:40 GMT
Status: 200 OK
X-RateLimit-Limit: 200
X-RateLimit-Remaining: 105
```

> Example rate limit error response:

```shell
HTTP/1.1 429 Too Many Requests

X-RateLimit-Limit: 200
X-RateLimit-Remaining: 0
X-RateLimit-Reset: 1602169573
Retry-After: 50

Content-Type: application/json

{
  "message": "Too Many Attempts."
}
```

You can make 200 requests per minute to the API.

Check the returned HTTP headers of any API request to see your current rate limit status.

Header | Meaning
---------- | -------
X-RateLimit-Limit | The maximum number of requests that the customer is permitted to make per minute.
X-RateLimit-Remaining | The number of requests remaining in the current rate limit window.
X-RateLimit-Reset | The time at which the current rate limit window resets in UTC epoch seconds.
Retry-After | The number of seconds to wait until the rate limit window resets. Only sent when the rate limit.
