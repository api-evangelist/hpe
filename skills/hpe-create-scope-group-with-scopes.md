---
name: hpe-create-scope-group-with-scopes
description: Create a new scope group and add resources to it.
api: openapi/hpe-authorization-api-openapi.yml
operations:
- createScopeGroup
- addScopesBatch
- listScopes
generated: '2026-10-04'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/hpe-authorization-api-openapi.yml ; every operationId checked against the contract
---

# hpe-create-scope-group-with-scopes

Create a new scope group and add resources to it.

## Steps

1. 1. Call `createScopeGroup` with the required request body fields for the new scope group.
2. 2. Call `addScopesBatch` with the `scope-group-id` returned from step 1 and the list of scopes to add.
3. 3. Call `listScopes` with the same `scope-group-id` to verify the scopes were added.

## Rules

- Include a Bearer token in the `Authorization` header (BearerAuth or bearerAuth).
- Pagination parameters `limit` and `sort` can be used with `listScopes`.
- If the rate limit of 1 request per second is exceeded, the API returns HTTP 429.
