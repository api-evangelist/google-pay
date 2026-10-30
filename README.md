# Google Pay

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

Google Pay is Google's digital wallet and payment surface, exposed to developers as a family of distinct APIs rather than one endpoint. The Google Pay API for Web and Android is a client-side payment sheet that returns a signed, ECIES-encrypted payment token for a merchant's gateway to decrypt; the Google Wallet API is a REST service on walletobjects.googleapis.com for issuing loyalty cards, event tickets, boarding passes, transit tickets, gift cards and offers; Google Standard Payments carries the integrator APIs for issuers and PSPs; and the Google Pay & Wallet Developer MCP server gives AI coding agents live access to merchant profiles, integration status and the official documentation.

**Areas:** Agentic Commerce · Checkout · Contactless Payments · Digital Wallet · Merchants · Mobile Payments · Payments · Tokenization

## Google Pay on APIs.io

Everything profiled for Google Pay is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/google-pay/](https://apis.io/providers/google-pay/)** — or go straight to one of the APIs or properties below.

### APIs (9)

- [Google Pay API](https://apis.io/apis/google-pay/google-pay-api/) — Enables integration of the Google Pay payment method into web applications, allowing merchants to accept payments from cards saved to Google Accounts. The…
- [Google Pay API for Android](https://apis.io/apis/google-pay/google-pay-api-for-android/) — Enables integration of Google Pay into Android applications, allowing users to pay with cards saved to their Google Account. The API provides methods to…
- [Google Wallet API](https://apis.io/apis/google-pay/google-wallet-api/) — APIs for creating and managing digital passes for Google Wallet, including loyalty cards, event tickets, boarding passes, transit tickets, gift cards,…
- [Google Pay Facilitated Transaction Event API](https://apis.io/apis/google-pay/google-pay-facilitated-transaction-event-api/) — Provides services hosted by Google for processing facilitated payment events as part of Google Standard Payments. Payment integrators use this API to report…
- [Google Pay Virtual Cards API](https://apis.io/apis/google-pay/google-pay-virtual-cards-api/) — Enables payment integrators to enroll cards, retrieve virtual card numbers, manage transactions, and handle authentication challenges for virtual card…
- [Google Pay Push Provisioning API](https://apis.io/apis/google-pay/google-pay-push-provisioning-api/) — Allows card issuers to provision payment cards directly into Google Pay and Google Wallet from their own applications. Issuers can set default payment…
- [Google Pay Payment Card Recognition API](https://apis.io/apis/google-pay/google-pay-payment-card-recognition-api/) — Enables Android applications to scan credit and debit cards using the device camera to extract card number and expiration date through on-device optical…
- [Google Pay India Merchant SDK](https://apis.io/apis/google-pay/google-pay-india-merchant-sdk/) — A toolkit for developers in India to integrate their Android, iOS, and web applications with Google Pay for accepting UPI and card-based payments. Supports…
- [Google Universal Commerce Protocol](https://apis.io/apis/google-pay/google-universal-commerce-protocol/) — A standard for securely and efficiently exchanging commerce data between merchant and platform systems to enable checkout experiences directly on Google…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Google Pay & Wallet Developer MCP server](https://apis.io/servers/google-pay/google-pay-wallet-developer-mcp-server/)

#### JSON Schema (1)

The data models the API reads and writes.

- [Google Pay Payment Handler Configuration](https://apis.io/schemas/google-pay/google-pay-ucp-payment-handler-config/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Google Pay Authentication](https://apis.io/security/google-pay/google-pay-authentication/)
- [Google Pay Domain Security](https://apis.io/security/google-pay/google-pay-domain-security/)
- [Google Pay Vulnerability Disclosure](https://apis.io/security/google-pay/google-pay-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Google Pay Scopes](https://apis.io/scopes/google-pay/google-pay-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Google Pay Plans Pricing](https://apis.io/plans/google-pay/google-pay-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Google Pay Rate Limits](https://apis.io/rate-limits/google-pay/google-pay-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Google Pay Finops](https://apis.io/finops/google-pay/google-pay-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.google.com/)
- [Documentation](https://developers.google.com/pay/api/web)
- [Getting started](https://developers.google.com/pay/api/web/guides/tutorial)
- [API reference](https://developers.google.com/pay/api/web/reference/client)
- [Pricing](https://developers.google.com/pay/api/faq)
- [Sign up](https://pay.google.com/business/console/)
- [Support](https://developers.google.com/pay/api/web/support/troubleshooting)
- [Changelog](https://developers.google.com/pay/api/web/support/release-notes)
- [Blog](https://developers.googleblog.com/)
- [Security](https://g.co/vrp)
- [Terms of service](https://payments.developers.google.com/terms/sellertos)
- [Privacy policy](https://policies.google.com/privacy)
- [GitHub](https://github.com/google-pay)
- [Status](https://developers.google.com/pay/api/status)

## API Evangelist rating

**Kin Score 49.8** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 86.7 |
| Contract quality | 0.0 |
| Contract governance | 18.2 |
| Operational transparency | 65.8 |
| Developer ergonomics | 73.2 |
| Access clarity | 65.8 |

**Agent readiness 21.4** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | platform (partial credit) |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 36.6** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/google-pay/](https://apis.io/providers/google-pay/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Google Pay: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/google-pay/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
