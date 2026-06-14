# PokéAPI GraphQL — Plans

## Overview

PokéAPI GraphQL is entirely free and open. There are no paid plans, subscription tiers, or API keys. Access is granted immediately to any client without registration.

## Free Plan (Only Plan)

| Feature | Value |
|---|---|
| Cost | $0 / month |
| Authentication | None required |
| Rate Limit | 100 requests per hour per IP |
| GraphQL Endpoint | `https://graphql.pokeapi.co/v1beta2` |
| GraphiQL Console | `https://graphql.pokeapi.co/v1beta2/console/` |
| Data Coverage | Full PokéAPI dataset (species, moves, abilities, items, evolutions, encounters, game versions) |
| SLA | None — community-run on free-tier GCP infrastructure |
| Support | Community only via GitHub Issues |

## Infrastructure Notes

The service runs on a single free-tier GCP e2-micro instance. Scheduled daily reboots occur at 01:00 UTC causing approximately 2 minutes of downtime. Sporadic maintenance may cause additional unscheduled interruptions.

## Fair Use Requirements

Users of the free plan are expected to:

1. **Cache responses locally** — do not repeatedly request the same resource
2. **Respect rate limits** — stay under 100 calls/hour per IP
3. **Avoid hammering the endpoint** — distribute requests; do not burst
4. **Report vulnerabilities** — via GitHub rather than public disclosure

Non-compliant users risk permanent IP bans enforced at the infrastructure level.

## Sustainability

PokéAPI is a community-driven open-source project. If you rely on this API, consider supporting the project through [Open Collective](https://opencollective.com/pokeapi).

## Source

- https://pokeapi.co/docs/graphql
- https://pokeapi.co/about
