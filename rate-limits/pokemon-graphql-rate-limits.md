# PokéAPI GraphQL — Rate Limits

## Rate Limit Policy

PokéAPI GraphQL enforces a single rate limit across all users:

| Dimension | Limit |
|---|---|
| Requests per hour | 100 per IP address |
| Burst allowance | None documented |
| Rate limit scope | Per source IP address |
| Enforcement | Infrastructure level (GCP) |

## Reason for Limits

The GraphQL endpoint runs on a single free-tier GCP e2-micro instance maintained by community volunteers. The 100 calls/hour cap is in place to protect shared infrastructure and ensure fair access across all developers.

## Scheduled Downtime

- **Daily reboot:** 01:00 UTC — approximately 2 minutes of downtime
- **Sporadic maintenance:** unscheduled, announced via GitHub when possible

## Handling Rate Limit Errors

When the rate limit is exceeded, the API returns an HTTP `429 Too Many Requests` response. Clients should:

1. Implement exponential backoff before retrying
2. Cache all responses locally using the full URL or query hash as the cache key
3. Avoid issuing the same query more than once per session without checking the cache

## Caching Guidance

The PokéAPI dataset is static (it does not change in real time). All responses are safe to cache indefinitely or until a new Pokémon generation is released. Recommended minimum cache TTL: **24 hours**.

## Enforcement

Users who consistently violate rate limits or the fair use policy may receive a **permanent IP ban** applied at the infrastructure level with no appeal process documented. Comply with the fair use policy to avoid bans.

## Source

- https://pokeapi.co/docs/graphql
