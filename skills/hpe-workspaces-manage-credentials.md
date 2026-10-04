---
name: hpe-workspaces-manage-credentials
description: Create, list, reset, and delete API client credentials for Workspaces.
api: openapi/hpe-workspaces-api-openapi.yml
operations:
- createCredential
- listCredentials
- resetCredential
- deleteCredential
generated: '2026-10-04'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/hpe-workspaces-api-openapi.yml ; every operationId checked against the contract
---

# hpe-workspaces-manage-credentials

Create, list, reset, and delete API client credentials for Workspaces.

## Steps

1. 1. Use `createCredential` with required request body fields as defined in the contract.
2. 2. Use `listCredentials` with optional query parameters `limit` and `sort` for pagination.
3. 3. Use `resetCredential` with path parameter `id` and required header `X-Cypher-Token` (or other auth header) to regenerate the clientSecret.
4. 4. Use `deleteCredential` with path parameter `id` to remove a credential.

## Rules

- Auth: Include a valid Bearer token in the `Authorization: Bearer <token>` header or one of the API‑Key headers (e.g., `X-Cypher-Token`).
- Rate limit: Maximum 1 request per second; exceeding returns HTTP 429.
- Pagination: `listCredentials` supports `limit` and `sort` query parameters.
- Errors: HTTP 4xx for client errors (e.g., 404 for missing id), HTTP 5xx for server errors.
