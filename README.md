# Microservices with Kafka, Graphql & Elasticsearch 

E-commerce platform built with a microservices-first approach: Kafka for event streaming, a GraphQL gateway to orchestrate services, and Elasticsearch powering product discovery.

## Product Vision
- Service-per-domain (catalog, inventory, orders, payments) coordinated through Kafka topics.
- GraphQL gateway to unify service APIs for web and mobile clients.
- Elasticsearch-backed search with eventual consistency fed by Kafka consumer jobs.
- Horizontal scalability and fault isolation at the service level.

## Current Status (implemented)
- Catalog service skeleton in Express with REST endpoints for product CRUD (`/products`, `/products/:id`) to be fronted by the future GraphQL gateway.
- DTO validation with `class-validator` and `class-transformer` to enforce request shapes for create/update operations.
- Repository pattern with a mock/in-memory implementation and factories for generating product fixtures (via `rosie` and `faker`).
- Unit tests for `CatalogService` using Jest/ts-jest with `rosie`-built fixtures, faker data, and mock repository behavior.
- Integration tests for catalog routes using Supertest, covering happy paths, validation failures, and error propagation.

## Local Development
- Install deps: `yarn install`
- Run dev server: `yarn dev` (defaults to port 8000)
- Run tests with coverage: `yarn test`

## Next Up
- Wire the catalog service to Kafka producers/consumers and Elasticsearch writes/reads.
- Add GraphQL gateway schemas/resolvers and service composition.
- Replace mock repositories with real persistence and indexing flows.
