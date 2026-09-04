---
name: archbee-sync-an-openapi-reference
description: >-
  Push an OpenAPI file into an Archbee space so Archbee renders it as API reference documentation,
  then inspect the generated tree. The docs-as-code flow behind Archbee's own API reference pages.
api: archbee:archbee-public-api
operations:
- uploadSingleFile
- syncOpenApiDocument
- infoOpenApiDocument
- publishSpace
source: openapi/archbee-public-api-openapi.yml
generated: '2026-09-04'
method: generated
---

# Sync an OpenAPI reference into Archbee

This is the flow that turns a spec in your repository into rendered API reference pages. Run it from
CI on every spec change.

Base URL: `https://api.archbee.com/api/public-api`.

## 1. Upload the spec — `uploadSingleFile`

`POST /upload/file` is `multipart/form-data`, not JSON:

```bash
curl -X POST https://api.archbee.com/api/public-api/upload/file \
  -H "Authorization: Bearer $TOKEN" \
  -F 'file=@openapi.yaml' \
  -F 'isPublic=true'
```

Returns `{"status":"OK","data":{"src":"<url>"}}`. The OpenAPI import ceiling is **3MB**; a Postman
collection is also 3MB, and a zip is 20MB.

## 2. Sync it — `syncOpenApiDocument`

`POST /sync-api-reference` regenerates the API-reference subtree from the spec. Archbee identifies
that subtree by `docTreeId`.

## 3. Inspect the result — `infoOpenApiDocument`

`GET /info-api-reference` reports on an existing tree — use it to confirm the operation count changed
the way you expected before publishing.

## 4. Publish — `publishSpace`

`POST /space/publish` makes the regenerated reference live.

## Rules to respect

- **The sync regenerates the tree.** Hand edits inside a generated API-reference subtree are not
  durable across a sync. Keep prose in ordinary documents outside the tree.
- **Replacing an asset keeps its URL.** If a diagram or logo referenced from the reference changes,
  use `overwriteAFileManagerFile` (`POST /file-manager/replace`) rather than delete-then-upload — it
  preserves the public URL, so published links do not break. The prior bytes are gone either way.
- **No dry run.** There is no validate-only mode. Validate the OpenAPI locally (or with
  `archbee validate` from the CLI) before syncing, because a bad sync is corrected by another sync,
  not by an undo.
- **Errors are 400 with `{"status":"Not OK","messages":[...]}`.** Read `messages[]`.
- The `@archbee/cli` package wraps steps 1 to 4 as `archbee upload`, `archbee sync-openapi`,
  `archbee info-openapi` and `archbee publish-space`.
