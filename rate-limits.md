# Rate Limits

We rate limit all requests to our API to prevent any abuse or excessive stress on our infrastructure. Rate limits can vary depending on the route, and even whether a request is completed successfully or not.

Rate limits can be shared across certain routes which may be similar to each other or cover a similar area of the API.

As you near closer to exceeding a ratelimit, or make requests in rapid succession, we deliberately slow down and delay requests for an increasing duration with each new request made.

{% hint style="warning" %}
Rate limits can change at any time, without notice. You should not hard code rate limits into your code, and instead use the information provided in the headers to manage dynamic rate limits.
{% endhint %}

## Header Format

For each request made to our API, we return HTTP response headers which specify the rate limit encountered from the request.

#### Example

```http
X-RateLimit-Limit: 50
X-RateLimit-Remaining: 49
X-RateLimit-Reset: 1613425602
```

* **X-RateLimit-Limit**
  * The number of requests that can be made
* **X-RateLimit-Remaining**
  * The number of remaining requests that can be made
* **X-RateLimit-Reset**
  * Epoch time at which the rate limit resets
* **Retry-After**
  * Time \(in seconds\) until another request to this route can be made

## Exceeding A Rate Limit

If a rate limit is exceeded, a HTTP 429 response code will be returned.

