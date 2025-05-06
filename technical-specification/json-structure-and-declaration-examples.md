---
description: '2025-05-04'
---

# JSON Structure and Declaration Examples

​​This section defines the JSON format used to express opt-out declarations under the TDM·AI Protocol. The goal is to enable machine-readable communication of rights permissions or reservations concerning the use of digital content for:

* Text and Data Mining (TDM)
* AI Training
* Generative AI Training

The specification ensures consistency across systems and allows rightsholders to clearly signal whether their content may or may not be used in the context of automated analysis and model training. Each declaration can be independently interpreted, while respecting the vocabulary's hierarchical structure.

### Opt-Out Declaration Format

Usage reservations use a hierarchical list structure under the top-level key `usageReservation`. Each item in the list declares a restricted use case. The vocabulary is hierarchical:

* `TDM` also restricts `AiTraining` and `genAiTraining`&#x20;
* `AiTraining` also restricts `genAiTraining`
* `genAiTraining` restricts only generative model training

The `usageReservation` object contains a list of string values representing restricted use cases:

* `tdm`: general text and data mining
* `aiTraining`: AI training&#x20;
* `genAiTraining`: generative AI training

The `usagePermission` object contains a list of string values representing allowed use cases:

* `tdm`: general text and data mining
* `aiTraining`: AI training&#x20;
* `genAiTraining`: generative AI training

Each declaration **MUST** include, at the top level:

* `iscc`: a unique content identifier using the ISCC standard.

Each declaration **MAY** include, at the top level:

* `intent`: an optional, informational expression of the intention of the declaration, i.e. &#x20;
  * `activate` for an initial registration,
  * `update` for a revocation or other update by the original registrant,&#x20;
  * `supercede` for an automatic update triggered by dependencies or upstream changes in rights.&#x20;
  * If absent, the implicit default value is `activate`.
* `reservationSummary`: an informational, human-readable summary of what is reserved applied at time of declaration; can be auto-generated from the contents if omitted.
* `reservationPolicy`: an informational, human-readable summary of what compliance regimes are targeted (e.g., to EU directives or the AI Act).
* `permissionSummary`: an informational, human-readable summary of what is permitted applied at time of declaration; can be auto-generated from the contents if omitted.
* `permissionPolicy`: an informational, human-readable summary of what compliance regimes are targeted (e.g., to EU directives or the AI Act).

## Example Use Cases for Opt-Out Declarations

### **Example 1: Full TDM Reservation**&#x20;

This declaration reserves **all uses** — TDM, AI training, and generative AI training — by specifying the highest-level restriction.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "usageReservation": "TDM",
  "reservationSummary": "Content must not be used for text and data mining, AI training, or generative AI training.",
  "reservationPolicy": "The use of this work for text and data mining (TDM) is not permitted. This includes any automated analytical technique aimed at analyzing text or data in digital form to generate information, such as patterns, trends, or correlations. As a result, the work may also not be used for training general-purpose AI models or other systems, including those designed to generate synthetic content. This reservation is made in accordance with Article 4(3) of Directive 2019/790 (CDSM Directive)."
}
```
{% endcode %}

### **Example 2a**: AI Training Reserved&#x20;

This declaration **reserves AI training**, which also implicitly restricts generative AI training, while still allowing general text and data mining (e.g., for search, indexing, or non-AI analytical purposes).

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "usageReservation": "AiTraining",
  "reservationSummary": "Content may be used for text and data mining but must not be used for AI training or generative AI training.",
"reservationPolicy": "The use of this work to train AI models is not permitted. This includes training general-purpose AI systems or other models capable of performing a wide range of tasks such as labeling, classification, pattern recognition, decision-making, or semantic content understanding. Use of the work for training generative AI models is also prohibited. However, text and data mining (TDM) is permitted in accordance with Article 4 of Directive 2019/790 (CDSM Directive), provided it does not serve the purpose of model training."
}
```
{% endcode %}

### **Example 2b**: AI Training Reserved – TDM Permission

Depending on the use case, the legislation and its applicable AI policy, declaring parties may want to explicitly add the usage permission ("`usagePermission` "),  the permission summary `permissionSummary` and the permission policy `permissionPolicy` to the declaration:&#x20;

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "usagePermission": "TDM",
  "usageReservation": "AiTraining",
  "reservationSummary": "Content may be used for text and data mining but must not be used for AI training or generative AI training.",
"reservationPolicy": "The use of this work to train AI models is not permitted. This includes training general-purpose AI systems or other models capable of performing a wide range of tasks such as labeling, classification, pattern recognition, decision-making, or semantic content understanding. Use of the work for training generative AI models is also prohibited. However, text and data mining (TDM) is permitted in accordance with Article 4 of Directive 2019/790 (CDSM Directive), provided it does not serve the purpose of model training."
}
```
{% endcode %}

### Example 3a: Generative AI Training Reserved

This declaration reserves **generative AI training**. It allows all other uses, including AI training for non-generative purposes and general text and data mining.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE7UXMJCB6AVW4UHYMGYF6NNDPZKHQWQK5ZYPQJNPZAKGMYZQ",
  "usageReservation": "genAiTraining",
  "reservationSummary": "Content may be used for TDM and for training non-generative AI models, but not for generative AI training.",
  "reservationPolicy": "The use of this work to train AI models that are either (a) general-purpose AI systems with the capacity to generate synthetic content such as text, images, audio, or video, or (b) other types of AI systems whose primary purpose is the generation of such content, is not permitted. Text and Data Mining (TDM) is allowed for non-generative purposes, including training AI systems that do not produce synthetic outputs, in accordance with Article 4 of Directive 2019/790 (CDSM Directive), and for scientific research or temporary reproduction under Article 5(1) of Directive 2001/29/EC."
}
```
{% endcode %}

### **Example 3b**: Generative AI Training Reserved – TDM and AI Training Permission

Depending on the use case, the legislation and its applicable AI policy, declaring parties may want to explicitly add the usage permission ("`usagePermission` "), the permission summary `permissionSummary` and the permission policy `permissionPolicy` to the declaration. Since the model is hierarchical,  the usage permission includes AI training for non-generative purposes.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "usagePermission": "TDM",
  "usageReservation": "genAiTraining",
  "reservationSummary": "Content may be used for text and data mining but must not be used for AI training or generative AI training.",
"reservationPolicy": "The use of this work to train AI models is not permitted. This includes training general-purpose AI systems or other models capable of performing a wide range of tasks such as labeling, classification, pattern recognition, decision-making, or semantic content understanding. Use of the work for training generative AI models is also prohibited. However, text and data mining (TDM) is permitted in accordance with Article 4 of Directive 2019/790 (CDSM Directive), provided it does not serve the purpose of model training."
}
```
{% endcode %}
