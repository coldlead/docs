# Errors

Our API uses conventional HTTP response codes to indicate the success or failure of an API request.

In case of an error, we will return the correspondent error code.

### HTTP Status codes

Error Code | Meaning
---------- | -------
400 | Bad Request -- Your parameters are invalid.
401 | Unauthorized -- Your API key is wrong.
402 | Over Quota -- Over plan quota on this endpoint.
404 | Not Found -- The resource does not exist.
422 | Validation Error -- A validation error occurred.
429 | Too Many Requests -- You're making too many requests.
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
