# Minong Sentinel — Customer Store

Public sales site for Minong Sentinel. This repository publishes the store page (`index.html`) and the payment guide (`PAYMENT_GUIDE.md`).

## Approved price schedule

There is one approved schedule. It is the schedule published on the store page, in the payment guide, and in the deploy-branch payment interface:

| Tier | Price (AUD) | Access | Reference |
|------|-------------|--------|-----------|
| STANDARD | $99 | 30 days | STANDARD-001 |
| PROFESSIONAL | $299 | 90 days | PROFESSIONAL-001 |
| ENTERPRISE | $999 | 1 year | ENTERPRISE-001 |

## Payment method

Payments are received by NAB Business Osko transfer to the store PayID. Full customer instructions are in [PAYMENT_GUIDE.md](PAYMENT_GUIDE.md).

Bank account details (BSB/account number) are deliberately **not** stored in this repository. Customers use the PayID only.

## Security notes

- Do not add bank account details, BSB numbers, or account numbers to any file in this repository.
- Do not generate QR codes through third-party services (for example `api.qrserver.com`) — payment details embedded in external URLs are exposed to that service. QR images must be self-hosted and generated offline.
- This README previously contained a draft payment page with an exposed BSB and account number, third-party QR URLs, and an unapproved price schedule. It was removed on 2026-11-17 as part of the payment records audit. The old content remains visible in the repository's git history; treat that account number as public.

## Deployment

`netlify.toml` publishes the repository root. The deploy branch `deploy/minongsentinel777-quest` contains the QR payment interface, whose payment assets must be configured with verified, self-hosted QR images before launch.

## Pending compliance items

These cannot be completed without details only the store owner can provide:

- ABN to be displayed on the store page and invoices.
- GST registration status and the corresponding GST statement on the store page.
- Terms of sale and refund policy.
