---
description: '2025-07-21'
---

# Updates

## Updating Usage Preferences

A rightsholder who has previously declared a usage preference – whether to allow or disallow certain types of use – may later choose to **update** that declaration. An update is a machine-readable statement that supersedes a prior declaration for the same asset and explicitly communicates a change in permissions or restrictions.

While permission is generally assumed by default (in the absence of an opt-out or opt-in requirement), publishing an explicit update is important in scenarios where:

* A prior opt-out or usage restriction is already in circulation and may still be active in third-party systems
* The declaring party wishes to modify or replace an earlier declaration (e.g., due to licensing changes or policy shifts)
* There is a need to maintain continuity and transparency in the audit trail of usage preferences

## Declaration Format for Updates

Updates use the same JSON structure as any standard TDM·AI usage declaration. An update is intended to **replace** a previously issued declaration for the same asset.

To indicate that a declaration is an **update**, two optional fields may be included:

* `"intent": "update"` — signals that the purpose of this declaration is to revise or replace a prior statement.
* `"reference"` — provides the **Declaration ID** (a CID v1 hash) of the earlier declaration being replaced.

While `"intent"` serves as a **semantic hint** to systems, `"reference"` creates an **explicit link** to the prior declaration. This improves auditability and allows registries to track the update chain over time.

## Example: Update of a Previous Usage Reservation

This example lifts a prior reservation and re-authorises the use of the content for all types of automated processing, including TDM, AI training, and generative AI training.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "all": "true",
  "intent": "update",
  "reference": "bafyreibxxxxxxxyyyyyyzzzzzzzddeeeeeeeeeeeeeeeeeeeeeeeee"
}
```
{% endcode %}

In this case:

* `all: "true"` allows all uses (implicitly permitting `train-ai` and `train-genai`)
* `reference` points to the **Declaration ID** (CID v1) of the earlier declaration being replaced
* `intent: "update"` marks the purpose of the change and makes the revocation explicit and traceable for downstream systems.

Registries and consumers can use this linkage to deprecate or replace the earlier declaration in their compliance pipelines.

{% hint style="info" %}
### Why issue a revocation in the context of the EU CDSM?

Under the EU’s Copyright in the Digital Single Market Directive (CDSM Directive, 2019/790), the use of copyrighted content for Text and Data Mining (TDM) is governed by statutory exceptions rather than by traditional licensing.

Two Key Legal Provisions Define the Framework:

* Article 3 — Allows TDM for research organisations and cultural heritage institutions without needing prior permission. No opt-out is possible.
* Article 4 — Allows TDM for all other users, including commercial actors, unless the rightsholder has explicitly reserved their rights in a machine-readable way.

In practice, this means that:

> **If no reservation is declared under Article 4, TDM is permitted by default.**

This legal default – referred to in Article 4(3) – makes it lawful to mine content for patterns, trends, or correlations unless the rightsholder has clearly expressed a reservation.



Even though permission is assumed in the absence of a reservation, an explicit revocation of a previous reservation is often necessary or useful. This is because:

* Third-party systems may cache or store earlier declarations, continuing to enforce restrictions that are no longer intended.
* Archived opt-outs may persist in datasets used by AI developers or data brokers.
* Researchers and developers may require proof of permission, especially if access was previously denied.

A revocation declaration serves to:

* &#x20;Remove any lingering restrictions from prior machine-readable opt-outs
* Clearly signal that the rightsholder now allows TDM, AI training, or generative AI training

Revocations ensure transparency, help maintain up-to-date compliance, and support interoperability across evolving systems.
{% endhint %}
