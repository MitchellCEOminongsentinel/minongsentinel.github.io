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

## Tax position

As stated by the store owner: Minong Sentinel is **not registered for GST** and no GST is charged while turnover is below the $75,000 GST registration threshold. Registration becomes compulsory within 21 days of the threshold being reached (actual or projected), at which point prices become GST-inclusive and tax invoices are issued on request.

## Pending compliance items

- ABN to be displayed on the store page and invoices. The ABN is separate from the GST threshold: business customers who are not given the supplier's ABN must withhold the top rate of tax from payments.
- Terms of sale and refund policy.

## Threshold tracking

The $75,000 GST threshold counts combined turnover from all enterprises operated as a sole trader. At the approved prices, the threshold is reached at roughly 758 Standard sales, 251 Professional sales, or 76 Enterprise sales in any 12-month period (or a mix). Track monthly.
