---
description: '2025-11-04'
---

# TDMrep Vocabulary

This section defines the **W3C TDMrep vocabulary** as used by the TDM·AI Protocol to express machine-readable rights reservations for digital content. Rightsholders and publishers use TDMrep declarations to signal their preferences regarding text and data mining (TDM) – including AI training and generative AI training – and publish those declarations to the TDM·AI registry, where they become persistently discoverable and verifiable.

{% hint style="info" %}
**Note on Alignment with IETF Drafts and Current Status**

The TDM·AI Protocol currently uses the **W3C TDMRep vocabulary** ([https://www.w3.org/community/reports/tdmrep](https://www.w3.org/community/reports/tdmrep/CG-FINAL-tdmrep-20240510/)) as the basis for expressing usage preferences. TDMrep is a W3C Community Group Final Report providing a standardised mechanism for rightsholders to declare TDM reservations in a machine-readable way.

We have chosen TDMrep as a stable and broadly adopted vocabulary that aligns well with the registry-based attachment model used by TDM·AI. Unlike domain- or location-based signaling, Liccium binds TDMrep declarations to individual digital assets via ISCC fingerprints (ISO 24138:2024), making preferences persistent and verifiable regardless of how content is distributed.
{% endhint %}

## Vocabulary Definition

The TDMrep vocabulary defines two terms:

| Category Name   | Key               | Description                                                                                                                                   |
| --------------- | ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| TDM Reservation | `tdm-reservation` | Indicates whether TDM rights are reserved (`1`) or not reserved (`0`) for a resource                                                          |
| TDM Policy      | `tdm-policy`      | A URI pointing to a human- or machine-readable policy document specifying the conditions under which the content may be used for TDM purposes |

`tdm-reservation` is the required field. `tdm-policy` is optional and only meaningful when `tdm-reservation` is set to `1`.

### 1. TDM Reservation

`tdm-reservation` is a binary signal. A value of `1` means the rightsholder explicitly reserves all TDM rights – automated processing, including AI training, is not permitted without authorisation. A value of `0` means TDM use is permitted without contacting the rightsholder.

This single field covers the full scope of TDM activities, including text and data mining for commercial purposes, AI model training, and generative AI training.

### 2. TDM Policy

`tdm-policy` is an optional URI that links to a policy document where the rightsholder may specify more granular conditions – for example, permitted uses, licensing terms, or the legal basis for the reservation.

When present, automated systems are expected to retrieve and process the linked policy document to determine whether a specific use is permitted under the stated terms.

**Example:**

```json
{
  "tdm-reservation": 1,
  "tdm-policy": "https://example.com/tdm-policy"
}
```

A policy reference without a reservation has no effect. The `tdm-reservation` field must be set to `1` for the policy to be operative.

### Relationship to TDM·AI Registry Declarations

In the TDM·AI Protocol, TDMrep terms are not expressed at the domain level or embedded in content files. Instead, they are bound to ISCC fingerprints and published as signed declarations to federated registries. This registry-based approach ensures that rights reservations remain accessible even when content is shared, reformatted, or metadata is stripped from the original file.

Any party generating the ISCC for a piece of content can query the registry and retrieve the associated TDMrep declaration – without needing to know the original source domain or hosting location.
