---
description: DRAFT for Discussion 2025-03-20
---

# Revocation

## Opt-out Revocation

In certain situations, a rightsholder who has previously issued an opt-out declaration may choose to reverse that decision. An **opt-out revocation** is a machine-readable statement that explicitly indicates the removal of prior restrictions on the use of a work for Text and Data Mining (TDM), AI training, and/or generative AI training.

While permission is generally the default in the absence of an opt-out, an explicit revocation is useful in cases where a prior opt-out was published and may still be active in third-party systems. Revocation ensures clarity and removes ambiguity for downstream users and compliance systems.

A revocation is expressed using the same JSON structure as a regular opt-out declaration, but with all relevant categories marked as allowed (`true`). To make the intent clear, a revocation may include an optional `"revocation": true` flag or `"status": "revoked"`.

### **Example: Revocation of a Previous Opt-Out**

This example revokes a previous opt-out for a specific asset, reauthorizing its use for all purposes.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLECODE1234567890",
  "tdmOptOut": {
    "TDM": true,
    "aiTraining": true,
    "generativeAI": true
  },
  "revocation": true,
  "TDMAI_summary": "The previous opt-out declaration has been revoked. Content may now be used for TDM, AI training, and generative AI training.",
  "TDMAI_policy": "This statement revokes any previously issued opt-out declarations for this work. The content may now be used for text and data mining (TDM), training of general-purpose AI systems, and training of generative AI systems. This update supersedes all prior restrictions."
}
```
{% endcode %}

{% hint style="info" %}
####

### Why Issue a Revocation?

Under the EU’s Copyright in the Digital Single Market Directive (CDSM Directive, 2019/790), the use of copyrighted content for Text and Data Mining (TDM) is governed by statutory exceptions rather than by traditional licensing.

Two Key Legal Provisions Define the Framework:

* Article 3 — Allows TDM for research organisations and cultural heritage institutions without needing prior permission. No opt-out is possible.
* Article 4 — Allows TDM for all other users, including commercial actors, unless the rightsholder has explicitly reserved their rights in a machine-readable way.

In practice, this means that:

> **If no opt-out is declared under Article 4, TDM is permitted by default.**

This legal default – referred to in Article 4(3) – makes it lawful to mine content for patterns, trends, or correlations unless the rightsholder has clearly expressed a reservation.



Even though permission is assumed in the absence of an opt-out, an explicit revocation of a previous opt-out is often necessary or useful. This is because:

* Third-party systems may cache or store earlier declarations, continuing to enforce restrictions that are no longer intended.
* Archived opt-outs may persist in datasets used by AI developers or data brokers.
* Researchers and developers may require proof of permission, especially if access was previously denied.

A revocation declaration serves to:

* &#x20;Remove any lingering restrictions from prior machine-readable opt-outs
* Clearly signal that the rightsholder now allows TDM, AI training, or generative AI training

Revocations ensure transparency, help maintain up-to-date compliance, and support interoperability across evolving systems.
{% endhint %}
