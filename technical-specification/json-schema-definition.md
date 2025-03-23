---
description: DRAFT for Discussion 2025-03-20
---

# JSON Schema Definition

This section provides the formal JSON Schema for validating opt-out declarations under the TDM·AI Protocol. The schema ensures that all declarations follow a consistent, machine-readable structure, enabling reliable processing across tools, platforms, and compliance systems.

Each declaration expresses the rightsholder’s preferences regarding the use of their content for:

* Text and Data Mining (TDM)
* AI Training
* Generative AI Training

The schema defines required fields, permitted values, and semantic constraints. It also supports optional fields for revocations, versioning, and timestamps to facilitate updates, traceability, and lifecycle management of declarations.

This schema is designed to be:

* Interoperable – compatible with multiple opt-out systems
* Hierarchically consistent – reflecting the vocabulary structure
* Future-proof – allowing for optional metadata and extensibility

Implementations are expected to validate opt-out declarations against this schema before processing or honoring them.

{% code overflow="wrap" %}
```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "title": "TDMAI Opt-Out Declaration",
  "type": "object",
  "required": ["iscc", "tdmOptOut", "TDMAI_summary", "TDMAI_policy"],
  "properties": {
    "iscc": {
      "type": "string",
      "description": "ISCC identifier for the declared asset."
    },
    "tdmOptOut": {
      "type": "object",
      "required": ["TDM", "aiTraining", "generativeAI"],
      "properties": {
        "TDM": {
          "type": "boolean",
          "description": "Permission for text and data mining (true = allowed, false = opt-out)."
        },
        "aiTraining": {
          "type": "boolean",
          "description": "Permission for general-purpose AI training (true = allowed, false = opt-out)."
        },
        "generativeAI": {
          "type": "boolean",
          "description": "Permission for generative AI training (true = allowed, false = opt-out)."
        }
      }
    },
    "TDMAI_summary": {
      "type": "string",
      "description": "Plain-language summary of the declaration."
    },
    "TDMAI_policy": {
      "type": "string",
      "description": "Detailed policy statement, possibly including legal references."
    },
    "revocation": {
      "type": "boolean",
      "description": "Indicates whether this declaration revokes a previously issued opt-out (default: false)."
    },
    "status": {
      "type": "string",
      "enum": ["active", "revoked", "superseded"],
      "description": "Current status of the declaration."
    },
    "version": {
      "type": "string",
      "description": "Optional semantic versioning string (e.g. '1.0.1')."
    },
    "modified": {
      "type": "string",
      "format": "date-time",
      "description": "Timestamp of the declaration or last update (ISO 8601 format)."
    }
  }
}
```
{% endcode %}
