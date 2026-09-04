---
name: archbee-triage-reader-suggestions
description: >-
  Work the reader-suggestion queue on a published Archbee portal — merge a suggested edit into the
  live document or discard it — and export the organization before doing it in bulk.
api: archbee:archbee-public-api
operations:
- searchDocument
- getDocument
- mergeSuggestionIntoMainDocument
- discardSuggestionDocument
- organizationExport
source: openapi/archbee-public-api-openapi.yml
generated: '2026-09-04'
method: generated
---

# Triage reader suggestions

When Suggest Changes is enabled on a space, readers submit proposed edits that sit pending until
someone merges or discards them. Both outcomes are terminal.

Base URL: `https://api.archbee.com/api/public-api`.

## 1. Find the affected documents — `searchDocument`

```bash
curl -X POST https://api.archbee.com/api/public-api/docs/search \
  -H "Authorization: Bearer $TOKEN" \
  -H 'Content-Type: application/json' \
  -d '{"query": "authentication"}'
```

An empty `query` returns every document. There is no pagination on this API — no `limit`, `offset`,
`page` or cursor parameter exists — so the response is the whole result set, bounded only by the
1000-documents-per-space ceiling. `searchSessionId` in the response groups consecutive queries in
Archbee's search analytics; pass it back on follow-up searches.

## 2. Read the current content — `getDocument`

`GET /doc` with `{"docId": "...", "format": "markdown"}` in the body. Do this before merging, so you
know what the merge will replace. Note the GET-with-a-body shape.

## 3. Take a backup before a bulk pass — `organizationExport`

`GET /team/export` needs only an organization key, no `docSpaceId`. Merging is not reversible through
the API, so for anything larger than a handful of suggestions, export first.

## 4. Merge or discard

```bash
# accept the reader's edit into the live document
curl -X POST https://api.archbee.com/api/public-api/suggest-change/merge \
  -H "Authorization: Bearer $TOKEN" -H 'Content-Type: application/json' \
  -d '{"docId": "<docId>"}'

# reject it
curl -X POST https://api.archbee.com/api/public-api/suggest-change/discard \
  -H "Authorization: Bearer $TOKEN" -H 'Content-Type: application/json' \
  -d '{"docId": "<docId>"}'
```

## Rules to respect

- **Both outcomes are terminal in the API.** There is no unmerge and no undiscard operation. A merged
  edit can be rolled back only by a human, through Document Revision History in the app, and only
  within the plan's retention (1 year on Growing, 2 on Scaling, 5 on Enterprise). A discarded
  suggestion is gone.
- **No idempotency.** Do not blind-retry a merge whose response you did not see; read the document
  back first.
- **Rate limit.** `x-ratelimit-limit` was observed at 100 with an approximately one-second reset.
  Pace a bulk triage rather than firing the queue at once.
