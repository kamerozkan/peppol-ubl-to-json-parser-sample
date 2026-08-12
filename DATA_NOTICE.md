# Data Notice

## Purpose

This repository documents `peppol-ubl-to-json-parser` with three paired input and
output examples plus a standalone Dataset JSON Schema. It is an independent,
unofficial technical sample and is not endorsed by a standards body, tax
authority, validator vendor, Peppol authority, Access Point, or invoice
recipient.

## Snapshot and evidence class

| Field | Verified value |
|---|---|
| Snapshot date | `2026-07-30` |
| Actor ID | `2H8UdIY1VkrGgFZh4` |
| Actor status | `PUBLIC STORE LISTING` |
| Successful build | `0.0.1` |
| Event contract | `document-processed` at `$0.005` |
| Evidence class | real local pinned-engine contract evidence |

Local contract examples ran the pinned KoSIT 1.6.2 and Peppol BIS Billing 3.0.20-hotfix stack. They are not hosted or live Store results.

The Actor is now available through its [public Store listing](https://apify.com/kamerozkan/peppol-ubl-to-json-parser). Local contract results have `billable: false` because they were produced outside an Apify PPE run. They prove the pinned processing contract exercised locally, not a hosted charge or public lifecycle.

## Input provenance

| # | Stem | Fixture | SHA-256 observed in result |
|---:|---|---|---|
| 01 | `01_invoice` | Peppol BIS Invoice | `1b7cc3ff1834c8963f2c93f30f171b58002cbf0b2c52dc8765e7e83aebb9f7c9` |
| 02 | `02_credit_note` | Peppol BIS CreditNote | `08e0ad82e0dbe7e16d7533c01761843343a56954ea24881d0f7f1cce06f8879e` |
| 03 | `03_allowance_invoice` | Peppol allowance and multi-VAT invoice | `aa3df18eb8c634624637eb229891d989c5cfb7cd0d08894ff8e58c58f247ea5b` |

The input JSON files link to public fixtures at immutable commits or version
tags where available. The fixture bytes are not copied into this repository.
Each linked document remains governed by its upstream license and terms.

## Output provenance

Each output is an exact field subset from a hosted Dataset row or an exact
projection from a real local engine result. Projection removes bulky trace,
finding, and raw-report material; it does not invent replacement values.
`producedAt`, source digests, engine digests, target digests, status values,
and error codes are retained when present.

Hosted owner-side provenance:

- ZUGFeRD PDF parser build `0.0.6`: runs `eH5xbA5flKNgEoO0q`,
  `q2vDgyT5AM9mGXGoe`, and `GqxUtLATVjLlKuiaI`.
- XRechnung parser build `0.0.3`: runs `vDoLHAXakiHa2XevL`,
  `iVTmKY39aMbv6zsKk`, and `W1EFkJfrdcmgZugxr`.

The run and Dataset records are not made public by this repository. IDs are
included for owner-side audit provenance only.

## Privacy and security

No access token, cookie, signed URL, webhook secret, customer account ID, or
private KVS URL belongs in this repository. Public fixtures may contain
synthetic invoice parties, addresses, tax identifiers, bank data, amounts, and
line items under upstream terms.

Customer runs can contain personal data and confidential accounting data.
Validation reports, generated XML, extracted XML, and source PDFs can reproduce
the full invoice. Users are responsible for lawful processing, authorization,
access control, retention, deletion, and contractual obligations.

## Interpretation limits

- Technical conformance is not legal or tax validity.
- A parser does not prove authenticity, delivery, payment, or recipient acceptance.
- Peppol document validation is not AS4 transport or network delivery.
- A ZUGFeRD 1.0 upgrade does not prove legacy source-to-upgrade semantic identity.
- `CONVERTED` does not mean `LOSSLESS`.
- `LOSSLESS` is used only when the recorded canonical comparisons are complete and equivalent.
- Local evidence is not a hosted availability or billing claim.

## License boundary

MIT covers this repository's original text, result projections, and schema
adaptation. It does not relicense EN 16931, XRechnung, ZUGFeRD, Factur-X,
Peppol BIS, UBL, CII, KoSIT, Mustangproject, phax, public fixtures, third-party
software, specifications, trademarks, or report formats.
