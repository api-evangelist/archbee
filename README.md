# Archbee

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Archbee is a documentation and knowledge-portal platform for software teams. It creates, manages and publishes technical documentation, API references and internal wikis, with collaborative editing, revision history, branching and review, custom-domain publishing, an embeddable in-product docs widget, and AI-assisted search, writing and translation. Archbee imports and syncs OpenAPI and Postman collections to generate rendered API reference documentation. Its own developer surface is a 24-operation REST Public API at https://api.archbee.com/api/public-api, a first-party CLI (@archbee/cli), a React widget package (@archbee/app-widget), and a Model Context Protocol server shipped in two deployments — a hosted OAuth endpoint at https://api.archbee.com/api/public-mcp-ds/sse and a local stdio server on npm as @archbee/mcp — exposing 26 tools over documents, spaces, templates, snippets and variables.

**Areas:** API Documentation · Documentation Platform · Knowledge Base · Technical Writing · Developer Docs · Developer Portal · Docs as Code · OpenAPI · MCP · AI Agents · Content Management · Developer Tools

## Archbee on APIs.io

Everything profiled for Archbee is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/archbee/](https://apis.io/providers/archbee/)** — or go straight to one of the APIs or properties below.

### APIs (11)

- [Archbee MCP Server](https://apis.io/apis/archbee/archbee-mcp-server/) — Archbee's Model Context Protocol server, shipped in two deployments: a hosted remote endpoint at https://api.archbee.com/api/public-mcp-ds/sse that an MCP…
- [Archbee Access Control API](https://apis.io/apis/archbee/archbee-access-control-api/) — Magic-link access requests for gated portals
- [Archbee API Reference API](https://apis.io/apis/archbee/archbee-api-reference-api/) — Sync and inspect an imported OpenAPI reference
- [Archbee Documents API](https://apis.io/apis/archbee/archbee-documents-api/) — Create, read, update, delete and search documents
- [Archbee File Manager API](https://apis.io/apis/archbee/archbee-file-manager-api/) — Upload, list, move, replace and delete File Manager files
- [Archbee Members API](https://apis.io/apis/archbee/archbee-members-api/) — Team member and access management
- [Archbee Organization API](https://apis.io/apis/archbee/archbee-organization-api/) — Organization-level export and display rules
- [Archbee Pages API](https://apis.io/apis/archbee/archbee-pages-api/) — Page content management
- [Archbee Space Groups API](https://apis.io/apis/archbee/archbee-space-groups-api/) — Grouping of documentation spaces
- [Archbee Spaces API](https://apis.io/apis/archbee/archbee-spaces-api/) — Documentation space management
- [Archbee Suggestions API](https://apis.io/apis/archbee/archbee-suggestions-api/) — Reader-submitted suggested changes — merge or discard

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Archbee Webhooks](https://apis.io/asyncapis/archbee/archbee-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Archbee MCP Server](https://apis.io/servers/archbee/archbee-mcp-server/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Archbee Agentic Access](https://apis.io/agentic-access/archbee/archbee-agentic-access/)

#### JSON Schema (18)

The data models the API reads and writes.

- [Moved to /providers/archbee/](https://apis.io/schemas/archbee/archbee-api-error-response/)
- [Moved to /providers/archbee/](https://apis.io/schemas/archbee/archbee-api-member/)
- [Moved to /providers/archbee/](https://apis.io/schemas/archbee/archbee-api-member-list/)
- [Moved to /providers/archbee/](https://apis.io/schemas/archbee/archbee-api-page/)
- [Moved to /providers/archbee/](https://apis.io/schemas/archbee/archbee-api-page-list/)
- [Moved to /providers/archbee/](https://apis.io/schemas/archbee/archbee-api-page-request/)
- [Moved to /providers/archbee/](https://apis.io/schemas/archbee/archbee-api-space/)
- [Moved to /providers/archbee/](https://apis.io/schemas/archbee/archbee-api-space-list/)
- [Moved to /providers/archbee/](https://apis.io/schemas/archbee/archbee-api-space-request/)
- [Document Request](https://apis.io/schemas/archbee/archbee-document-request/)
- [Document Response](https://apis.io/schemas/archbee/archbee-document-response/)
- [Document Search Request](https://apis.io/schemas/archbee/archbee-document-search-request/)
- [Document Search Response](https://apis.io/schemas/archbee/archbee-document-search-response/)
- [Error Response](https://apis.io/schemas/archbee/archbee-error-response/)
- [File Upload Response](https://apis.io/schemas/archbee/archbee-file-upload-response/)
- [Space Create Request](https://apis.io/schemas/archbee/archbee-space-create-request/)
- [Space Group Create Request](https://apis.io/schemas/archbee/archbee-space-group-create-request/)
- [Space Update Request](https://apis.io/schemas/archbee/archbee-space-update-request/)

#### JSON Structure (18)

Data models expressed in JSON Structure.

- [Moved to /providers/archbee/](https://apis.io/json-structure/archbee/archbee-api-error-response-structure/)
- [Moved to /providers/archbee/](https://apis.io/json-structure/archbee/archbee-api-member-list-structure/)
- [Moved to /providers/archbee/](https://apis.io/json-structure/archbee/archbee-api-member-structure/)
- [Moved to /providers/archbee/](https://apis.io/json-structure/archbee/archbee-api-page-list-structure/)
- [Moved to /providers/archbee/](https://apis.io/json-structure/archbee/archbee-api-page-request-structure/)
- [Moved to /providers/archbee/](https://apis.io/json-structure/archbee/archbee-api-page-structure/)
- [Moved to /providers/archbee/](https://apis.io/json-structure/archbee/archbee-api-space-list-structure/)
- [Moved to /providers/archbee/](https://apis.io/json-structure/archbee/archbee-api-space-request-structure/)
- [Moved to /providers/archbee/](https://apis.io/json-structure/archbee/archbee-api-space-structure/)
- [Archbee Document Request Structure](https://apis.io/json-structure/archbee/archbee-document-request-structure/)
- [Archbee Document Response Structure](https://apis.io/json-structure/archbee/archbee-document-response-structure/)
- [Archbee Document Search Request Structure](https://apis.io/json-structure/archbee/archbee-document-search-request-structure/)
- [Archbee Document Search Response Structure](https://apis.io/json-structure/archbee/archbee-document-search-response-structure/)
- [Archbee Error Response Structure](https://apis.io/json-structure/archbee/archbee-error-response-structure/)
- [Archbee File Upload Response Structure](https://apis.io/json-structure/archbee/archbee-file-upload-response-structure/)
- [Archbee Space Create Request Structure](https://apis.io/json-structure/archbee/archbee-space-create-request-structure/)
- [Archbee Space Group Create Request Structure](https://apis.io/json-structure/archbee/archbee-space-group-create-request-structure/)
- [Archbee Space Update Request Structure](https://apis.io/json-structure/archbee/archbee-space-update-request-structure/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Archbee Api Context](https://apis.io/jsonld/archbee/archbee-api-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [Archbee Vocabulary](https://apis.io/vocabularies/archbee/archbee-vocabulary/)

#### Examples (18)

Example requests and responses.

- [Moved to /providers/archbee/](https://apis.io/examples/archbee/archbee-api-error-response-example/)
- [Moved to /providers/archbee/](https://apis.io/examples/archbee/archbee-api-member-example/)
- [Moved to /providers/archbee/](https://apis.io/examples/archbee/archbee-api-member-list-example/)
- [Moved to /providers/archbee/](https://apis.io/examples/archbee/archbee-api-page-example/)
- [Moved to /providers/archbee/](https://apis.io/examples/archbee/archbee-api-page-list-example/)
- [Moved to /providers/archbee/](https://apis.io/examples/archbee/archbee-api-page-request-example/)
- [Moved to /providers/archbee/](https://apis.io/examples/archbee/archbee-api-space-example/)
- [Moved to /providers/archbee/](https://apis.io/examples/archbee/archbee-api-space-list-example/)
- [Moved to /providers/archbee/](https://apis.io/examples/archbee/archbee-api-space-request-example/)
- [Archbee Document Request Example](https://apis.io/examples/archbee/archbee-document-request-example/)
- [Archbee Document Response Example](https://apis.io/examples/archbee/archbee-document-response-example/)
- [Archbee Document Search Request Example](https://apis.io/examples/archbee/archbee-document-search-request-example/)
- [Archbee Document Search Response Example](https://apis.io/examples/archbee/archbee-document-search-response-example/)
- [Archbee Error Response Example](https://apis.io/examples/archbee/archbee-error-response-example/)
- [Archbee File Upload Response Example](https://apis.io/examples/archbee/archbee-file-upload-response-example/)
- [Archbee Space Create Request Example](https://apis.io/examples/archbee/archbee-space-create-request-example/)
- [Archbee Space Group Create Request Example](https://apis.io/examples/archbee/archbee-space-group-create-request-example/)
- [Archbee Space Update Request Example](https://apis.io/examples/archbee/archbee-space-update-request-example/)

#### Collections (8)

Postman and Open Collection request collections.

- [Moved to /providers/archbee/](https://apis.io/collections/archbee/open-archbee-members-api/)
- [Moved to /providers/archbee/](https://apis.io/collections/archbee/open-archbee-pages-api/)
- [Archbee Public API](https://apis.io/collections/archbee/open-archbee-public-api/)
- [Moved to /providers/archbee/](https://apis.io/collections/archbee/open-archbee-spaces-api/)
- [Moved to /providers/archbee/](https://apis.io/collections/archbee/postman-archbee-members-api/)
- [Moved to /providers/archbee/](https://apis.io/collections/archbee/postman-archbee-pages-api/)
- [Archbee Public API](https://apis.io/collections/archbee/postman-archbee-public-api/)
- [Moved to /providers/archbee/](https://apis.io/collections/archbee/postman-archbee-spaces-api/)

#### Overlays (11)

OpenAPI overlays, including conversational phrasing for each operation.

- [Archbee Access Control Api Phrasing Overlay](https://apis.io/overlays/archbee/archbee-access-control-api-phrasing-overlay/)
- [Archbee Api Reference Api Phrasing Overlay](https://apis.io/overlays/archbee/archbee-api-reference-api-phrasing-overlay/)
- [Archbee Documents Api Phrasing Overlay](https://apis.io/overlays/archbee/archbee-documents-api-phrasing-overlay/)
- [Archbee File Manager Api Phrasing Overlay](https://apis.io/overlays/archbee/archbee-file-manager-api-phrasing-overlay/)
- [Archbee Members Api Phrasing Overlay](https://apis.io/overlays/archbee/archbee-members-api-phrasing-overlay/)
- [Archbee Organization Api Phrasing Overlay](https://apis.io/overlays/archbee/archbee-organization-api-phrasing-overlay/)
- [Archbee Pages Api Phrasing Overlay](https://apis.io/overlays/archbee/archbee-pages-api-phrasing-overlay/)
- [Archbee Public Api Overlay](https://apis.io/overlays/archbee/archbee-public-api-overlay/)
- [Archbee Space Groups Api Phrasing Overlay](https://apis.io/overlays/archbee/archbee-space-groups-api-phrasing-overlay/)
- [Archbee Spaces Api Phrasing Overlay](https://apis.io/overlays/archbee/archbee-spaces-api-phrasing-overlay/)
- [Archbee Suggestions Api Phrasing Overlay](https://apis.io/overlays/archbee/archbee-suggestions-api-phrasing-overlay/)

#### Governance rules (2)

Spectral rulesets for the provider's contracts.

- [Archbee — jsonschema rules](https://apis.io/rules/archbee/archbee-jsonschema-spectral-rules/)
- [Archbee API Rules](https://apis.io/rules/archbee/archbee-spectral-rules/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Archbee Authentication](https://apis.io/security/archbee/archbee-authentication/)
- [Archbee Domain Security](https://apis.io/security/archbee/archbee-domain-security/)
- [Archbee Trust Center](https://apis.io/security/archbee/archbee-trust-center/)
- [Archbee Vulnerability Disclosure](https://apis.io/security/archbee/archbee-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Archbee Scopes](https://apis.io/scopes/archbee/archbee-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Archbee Plans Pricing](https://apis.io/plans/archbee/archbee-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Archbee Rate Limits](https://apis.io/rate-limits/archbee/archbee-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Archbee Finops](https://apis.io/finops/archbee/archbee-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.archbee.com/)
- [Documentation](https://docs.archbee.com/)
- [Getting started](https://www.archbee.com/docs/how-to-get-started)
- [API reference](https://www.archbee.com/docs/get-document)
- [Pricing](https://www.archbee.com/pricing)
- [Blog](https://www.archbee.com/blog)
- [Terms of service](https://www.archbee.com/terms-of-service)
- [Privacy policy](https://www.archbee.com/privacy-policy)
- [GitHub](https://github.com/archbee)
- [Status](https://status.archbee.com/)

## API Evangelist rating

**Kin Score 68.2** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 80.0 |
| Contract quality | 52.2 |
| Contract governance | 35.6 |
| Operational transparency | 50.0 |
| Developer ergonomics | 77.5 |
| Access clarity | 85.5 |

**Agent readiness 59.3** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | verified |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | yes |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 45.1** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/archbee/](https://apis.io/providers/archbee/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Archbee: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/archbee/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
