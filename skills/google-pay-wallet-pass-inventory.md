---
name: google-pay-wallet-pass-inventory
description: >-
  Inventory Google Wallet pass issuers and pass classes and validate a pass JWT before issuing it.
  Use when auditing which pass templates exist under an issuer, or when a save-to-wallet link is
  being rejected.
api: Google Pay & Wallet Developer MCP server
endpoint: https://paydeveloper.googleapis.com/mcp
operations:
  - list_pass_issuers
  - list_pass_classes
  - validate_pass_jwt
  - search_documentation
generated: '2026-09-12'
method: generated
source: >-
  mcp/google-pay-mcp-tools-list.json (verbatim anonymous tools/list, HTTP 200, 2026-09-12) ·
  discovery/google-pay-walletobjects-v1-discovery.json (Google Wallet API v1 Discovery, rev 20260911)
---

# Audit Google Wallet passes

Read-only. The scope this needs is
`https://www.googleapis.com/auth/paydeveloper.issuer.readonly`.

## Steps

1. **List the issuers.** `list_pass_issuers` takes no arguments and returns every pass issuer
   registered in the Google Wallet business console for the authenticated account. It corresponds
   to the REST method `walletobjects.issuer.list`
   (`GET walletobjects/v1/issuer`).
2. **List the classes under one issuer.** `list_pass_classes` requires `issuerId` and accepts
   `passType` and `view`. One tool call fans out across the seven per-type REST list methods —
   `genericclass.list`, `loyaltyclass.list`, `offerclass.list`, `giftcardclass.list`,
   `eventticketclass.list`, `flightclass.list`, `transitclass.list` — so `passType` is how you
   narrow it.
3. **Validate before you issue.** `validate_pass_jwt` takes `passJwt` **or** `passJson` (neither
   is individually required; supply one). This is the only rehearsal surface Google gives for pass
   issuance — use it before minting a save link, because there is no dry-run flag anywhere else.
4. **Look up the field semantics.** `search_documentation` with a `userQuery` naming the pass type
   returns the relevant Wallet reference chunks.

## What this skill deliberately does not do

Issuing passes is **not** available through MCP. 91 of the 99 Google Wallet REST methods have no
MCP tool — every `*object.insert`, `*.patch`, `*.update`, `permissions.update`, `smarttap` and
`jwt.insert` method among them (see `mcp/google-pay-tool-crosswalk.yml`). To create or update a
pass you must call `walletobjects.googleapis.com` directly with a service-account OAuth token on
the scope `https://www.googleapis.com/auth/wallet_object.issuer`. Note that scope is coarse: it
grants read *and* write across every pass type, so there is no read-only Wallet REST credential.

Also note the Discovery document exposes **no delete method for any pass type** — a pass class or
object is retired by moving its state to `EXPIRED`, not by deleting it, and Google publishes no
window for that (`conventions/google-pay-conventions.yml`, `reversibility`).
