---
description: '2025-03-26'
---

# JSON Schema Definition

This section provides the formal JSON Schema for validating opt-out declarations under the TDM·AI Protocol. The schema ensures that all declarations follow a consistent, machine-readable structure, enabling reliable processing across tools, platforms, and compliance systems.

Each declaration expresses the rightsholder’s preferences regarding the use of their content for:

* Text and Data Mining (TDM)
* AI Training
* Generative AI Training

The specification requires each usage type (`TDM`, `AiTraining`, and `genAiTraining`) to be declared independently using one of two values:

* `"usagePermission"` — use is explicitly allowed
* `"usageReservation"` — use is explicitly reserved

The schema defines required fields, permitted values, and semantic constraints. It also supports optional fields for lifecycle operations such as versioning, updates, and revocations, using metadata like `intent`, `summary`, `policy`, and timestamps.

This schema is designed to be:

* Interoperable – compatible with multiple opt-out systems
* Future-proof – allowing for optional metadata and extensibility

Implementations are expected to validate usage reservation declarations against this schema before processing or honouring them. In specific use-cases, they MAY additionally want to reject or ignore any declarations containing unknown fields, i.e. by adding `"additionalProperties": false` at the root level of the schema.

The following schema suffices to validate conformance to this core data model.

{% code overflow="wrap" %}
```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://docs.tdmai.org/schema/usage-reservation-v1.json",
  "title": "Usage Reservation Declaration",
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
    "TDM": {
      "type": "string",
      "description": "Declared usage status for general text and data mining.",
      "enum": ["usagePermission", "usageReservation"]
    },
    "AiTraining": {
      "type": "string",
      "description": "Declared usage status for AI training (non-generative).",
      "enum": ["usagePermission", "usageReservation"]
    },
    "genAiTraining": {
      "type": "string",
      "description": "Declared usage status for generative AI training.",
      "enum": ["usagePermission", "usageReservation"]
    },
    "reference": {
      "type": "string",
      "description": "Reference to an updated or previous declaration (e.g. declarationID)."
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
