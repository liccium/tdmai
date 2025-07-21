---
description: '2025-07-21'
---

# JSON Schema Definition

This section provides the formal JSON Schema for validating declarations under the **TDM·AI Protocol**. The schema ensures that all declarations follow a consistent, machine-readable structure, enabling reliable processing across tools, registries, and compliance systems.

Each declaration expresses the rightsholder’s preferences regarding the use of their content for:

* Automated Processing (`all`)
* AI Training (`train-ai`)
* Generative AI Training (`train-genai`)
* AI Use / Inference (`ai-use`)
* Search (`search`)

Usage preferences are encoded using the IETF-compatible tokens:

* `"y"` — use is explicitly allowed
* `"n"` — use is explicitly disallowed (opt-out)

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
      "enum": ["y", "n"]
    },
    "train-ai": {
      "type": "string",
      "description": "Preference for AI training (non-generative).",
      "enum": ["y", "n"]
    },
    "train-genai": {
      "type": "string",
      "description": "Preference for generative AI training.",
      "enum": ["y", "n"]
    },
    "ai-use": {
      "type": "string",
      "description": "Preference for inference-time use of the asset as input to a trained model.",
      "enum": ["y", "n"]
    },
    "search": {
      "type": "string",
      "description": "Preference for inclusion in search applications.",
      "enum": ["y", "n"]
    },
    "reference": {
      "type": "string",
      "description": "Reference to a prior declaration (CID) this one updates or supersedes."
    },
    "intent": {
      "type": "string",
      "description": "Type of declaration in its lifecycle.",
      "enum": ["activate", "update", "supercede"],
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
