# PokéAPI GraphQL

PokéAPI GraphQL is a free, Hasura-powered GraphQL beta endpoint for the PokéAPI dataset. It provides flexible GraphQL queries over the complete Pokémon database including species, moves, abilities, items, evolutions, and game version data.

**GraphQL Endpoint:** https://graphql.pokeapi.co/v1beta2  
**GraphiQL Console:** https://graphql.pokeapi.co/v1beta2/console/  
**Documentation:** https://pokeapi.co/docs/graphql  
**Website:** https://pokeapi.co  
**GitHub Org:** https://github.com/PokeAPI  

## About

PokéAPI is a community-maintained open-source project providing Pokémon data through REST and GraphQL interfaces. The GraphQL layer is powered by [Hasura](https://hasura.io/) and exposes the same underlying PostgreSQL dataset as the REST API.

The API is completely free with no authentication required. A fair use policy applies: cache responses locally and stay within 100 calls per hour per IP address.

## Contents

| Path | Description |
|---|---|
| `apis.yml` | APIs.json 0.19 catalog entry |
| `graphql/pokemon-graphql-graphql.md` | GraphQL endpoint reference |
| `plans/pokemon-graphql-plans.md` | Plan details (free only) |
| `rate-limits/pokemon-graphql-rate-limits.md` | Rate limit policy |
| `finops/pokemon-graphql-finops.md` | FinOps guidance for consumers |

## Maintainer

Kin Lane — kin@apievangelist.com
