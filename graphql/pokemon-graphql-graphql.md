# PokéAPI GraphQL API

The PokéAPI GraphQL endpoint is a Hasura-powered GraphQL interface over the complete PokéAPI Pokémon database. It exposes every table in the `pokemon_v2` schema as a top-level query, supporting filtering, ordering, aggregation, and pagination via Hasura's standard argument conventions. The database covers Pokémon species, individual Pokémon forms, moves, abilities, types, items, evolutions, encounters, locations, regions, generations, game versions, Pokédexes, egg groups, berries, natures, machines (TM/HM), contest effects, and associated multilingual name/description tables.

Authentication is not required. The endpoint is open and rate-limited by IP.

**Endpoint:** https://beta.pokeapi.co/graphql/v1beta

**Documentation:** https://pokeapi.co/docs/graphql

**References:**
- Documentation: https://pokeapi.co/docs/graphql
- GettingStarted: https://pokeapi.co/docs/graphql#quick-start
- GraphiQL: https://beta.pokeapi.co/graphql/console/
- GitHub: https://github.com/PokeAPI/pokeapi
- Website: https://pokeapi.co

## Overview

PokéAPI provides a free, Hasura-powered GraphQL beta endpoint exposing the complete Pokémon database. The GraphQL interface allows developers to query species, moves, abilities, items, evolutions, game version data, and more using flexible GraphQL queries rather than multiple REST calls.

## Authentication

No authentication is required. The API is fully open and publicly accessible.

## Example Query

```graphql
query GetPokemon {
  pokemon_v2_pokemon(limit: 10) {
    id
    name
    base_experience
    height
    weight
    pokemon_v2_pokemontypes {
      pokemon_v2_type {
        name
      }
    }
  }
}
```

## Available Data

- **Species & Pokémon** — base stats, forms, names in multiple languages
- **Moves** — move details, damage class, effect, learn methods
- **Abilities** — effect text per language, hidden ability flags
- **Items** — item attributes, categories, fling effects
- **Evolutions** — evolution chains, triggers, conditions
- **Game Versions** — version groups, generations, regions
- **Encounters** — encounter methods, conditions, rates by location
- **Berries, Contests, Egg Groups, Natures, Pal Park** — full coverage

## Rate Limits

100 calls per hour per IP address. The service runs on a free-tier GCP e2-micro instance with scheduled daily reboots at 01:00 UTC (approximately 2 minutes of downtime). Clients exceeding the rate limit or violating the fair use policy may receive a permanent IP ban.

## Fair Use Policy

- Cache responses locally — do not repeatedly fetch the same resource
- Do not hammer the endpoint; respect the shared community infrastructure
- Report security vulnerabilities responsibly via the GitHub repository
- Respect the Pokémon trademark owned by Nintendo

## Technology Stack

The GraphQL layer is powered by [Hasura](https://hasura.io/), an open-source GraphQL engine that auto-generates a GraphQL API over a PostgreSQL database. The underlying data is the same dataset served by the PokéAPI REST endpoints.

## Related Resources

- REST API Documentation: https://pokeapi.co/docs/v2
- GitHub Organization: https://github.com/PokeAPI
- Main Website: https://pokeapi.co
