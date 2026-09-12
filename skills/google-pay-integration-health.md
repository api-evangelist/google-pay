---
name: google-pay-integration-health
description: >-
  Read post-integration performance and error metrics for a Google Pay merchant, and look up the
  official remediation in Google's documentation. Use when diagnosing a drop in Google Pay
  conversion or a spike in checkout errors.
api: Google Pay & Wallet Developer MCP server
endpoint: https://paydeveloper.googleapis.com/mcp
operations:
  - query_merchant_performance
  - query_merchant_error_metrics
  - list_google_pay_integrations
  - search_documentation
generated: '2026-09-12'
method: generated
source: mcp/google-pay-mcp-tools-list.json (verbatim anonymous tools/list, HTTP 200, 2026-09-12)
---

# Diagnose a Google Pay integration

All four tools used here are annotated `readOnlyHint: true` by the server itself — this skill
cannot change anything.

## Steps

1. **Identify the merchant.** `list_merchants` (optional `view`) to resolve a `merchantId`.
2. **Read the headline numbers.** `query_merchant_performance` with required `merchantId` and
   optional `timeRange` returns high-level aggregated performance and post-integration metrics.
3. **Read the failures.** `query_merchant_error_metrics` with required `merchantId` and optional
   `timeRange` returns detailed error metrics for that merchant business profile. Start here when
   conversion drops — the error mix tells you whether the problem is the shopper
   (`BUYER_ACCOUNT_ERROR`), the request (`DEVELOPER_ERROR`), or the registration
   (`MERCHANT_ACCOUNT_ERROR`).
4. **Confirm the configuration.** `list_google_pay_integrations` with required `merchantId`
   returns the current status and configuration of each integration — a common cause of a sudden
   zero is a domain that is no longer registered against the business profile.
5. **Get the official fix.** `search_documentation` with a `userQuery` naming the exact status
   code returns the relevant chunks of Google's troubleshooting pages with their URIs.

## Reading the numbers honestly

- There are no pagination parameters on these tools; the server returns what it returns.
- Google publishes **no rate-limit headers** on any Google Pay surface
  (`rate-limits/google-pay-rate-limits.yml`), so there is no runtime signal to pace a polling
  loop against. Poll conservatively.
- Money movement is not visible here. Authorisations, declines and refunds belong to the
  merchant's gateway/PSP, not to Google Pay — do not expect decline codes from these tools.
