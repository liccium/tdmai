---
description: DRAFT for Discussion 2025-03-20
---

# JSON Structure and Declaration Examples

This section defines the JSON format used to express opt-out declarations under the TDM·AI Protocol. The goal is to enable machine-readable communication of rights reservations concerning the use of digital content for:

* Text and Data Mining (TDM)
* AI Training
* Generative AI Training

The specification ensures consistency across systems and allows rightsholders to clearly signal how their content may or may not be used in the context of automated analysis and model training. Each declaration can be independently interpreted, while respecting the vocabulary's hierarchical structure.

### Opt-Out Declaration Format

Opt-out declarations use a flat key structure under a top-level object. Each use case is declared explicitly using boolean values:

* `true` means the activity is allowed (no opt-out).
* `false` means the activity is not allowed (opt-out).
* The `tdmOptOut` object contains three boolean keys:
  * `TDM`: general text and data mining
  * `aiTraining`: AI training (non-generative or general-purpose)
  * `generativeAI`: generative AI training

Each declaration must also include:

* `iscc`: a unique content identifier using the[ ISCC](https://iscc.io) standard.
* `TDMAI_summary`: a plain-language summary of what is permitted or reserved.
* `TDMAI_policy`: a more detailed statement of the policy, optionally including legal references (e.g., to EU directives or the AI Act).

## Example use cases

### **Example 1: Full TDM Opt-Out (TDM, AI Training, and Generative AI Training)**

This declaration opts out of all uses—TDM, AI training, and generative AI training.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:KEC7VSV5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "tdmOptOut": {
    "TDM": false,
    "aiTraining": false,
    "generativeAI": false
  },
  "TDMAI_summary": "Content must not be used for text and data mining, AI training, or generative AI training.",
  "TDMAI_policy": "The use of this work for text and data mining (TDM) is not permitted. This includes any automated analytical technique aimed at analyzing text or data in digital form to generate information, such as patterns, trends, or correlations. As a result, the work may also not be used for training general-purpose AI models or other systems, including those designed to generate synthetic content. This reservation is made in accordance with Article 4(3) of Directive 2019/790 (CDSM Directive)."
}
```
{% endcode %}

### **Example 2: Opt-Out of AI Training and Generative AI Training, but Allowing TDM**

This declaration **opts out** of AI and generative AI training but **allows** text and data mining.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:KEC7VSV5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "tdmOptOut": {
    "TDM": true,
    "aiTraining": false,
    "generativeAI": false
  },
  "TDMAI_summary": "Content may be used for text and data mining but must not be used for AI training or generative AI training.",
  "TDMAI_policy": "The use of this work to train AI models is not permitted. This includes training general-purpose AI systems or other models capable of performing a wide range of tasks such as labeling, classification, pattern recognition, decision-making, or semantic content understanding. Use of the work for training generative AI models is also prohibited. However, text and data mining (TDM) is permitted in accordance with Article 4 of Directive 2019/790 (CDSM Directive), provided it does not serve the purpose of model training."
}

```
{% endcode %}

### **Example 3: Opt-Out of Generative AI Training Only**

This declaration **opts out** only from generative AI training, while **allowing** TDM and general AI training.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLECODE1234567890",
  "tdmOptOut": {
    "TDM": true,
    "aiTraining": true,
    "generativeAI": false
  },
  "TDMAI_summary": "Content may be used for text and data mining and AI training but must not be used for generative AI training.",
  "TDMAI_policy": "The use of this work to train AI models that are either (a) general-purpose AI systems with the capacity to generate synthetic content such as text, images, audio, or video, or (b) other types of AI systems whose primary purpose is the generation of such content, is not permitted. Text and Data Mining (TDM) is allowed for non-generative purposes, including training AI systems that do not produce synthetic outputs, in accordance with Article 4 of Directive 2019/790 (CDSM Directive), and for scientific research or temporary reproduction under Article 5(1) of Directive 2001/29/EC."
}
```
{% endcode %}
