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
* Future-proof – allowing for optional metadata and extensibility

Implementations are expected to validate opt-out declarations against this schema before processing or honouring them. In specific use-cases, they MAY additionally want to ignore any additional properties (or discard any records containing additional properties) for security reasons, i.e. by adding `“additionalProperties”:false` at the end of the schema. In other use cases, they MAY also want to validate that the values provided are logically consistent with the hierarchy between TDM rights, training rights, and generative training rights mentioned above. The following suffices to validate conformance to this core data model, however.

{% code overflow="wrap" %}
```json
{
    "$schema": "https://json-schema.org/draft/2020-12/schema",
    "title": "TDMAI Opt-Out Declaration",
    "type": "object",
    "required": ["iscc", "usagePermission", "permissionSummary", "permissionPolicy"],
    "properties": {
      "iscc": {
        "type": "string",
        "description": "ISCC identifier for the declared asset. See https://iscc.codes for specification."
      },
      "usagePermission": {
        "type": "object",
        "required": ["tdm", "aiTraining", "generativeAI"],
        "properties": {
          "tdm": {
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
      "permissionSummary": {
        "type": "string",
        "description": "Plain-language summary of the permissions declaration."
      },
      "permissionPolicy": {
        "type": "string",
        "description": "Detailed policy statement, possibly including legal references, explaining the context in which the permissions are declared."
      },
      "intent": {
        "type": "string",
        "enum": ["activate", "update", "supersede"],
        "description": "Informational hint about whether this is an initial declaration (activate), a re-declaration by a repeat registrant (update), or an automatic/policy-triggered declaration (supersede)."
      },
      "version": {
        "type": "string",
        "description": "Optional semantic versioning string (e.g. '1.0.1')."
      }
    }
  }
```
{% endcode %}
