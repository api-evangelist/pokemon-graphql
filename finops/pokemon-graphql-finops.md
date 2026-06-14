# PokéAPI GraphQL — FinOps

## Cost Profile

PokéAPI GraphQL has zero direct cost to API consumers. There are no usage fees, subscription charges, or overage costs at any volume.

| Cost Category | Amount |
|---|---|
| API access fees | $0 |
| Authentication / API keys | $0 |
| Egress charges (consumer side) | $0 |
| Support charges | $0 |
| Rate limit overage fees | $0 (IP ban instead) |

## Cost Drivers for Consumers

While the API itself is free, teams building on PokéAPI GraphQL should account for:

| Item | Notes |
|---|---|
| Local caching infrastructure | Required by fair use policy; saves on repeated calls within the 100/hr cap |
| Developer time | Building GraphQL query logic and managing schema changes between Pokémon generations |
| Rate limit monitoring | Tooling to track calls/hour per IP to avoid bans |
| Fallback / resilience handling | The API has no SLA; daily reboots and sporadic maintenance should be handled gracefully |

## FinOps Recommendations

1. **Cache aggressively.** The Pokémon dataset changes only with new game releases. Cache all GraphQL responses with a minimum TTL of 24 hours; indefinite caching is safe between generation updates.

2. **Batch queries.** GraphQL allows fetching related data in a single query. Use query nesting and aliases to minimise total call count and stay well under the 100/hr limit.

3. **Use the GraphiQL Explorer.** Before coding, prototype queries at `https://graphql.pokeapi.co/v1beta2/console/` to confirm shape and cost (number of rows returned) before embedding in production.

4. **Monitor IP usage.** If running on shared infrastructure (e.g., CI runners, cloud NAT), multiple services may share the same outbound IP and collectively exhaust the 100/hr cap. Assign dedicated IPs or implement a shared rate-limit counter.

5. **Support the project.** If this API provides business value, consider donating via [Open Collective](https://opencollective.com/pokeapi) to help keep the free infrastructure running.

## Infrastructure Cost (Provider Side, for Reference)

PokéAPI GraphQL runs on a single GCP e2-micro instance (free tier). The project is sustained by community donations through Open Collective. There is no commercial entity behind this service.

## Source

- https://pokeapi.co/docs/graphql
- https://pokeapi.co/about
