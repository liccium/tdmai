---
description: '2025-03-26'
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
* Future-proof – allowing for optional metadata and extensibility

Implementations are expected to validate usage reservation declarations against this schema before processing or honouring them. In specific use-cases, they MAY additionally want to reject or ignore any declarations containing unknown fields, i.e. by adding `"additionalProperties": false` at the root level of the schema.

Implementations MAY also want to validate that the value provided for `usageReservation` is logically consistent with the hierarchical model: `TDM` includes `AITraining` and `genAITraining`, and `AITraining` includes `genAITraining`.

The following schema suffices to validate conformance to this core data model.

{% code overflow="wrap" %}
```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://docs.tdmai.org/schema/usage-reservation-v1.json",
  "title": "Usage Reservation Declaration",
  "type": "object",
  "required": ["version", "iscc"],
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
    "usageReservation": {
      "type": "string",
      "description": "The declared usage restriction level.",
      "enum": ["TDM", "AITraining", "genAITraining"]
    },
    "intent": {
      "type": "string",
      "description": "Optional declaration purpose.",
      "enum": ["activate", "update", "supercede"],
      "default": "activate"
    },
    "reservationSummary": {
      "type": "string",
      "description": "Optional human-readable summary of the reservation."
    },
    "reservationPolicy": {
      "type": "string",
      "description": "Optional human-readable description of the targeted compliance regime."
    }
  },
  "additionalProperties": false
}

```
{% endcode %}
