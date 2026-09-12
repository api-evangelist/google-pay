---
name: google-pay-merchant-onboarding
description: >-
  Create and maintain a Google Pay merchant business profile and inspect its Google Pay
  integrations, using the Google Pay & Wallet Developer MCP server. Use when onboarding a new
  merchant, correcting merchant support contact details, or checking whether an integration is
  live.
api: Google Pay & Wallet Developer MCP server
endpoint: https://paydeveloper.googleapis.com/mcp
operations:
  - create_merchant
  - list_merchants
  - update_merchant
  - list_google_pay_integrations
  - search_documentation
generated: '2026-09-12'
method: generated
source: mcp/google-pay-mcp-tools-list.json (verbatim anonymous tools/list, HTTP 200, 2026-09-12)
---

# Onboard and maintain a Google Pay merchant

Every tool name and parameter below comes from the server's own `tools/list` response saved at
`mcp/google-pay-mcp-tools-list.json`. Nothing here is invented.

## Before you start

- The server is remote: `https://paydeveloper.googleapis.com/mcp`. There is no npx package.
- It authenticates with **OAuth 2.0 + Cloud IAM** and **does not accept API keys**. You need the
  IAM role `roles/mcp.toolUser` and the scope
  `https://www.googleapis.com/auth/paydeveloper.merchant`.
- `tools/list` answers anonymously; every tool call does not.

## Steps

1. **See what already exists.** Call `list_merchants` (no required arguments; optional `view`).
   Onboarding a merchant that already exists is the most common wasted call.
2. **Create the profile if it is missing.** Call `create_merchant` with the required `merchant`
   object — display name, merchant category code (MCC), corporate website, and customer support
   details. Note the annotation the server itself publishes: `idempotentHint: false`. Calling it
   twice creates two merchants, and **there is no delete_merchant tool** — a merchant created in
   error cannot be removed through this surface. Confirm step 1 came back empty first.
3. **Check the integration state.** Call `list_google_pay_integrations` with the required
   `merchantId` to read the current status and configuration of that merchant's Google Pay
   integrations.
4. **Correct profile fields.** Call `update_merchant` with `merchantId` plus any of
   `displayName`, `mcc`, `corporateWebsiteUrl`, `customerSupportEmail`, `customerSupportPhone`,
   `customerSupportWebsiteUrl`. This one is `idempotentHint: true`, so a repeated identical write
   is safe. There is no revision history — capture the previous value before you overwrite it if
   you may need to roll back.
5. **Look anything up in the docs.** `search_documentation` takes a required `userQuery` and an
   optional `languageCode`, and returns document chunks with title, content and URI from the
   official Google Pay and Google Wallet documentation.

## What this skill cannot do

Creating a merchant profile is **not** production access. Going live still requires a human loop
Google does not expose as a tool: accepting the Google Pay API Terms of Service and Acceptable Use
Policy, registering the top-level domain that calls the API, and submitting integration
screenshots for review by the Google Pay team. See
`https://developers.google.com/pay/api/web/guides/test-and-deploy/deploy-production-environment`.

## Error handling

The client-side Google Pay API returns a `PaymentsError` with `statusCode` and `statusMessage`
(`BUYER_ACCOUNT_ERROR`, `DEVELOPER_ERROR`, `MERCHANT_ACCOUNT_ERROR`, `INTERNAL_ERROR`) — see
`errors/google-pay-problem-types.yml`. Only `INTERNAL_ERROR` is worth retrying. There is **no
idempotency key** on any Google Pay surface (`conventions/google-pay-conventions.yml`,
`idempotency.coverage: none`), so never blind-retry a write whose outcome you did not read.
