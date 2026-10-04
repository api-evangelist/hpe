---
name: hpe-invite-and-verify-user
description: Invite a new user to the workspace and verify the invitation by retrieving the user details.
api: openapi/hpe-identity-api-openapi.yml
operations:
- inviteUser
- getUser
generated: '2026-10-04'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/hpe-identity-api-openapi.yml ; every operationId checked against the contract
---

# hpe-invite-and-verify-user

Invite a new user to the workspace and verify the invitation by retrieving the user details.

## Steps

1. 1. Call `inviteUser` with the required request body (user email, role, etc.) and include an authentication header (e.g., `Authorization: Bearer <token>`).
2. 2. Call `getUser` with the user ID returned from the invitation response, again providing the authentication header.

## Rules

- Authentication: Use one of the BearerAuth schemes (`Authorization: Bearer <token>`).
- Rate limiting: Maximum 1 request per second; exceeding this returns HTTP 429.
- Errors: Handle standard HTTP error codes, especially 429 for rate limit exhaustion.
