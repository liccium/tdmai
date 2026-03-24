---
description: '2025-04-11'
---

# JSON Schema Definition

{% hint style="info" %}
**Note on Alignment with IETF Drafts and Current Status**

This specification on the Usage Preferences Vocabulary for the TDM·AI Protocol currently aligns with version 02 of the draft‑ietf‑aipref‑vocab‑02 published by the Internet Engineering Task Force (IETF) as of July 21 2025. [datatracker.ietf.org+2datatracker.ietf.org+2](https://datatracker.ietf.org/doc/html/draft-ietf-aipref-vocab-02?utm_source=chatgpt.com)\
\
It is important to note that the IETF work on the “AI Preferences” vocabulary remains a **work in progress**. The draft is still under discussion, subject to change, and does not yet constitute a finalized standard. [datatracker.ietf.org+1](https://datatracker.ietf.org/doc/draft-ietf-aipref-vocab/02/?utm_source=chatgpt.com)\
\
We have chosen to use this particular draft version as a **reference point** to illustrate how a domain-based attachment mechanism (as proposed by the IETF) can be **translated** into a registry-based system — that is, how preference declarations can be persistently and verifiably associated with individual digital assets via a registry rather than relying solely on domain- or location-based signaling.\
\
As the IETF draft evolves, we expect to revisit and update our alignment accordingly. Until then, this documentation should be regarded as **preliminary guidance**, not a definitive implementation.
{% endhint %}

This section provides the formal JSON Schema for validating declarations under the **TDM·AI Protocol**. The schema ensures that all declarations follow a consistent, machine-readable structure, enabling reliable processing across tools, registries, and compliance systems.

Each declaration expresses the rightsholder’s preferences regarding the use of their content for:

* Automated Processing (`all`)
* AI Training (`train-ai`)
* Generative AI Training (`train-genai`)
* AI Use / Inference (`ai-use`)
* Search (`search`)

Usage preferences are encoded using the IETF-compatible tokens:

* `"true"` — use is explicitly allowed
* `"false"` — use is explicitly disallowed (opt-out)

The schema defines required fields, permitted values, and optional metadata for lifecycle management such as updates and policy declarations.

Implementations are expected to validate usage reservation declarations against this schema before processing or honouring them. In specific use-cases, they MAY additionally want to reject or ignore any declarations containing unknown fields, i.e. by adding `"additionalProperties": false` at the root level of the schema.

The following schema suffices to validate conformance to this core data model.

{% code overflow="wrap" %}
```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://docs.tdmai.org/technical-specification/json-schema-definition",
  "title": "TDM·AI Usage Declaration",
  "type": "object",
  "required": ["version", "iscc", "intent"],
  "properties": {
    "version": {
      "type": "string",
      "description": "The version of the reservation declaration schema.",
      "const": "1.0"
    },
    "iscc": {
      "type": "string",
      "description": "A unique content identifier using the ISCC standard (ISO 24138:2024)."
    },
    "all": {
      "type": "string",
      "description": "Preference for general automated processing.",
      "enum": ["true", "false"]
    },
    "train-ai": {
      "type": "string",
      "description": "Preference for AI training (non-generative).",
      "enum": ["true", "false"]
    },
    "train-genai": {
      "type": "string",
      "description": "Preference for generative AI training.",
      "enum": ["true", "false"]
    },
    "ai-use": {
      "type": "string",
      "description": "Preference for inference-time use of the asset as input to a trained model.",
      "enum": ["true", "false"]
    },
    "search": {
      "type": "string",
      "description": "Preference for inclusion in search applications.",
      "enum": ["true", "false"]
    },
    "reference": {
      "type": "string",
      "description": "Reference to a prior declaration (CID) this one updates or supersedes."
    },
    "intent": {
      "type": "string",
      "description": "Type of declaration in its lifecycle.",
      "enum": ["activate", "update", "supersede"],
      "default": "activate"
    },
    "summary": {
      "type": "string",
      "description": "Optional human-readable summary of declared permissions or reservations."
    },
    "policy": {
      "type": "string",
      "description": "Optional human-readable reference to the targeted compliance regime (e.g. CDSM, AI Act)."
    }
  },
  "additionalProperties": false
}
```
{% endcode %}
