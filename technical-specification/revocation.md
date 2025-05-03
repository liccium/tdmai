---
description: '2025-05-04'
---

# Revocation

## Updating Usage Reservation (Opt-Out)

In certain situations, a rightsholder, who has previously expressed a permission or reservation may choose to reverse that decision. An revocation is a machine-readable statement that explicitly indicates the removal of prior permission or restrictions on the use of a work for Text and Data Mining (TDM), AI training, and/or generative AI training.

While permission is generally the default in the absence of an opt-out (or the absence of an opt-in policy), explicitly marking subsequent declarations as updates is useful in cases where a prior opt-out was published and may still be active in third-party systems, or the continuity of record histories is otherwise broken. Revocation ensures clarity and removes ambiguity for downstream users and compliance systems.

A revocation is expressed using the same JSON structure as a regular declaration of a usage preference. To make the revocation intent explicit, a revoking or updating re-declaration may include the optional property `"intent": "update"` as a hint that thus declaration intends to replace an older one.

## Example: Revocation of a Previous Usage Reservation

This example revokes a previous reservation for a specific asset, re-authorising its use for **all purposes**, including TDM, AI training, and generative AI training.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "intent": "update",
  "reference": "[[declarationID]]",
  "reservationSummary": "The previous reservation has been revoked. Content may now be used for TDM, AI training, and generative AI training.",
  "reservationPolicy": "This statement revokes any previously issued usage reservations for this work. The content may now be used for text and data mining (TDM), training of general-purpose AI systems, and training of generative AI systems. This update supersedes all prior restrictions."
}
```
{% endcode %}

{% hint style="info" %}
**Technical Notes:**

* The `"intent": "update"` field makes the revocation explicit and traceable for downstream systems.
{% endhint %}

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
