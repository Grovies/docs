# Ratelimit

To ensure optimal performance and fair usage of the Groovies API, rate limiting is implemented. Rate limits are designed to protect the API infrastructure and ensure a consistent experience for all developers integrating with Groovies.

- Requests Per Minute (RPM): 25 requests per minute.

## Respect Headers
    - X-RateLimit-Limit: The maximum number of requests permitted within the current time window.
    - X-RateLimit-Remaining: The number of requests remaining within the current time window.
    - X-RateLimit-Reset: The time at which the current rate limit window resets in UTC epoch seconds.

## Handling Rate Limit Exceedances
    - If the rate limit is exceeded, the API will respond with an HTTP status code 429 Too Many Requests.
    - The response headers will provide information on the rate limit status, including when you can make additional requests.
    - IP Banning: Exceeding the rate limit excessively may result in IP banning, with subsequent requests receiving HTTP status code 403 Forbidden.

## Best Practices
    - implement exponential backoff strategies to handle rate limit errors gracefully.
    - Cache data where possible to minimize the number of API requests.
    - Monitor rate limit headers to adjust your application's behavior dynamically.

:::danger

Rate limits are subject to change to ensure fair usage and system stability. Developers are encouraged to monitor API usage and adjust integration strategies accordingly.

:::