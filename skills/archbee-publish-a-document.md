---
name: archbee-publish-a-document
description: >-
  Create or update a page in an Archbee documentation space from Markdown or MDX, then publish the
  space so readers see it. Covers the credential shape, the upsert semantics of POST /doc, and the
  fact that publishing has no documented inverse.
api: archbee:archbee-public-api
operations:
- updateCreateDocument
- getDocument
- publishSpace
source: openapi/archbee-public-api-openapi.yml
generated: '2026-09-04'
method: generated
---

# Publish a document to an Archbee space

## Before you start

Build the credential yourself. Archbee's bearer value is not a token it issued — it is
`base64(docSpaceId + "~" + apiKey)`:

```bash
TOKEN=$(printf '%s~%s' "$DOC_SPACE_ID" "$API_KEY" | base64)
```

An organization key beginning `abteam_` is used as-is instead, and reaches every space; the space
then travels in the request body. A `PUBLISHED-` or `PREVIEW-` snapshot space id reads fine and is
refused for every write.

Base URL: `https://api.archbee.com/api/public-api`.

## 1. Create or update the document — `updateCreateDocument`

`POST /doc` is an upsert. Send a `docId` and it updates that document in place; omit it and Archbee
creates a new one.

```bash
curl -X POST https://api.archbee.com/api/public-api/doc \
  -H "Authorization: Bearer $TOKEN" \
  -H 'Content-Type: application/json' \
  -d '{
        "content": "# Release notes\nAnd this is a paragraph",
        "format": "markdown",
        "title": "Release notes"
      }'
```

`format` accepts `markdown`, `mdx` or `json`. Use `mdx` when the body contains JSX-style Archbee
components (`<hint>`, `<CtaButton />`, `<Tabs>`); directive-style components (`:::hint{type="info"}`)
work in both.

Only the fields you send are changed on an update. Nest the page by passing `parentDocId`.

## 2. Read it back — `getDocument`

`GET /doc` carries a **JSON request body**, which is unusual and which some HTTP clients silently
drop. If you get a 400 with `Api key or Space Id not found or not allowed!` on a request you believe
is authenticated, check that your client actually sent the body.

```bash
curl -X GET https://api.archbee.com/api/public-api/doc \
  -H "Authorization: Bearer $TOKEN" \
  -H 'Content-Type: application/json' \
  -d '{"docId": "<docId>", "format": "markdown"}'
```

## 3. Publish the space — `publishSpace`

```bash
curl -X POST https://api.archbee.com/api/public-api/space/publish \
  -H "Authorization: Bearer $TOKEN" \
  -H 'Content-Type: application/json' \
  -d '{"docSpaceId": "'"$DOC_SPACE_ID"'"}'
```

## Rules to respect

- **No idempotency.** There is no `Idempotency-Key` header and no replay window. A retried
  create-without-a-docId creates a second document. Retry safely only by supplying a `docId`, which
  turns the call into an update.
- **Errors are always 400.** Bad credentials, bad input and refused operations all return HTTP 400
  with `{"status":"Not OK","messages":["..."]}`. Read `messages[]`; the status line tells you nothing.
- **Rate limit.** Every response carries `x-ratelimit-limit`, `x-ratelimit-remaining` and
  `x-ratelimit-reset`. The observed unauthenticated ceiling is 100 and `x-ratelimit-reset` is a
  human-readable date string, not a timestamp — parse it as a date. There is no `Retry-After`.
- **Publishing has no documented inverse.** No unpublish operation exists in the Public API. Confirm
  the content before you publish.
- **Limits.** 500 blocks and 1MB per document, 1000 documents per space.
