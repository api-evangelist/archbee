---
name: archbee-manage-a-space
description: >-
  Create, configure, clone and delete an Archbee documentation space, including the public access
  control block. Emphasises that deleteSpace is irreversible and destroys the API key with the space.
api: archbee:archbee-public-api
operations:
- createSpace
- updateSpace
- cloneSpace
- deleteSpace
- createSpaceGroup
- deleteSpaceGroup
source: openapi/archbee-public-api-openapi.yml
generated: '2026-09-04'
method: generated
---

# Manage an Archbee space

A space is the container for documents and the unit an API key is scoped to. Space-lifecycle calls
need an organization key (`abteam_...`), because a space key cannot create the space it does not yet
belong to.

Base URL: `https://api.archbee.com/api/public-api`.

## 1. Create — `createSpace`

```bash
curl -X POST https://api.archbee.com/api/public-api/space/create \
  -H "Authorization: Bearer $ORG_KEY" \
  -H 'Content-Type: application/json' \
  -d '{"name": "Developer docs", "isReviewSystemEnabled": true}'
```

Returns the new space id. The new space inherits the apiKey. Optional flags include
`isLlmEnabled`, `isReviewSystemEnabled`, `isBranchingSystemEnabled` and `docSpaceGroupId`.

**Not idempotent.** Two identical calls create two spaces. There is no key to deduplicate on — check
for an existing space before retrying a call whose response you did not see.

## 2. Configure — `updateSpace`

`POST /space/update` changes only the parts you send. The access-control block is where the security
posture of a published portal lives:

- `publicProtectionType` selects none, password, guest accounts, magic link, private accounts,
  private links, JWT or SAML.
- `publicPassword`, `publicGuestAccounts`, `publicMagicLinkAccounts`, `publicPrivateAccounts` and
  `privateLinkTokens` carry the corresponding configuration.
- `jwtValidationType`, `jwtKeyUrl`, `jwtSecret`, `jwtRedirectURL` and `samlMetadata` configure the
  federated options.
- `hostnamePart` sets the custom hostname; `spaceLinks` wires multi-product navigation and should
  start with the current space.

Loosening `publicProtectionType` makes previously gated content world-readable on the next publish.
Treat it as a privileged change.

## 3. Clone — `cloneSpace`

`POST /space/clone` copies a space, optionally into a different `targetSpaceGroupId`. Use it as the
safe rehearsal for a destructive edit: the API has no dry-run mode, so a clone is the only way to try
a bulk change without touching the original.

## 4. Group — `createSpaceGroup` / `deleteSpaceGroup`

`POST /space-group/create` and `DELETE /space-group/delete`. A group must be empty before it can be
deleted, which is a real guard rail — move or delete its spaces first.

## 5. Delete — `deleteSpace`

```bash
curl -X DELETE https://api.archbee.com/api/public-api/space/delete \
  -H "Authorization: Bearer $ORG_KEY" \
  -H 'Content-Type: application/json' \
  -d '{"docSpaceId": "<docSpaceId>"}'
```

**Stop and read this before calling it.** `deleteSpace` permanently deletes the space and every
document in it, and it invalidates the space API key along with it. Archbee documents no restore
path and no recovery window. Export first with `organizationExport` (`GET /team/export`) if the
content matters. This is the single highest-consequence call in the API; require an explicit human
confirmation naming the space before an agent issues it.
