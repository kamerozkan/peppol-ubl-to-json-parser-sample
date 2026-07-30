> **Release preview:** this Actor is private. These files document the current contract and evidence; they are not a public API availability claim.

# Peppol BIS Billing UBL to JSON Parser: JSON Examples and Schema

[![Apify Actor](https://img.shields.io/badge/Apify-PRIVATE%20HOSTED-BUILD%20PREVIEW-00c7b7?logo=apify)](https://apify.com/kamerozkan)
![Build](https://img.shields.io/badge/build-0.0.1%20SUCCEEDED-2f855a)
![PPE](https://img.shields.io/badge/document--processed-%240.005-4c1)
![Samples](https://img.shields.io/badge/examples-3%20paired%20JSON-2f855a)
![License](https://img.shields.io/badge/license-MIT-blue)

Validate Peppol BIS Billing UBL Invoice and CreditNote documents and normalize them into JSON for ERP and AP workflows.

This repository is a flat, GitHub-friendly sample pack with three paired Actor
inputs, three Dataset result rows, and a standalone JSON Schema. It is useful
for ERP integration design, AP automation, e-invoice testing, and search-driven
technical discovery.

## Verified snapshot

| Field | Value |
|---|---|
| Actor | `peppol-ubl-to-json-parser` |
| Actor ID | `2H8UdIY1VkrGgFZh4` |
| Status | `PRIVATE HOSTED-BUILD PREVIEW` |
| Successful build | `0.0.1` |
| Custom event | `document-processed` |
| Exact event price | `$0.005` |

The exact source billing contract is $0.005 per evaluated document. Platform PPE was not configured at the snapshot.

Local contract examples ran the pinned KoSIT 1.6.2 and Peppol BIS Billing 3.0.20-hotfix stack. They are not hosted or live Store results.

## What the Actor does

- UBL Invoice and CreditNote processing with active Peppol document rules
- CustomizationID, ProfileID, syntax, source digest, and normalized invoice fields
- explicit SBDH unwrap status without claiming SBDH validation

## Example matrix

| # | Scenario and input | Output | Result |
|---:|---|---|---|
| 01 | [Peppol BIS Invoice](01_invoice_input.json) | [Dataset row](01_invoice_output.json) | `SUCCEEDED` / `ACCEPTED` |
| 02 | [Peppol BIS CreditNote](02_credit_note_input.json) | [Dataset row](02_credit_note_output.json) | `SUCCEEDED` / `ACCEPTED` |
| 03 | [Peppol allowance and multi-VAT invoice](03_allowance_invoice_input.json) | [Dataset row](03_allowance_invoice_output.json) | `SUCCEEDED` / `ACCEPTED` |

Example outputs are exact hosted field subsets or projections from real local
engine results. No omitted value was reconstructed. See
[`DATA_NOTICE.md`](DATA_NOTICE.md) for run IDs, fixture hashes, status, and the
hosted-versus-local evidence boundary.



## Dataset contract

[`dataset_record.schema.json`](dataset_record.schema.json) is adapted directly
from the production Dataset contract and narrowed to this Actor name. Money and
quantity values remain decimal strings. Raw XML, PDFs, and generated artifacts
belong in the run key-value store, not in Dataset rows.

Validate an output with any JSON Schema Draft 7 implementation:

```bash
python -m jsonschema -i 01_invoice_output.json dataset_record.schema.json
```

## Interpretation boundary

This is document-rule processing only. It is not an Access Point, SMP or SML discovery, AS4 transport, delivery receipt, network acceptance, or Peppol certification service.

`ACCEPTED`, `CONFORMANT`, or `CONVERTED` describes only the evidence explicitly
recorded by the pinned processing pipeline. It does not prove legal validity,
tax treatment, authenticity, signature validity, transmission, payment,
archival compliance, or recipient or network acceptance.

## Privacy

Do not publish customer invoices, raw reports, extracted XML, bank details,
tax identifiers, personal data, access tokens, cookies, or private KVS links.
The examples reference public upstream fixtures. You remain responsible for
lawful processing, access control, retention, and deletion.

## Related e-invoice Actor samples

- [ZUGFeRD and Factur-X PDF to JSON](https://github.com/kamerozkan/zugferd-facturx-pdf-to-json-sample)
- [XRechnung XML to JSON](https://github.com/kamerozkan/xrechnung-to-json-parser-sample)
- [Peppol BIS UBL to JSON](https://github.com/kamerozkan/peppol-ubl-to-json-parser-sample) (this repository)
- [ZUGFeRD to XRechnung](https://github.com/kamerozkan/zugferd-to-xrechnung-converter-sample)
- [UBL and CII conversion](https://github.com/kamerozkan/ubl-cii-format-converter-sample)

## License

MIT applies to this repository's original documentation, JSON projections, and
schema adaptation. It does not relicense standards, validator engines, public
fixtures, upstream repositories, third-party marks, or source documents.
