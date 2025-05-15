---
description: '2025-05-04'
---

# JSON Structure and Declaration Examples

This section defines the JSON format used to express opt-out and permission declarations under the TDM·AI Protocol. The goal is to support clear, machine-readable communication of rights regarding the use of digital content for:

* Text and Data Mining (TDM)
* AI Training
* Generative AI Training

The specification ensures consistency across systems and implementations and allows rightsholders to precisely declare whether their content may or may not be used for specific purposes. Each usage type is declared explicitly, with no assumptions about hierarchical inclusion.

Instead of relying on nested or implicit logic, this structure:

* Treats each key independently.
* Avoids ambiguous inheritance.
* Enhances interoperability between frameworks with different legal assumptions.

Each declaration uses one of two values:

* `"usagePermission"` — use is explicitly allowed.
* `"usageReservation"` — use is explicitly reserved (i.e., opted out).

This design provides the best balance between legal clarity, technical robustness, and cross-jurisdictional compatibility.

## Declaration Format

The declaration format uses three defined keys representing distinct types of use:

* `TDM`: General text and data mining
* `AiTraining`: AI training
* `genAiTraining`: Generative AI training

Declarations consist of a flat key-value structure where each usage type is explicitly associated with a value:

* `"usagePermission"` — use is explicitly allowed.
* `"usageReservation"` — use is explicitly reserved (i.e., opted out).

This format removes hierarchical assumptions and supports compatibility across systems that process rights declarations.

#### Required and Optional Fields

Each declaration **MUST** include:

* `iscc`: A unique content identifier using the [ISCC standard](https://iscc.codes/).

Each declaration **MAY** include, at the top level:

* `intent`: an optional, informational expression of the intention of the declaration, i.e. &#x20;
  * `activate` for an initial registration,
  * `update` for a revocation or other update by the original registrant,&#x20;
  * `supercede` for an automatic update triggered by dependencies or upstream changes in rights.&#x20;
  * If absent, the implicit default value is `activate`.
* `summary`: A human-readable summary of the declared rights (e.g., reservation or permission).
* `policy`: A human-readable note on compliance targets (e.g. AI Act, EU directives, or national law).

## Example Use Cases for Opt-Out Declarations

### **Example 1: Full TDM Reservation**&#x20;

This declaration reserves all uses — general TDM, AI training, and generative AI training — by explicitly setting all three categories to `"usageReservation"`.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "TDM": "usageReservation",
  "AiTraining": "usageReservation",
  "genAiTraining": "usageReservation",
  "reservationSummary": "Content must not be used for text and data mining, AI training, or generative AI training.",
  "reservationPolicy": "The use of this work for text and data mining (TDM) is not permitted. This includes any automated analytical technique aimed at analyzing text or data in digital form to generate information, such as patterns, trends, or correlations. As a result, the work may also not be used for training general-purpose AI models or other systems, including those designed to generate synthetic content. This reservation is made in accordance with Article 4(3) of Directive 2019/790 (CDSM Directive)."
}
```
{% endcode %}

### **Example 2**: AI Training Reserved&#x20;

This declaration **reserves AI training**, which also implicitly restricts generative AI training, while still allowing general text and data mining (e.g., for search, indexing, or non-AI analytical purposes).

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "TDM": "usagePermission",
  "AiTraining": "usageReservation",
  "genAiTraining": "usageReservation",
  "reservationSummary": "Content may be used for text and data mining but must not be used for AI training or generative AI training.",
"reservationPolicy": "The use of this work to train AI models is not permitted. This includes training general-purpose AI systems or other models capable of performing a wide range of tasks such as labeling, classification, pattern recognition, decision-making, or semantic content understanding. Use of the work for training generative AI models is also prohibited. However, text and data mining (TDM) is permitted in accordance with Article 4 of Directive 2019/790 (CDSM Directive), provided it does not serve the purpose of model training."
}
```
{% endcode %}

### Example 3: Generative AI Training Reserved

This declaration reserves **generative AI training**. It allows all other uses, including AI training for non-generative purposes and general text and data mining.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE7UXMJCB6AVW4UHYMGYF6NNDPZKHQWQK5ZYPQJNPZAKGMYZQ",
  "TDM": "usagePermission",
  "AiTraining": "usagePermission",
  "genAiTraining": "usageReservation",
  "reservationSummary": "Content may be used for TDM and for training non-generative AI models, but not for generative AI training.",
  "reservationPolicy": "The use of this work to train AI models that are either (a) general-purpose AI systems with the capacity to generate synthetic content such as text, images, audio, or video, or (b) other types of AI systems whose primary purpose is the generation of such content, is not permitted. Text and Data Mining (TDM) is allowed for non-generative purposes, including training AI systems that do not produce synthetic outputs, in accordance with Article 4 of Directive 2019/790 (CDSM Directive), and for scientific research or temporary reproduction under Article 5(1) of Directive 2001/29/EC."
}
```
{% endcode %}
