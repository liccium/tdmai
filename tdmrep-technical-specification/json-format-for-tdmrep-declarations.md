---
description: '2025-11-04'
---

# JSON Format for TDMrep Declarations

This section defines the JSON format used to express TDMrep declarations under the TDM·AI Protocol. TDMrep uses a simple two-field structure bound to an ISCC fingerprint, making it straightforward to implement while remaining fully machine-readable.

## Declaration Format

Each declaration consists of a flat key-value structure:

```json
{
  "iscc": "ISCC:EXAMPLE5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "tdm-reservation": 1,
  "tdm-policy": "https://example.com/tdm-policy"
}
```

### **Keys**

* `tdm-reservation` – indicates whether TDM rights are reserved. Required.
* `tdm-policy` – a URI pointing to a policy document specifying the conditions under which content may be used for TDM. Optional; only meaningful when `tdm-reservation` is `1`.

### **Values**

* `1` – TDM rights reserved; automated processing including AI training is not permitted without authorisation
* `0` – TDM rights not reserved; use is permitted without contacting the rightsholder

## Required and Optional Fields

Each declaration **MUST** include:

* `iscc` – a content-derived identifier based on ISO 24138:2024, representing the specific asset to which the declaration applies.
* `tdm-reservation` – the reservation flag (`1` or `0`).

Each declaration **MAY** include:

* `tdm-policy` – a URI to a human- or machine-readable policy document.

## Example Use Cases

### Example 1: Full TDM Reservation

All TDM rights reserved. No automated processing or AI training is permitted without authorisation.

```json
{
  "iscc": "ISCC:EXAMPLE5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "tdm-reservation": 1
}
```

#### Example 2: TDM Reservation with Policy Reference

Rights are reserved and a policy document specifies the conditions under which licensing may be available.

```json
{
  "iscc": "ISCC:EXAMPLE5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "tdm-reservation": 1,
  "tdm-policy": "https://example.com/tdm-policy"
}
```

#### Example 3: No Reservation

TDM use is explicitly permitted without contacting the rightsholder.

```json
{
  "iscc": "ISCC:EXAMPLE5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "tdm-reservation": 0
}
```
