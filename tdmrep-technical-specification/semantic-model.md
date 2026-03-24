---
description: '2025-04-11'
---

# Semantic Model

Liccium declarations are designed to be both machine-readable and semantically interoperable. Each declaration references a versioned JSON Schema for structural validation, a JSON-LD context for semantic interpretation, and is grounded in a formal OWL ontology. Together these three artefacts define how TDMrep declarations can be understood, validated, and processed consistently across systems.

### Schema

The Liccium JSON Schema provides the formal structure for validating declaration payloads. It defines required and optional fields, permitted value ranges, and the overall structure of a declaration including its plugin metadata.

```
https://w3id.org/liccium/schema/0.3.0.json
```

Every declaration includes a `$schema` reference to this URL. Implementations should validate declarations against it before processing or honouring them.

Within the schema, TDMrep preferences are expressed under `liccium_plugins.tdmrep`:

```json
{
  "tdm-reservation": {
    "type": "integer",
    "enum": [0, 1],
    "description": "1 = TDM rights reserved; 0 = TDM rights not reserved."
  },
  "tdm-policy": {
    "type": "string",
    "format": "uri",
    "description": "URL linking to a TDM policy document."
  }
}
```

### JSON-LD Context

The Liccium JSON-LD context maps declaration fields to their formal semantic identifiers, allowing linked data agents to interpret declarations consistently.

```
https://w3id.org/liccium/context/0.3.0.json
```

Each declaration includes a `@context` reference to this URL. The context maps TDMrep terms to their canonical identifiers under the W3C TDMrep namespace (`https://www.w3.org/ns/tdmrep#`) and the Liccium ontology namespace (`https://w3id.org/liccium/ont/`).

### Ontology

The Liccium OWL ontology formally defines the properties used in declarations as RDF data properties, including their domain, range, and human-readable descriptions.

```
https://w3id.org/liccium/context/0.3.0.json
```

The two TDMrep properties are defined as follows.

`tdm-reservation` is a datatype property with range `xsd:integer`, accepting values `0` or `1`. A value of `1` means TDM rights are reserved and automated processing including AI training is not permitted without authorisation from the rightsholder. A value of `0` means TDM rights are not reserved and use is permitted without contacting the rightsholder.

`tdm-policy` is a datatype property with range `xsd:anyURI`. It links to a policy document – human- or machine-readable – specifying the conditions under which content may be used for TDM purposes. It is only meaningful when `tdm-reservation` is set to `1`.

Both properties have domain `liccium:Declaration`, meaning they are properties of a signed declaration bound to an ISCC fingerprint – not properties of the content file itself.
