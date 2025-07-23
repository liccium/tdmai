---
description: '2025-07-21'
---

# JSON Format for Usage Declarations

This section defines the JSON format used to express opt-out and permission declarations under the **TDM·AI Protocol**. The format enables machine-readable communication of rights regarding the use of digital content for:

* Automated Processing (`all`)
* AI Training (`train-ai`)
* Generative AI Training (`train-genai`)
* AI Use / Inference (`ai-use`)
* Search (`search`)

The structure follows the [IETF AI Preferences Vocabulary](https://www.ietf.org/archive/id/draft-ietf-aipref-vocab-02.html) and [Attachment Mechanisms](https://www.ietf.org/archive/id/draft-ietf-aipref-attach-02.html), using compact single-byte tokens defined in Section 3.3.4:

* `true` — explicitly allowed
* `false` — explicitly disallowed

## Declaration Format

Each declaration consists of a flat key-value structure where usage types are associated with a value:

```json
{
  "all": "false",
  "ai-use": "true",
  "search": "true"
}
```

In this example:

* Automated processing and AI-training and Generative AI Training are disallowed
* AI inference and search are permitted

**Keys**

* `all` – General automated processing (formerly TDM)
* `train-ai` – AI model training
* `train-genai` – Generative model training
* `ai-use` – Use of content as input to a deployed AI model (inference)
* `search` – Use in search applications

**Values**

* `true` — allowed
* `false` — disallowed

## Inheritance and Overrides

The keys `all`, `train-ai`, and `train-genai` are hierarchically nested:

* `train-ai` inherits from `all`
* `train-genai` inherits from `train-ai`

Subordinate values inherit from parent values unless explicitly overridden. \
Other keys (`ai-use`, `search`) are independent and must be declared directly.

_Example:_

```json
{
  "all": "true",
  "train-genai": "false"
}
```

→ All processing is allowed except generative AI training, which is explicitly disallowed.

## Required and Optional Fields

Each declaration **MUST** include:

* `iscc`: A unique content identifier based on the ISCC standard, representing the specific asset to which the usage preferences apply.

Each declaration **MAY** include the following optional top-level fields:

* `intent`: A short code indicating the purpose of the declaration. Valid values are:
  * `activate` — for initial registration (default if omitted)
  * `update` — for a revision or change by the original declaring party
  * `supercede` — for an automatic update triggered by dependency or policy changes
* `summary`: A brief human-readable explanation of the declared usage rights, such as the scope of opt-out or permission. (optional)
* `policy`: A human-readable reference to relevant legal or regulatory frameworks that inform the declaration, e.g., EU AI Act, CDSM Directive, national copyright laws. (optional)

These optional fields provide additional context but do not affect the machine-readable enforcement of the core usage preferences.

## Example Use Cases for Opt-Out Declarations

### Example 1: Full Reservation of Automated Processing (TDM)

This declaration opts out of all usage categories—automated processing, AI training, and generative AI training – by setting the top-level category (`all`) to `n`. No overrides are needed for subordinate categories.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "all": "false",
  "summary": "Content must not be used for text and data mining, AI training, or generative AI training.",
  "policy": "The use of this work for text and data mining (TDM) is not permitted. This includes any automated analytical technique aimed at analyzing text or data in digital form to generate information, such as patterns, trends, or correlations. As a result, the work may also not be used for training general-purpose AI models or other systems, including those designed to generate synthetic content. This reservation is made in accordance with Article 4(3) of Directive 2019/790 (CDSM Directive)."
}
```
{% endcode %}

This compact structure uses the `all` category to disallow all subordinate types of use (`train-ai`, `train-genai`) through hierarchical inheritance.

### Example 2: AI Training Reserved

This declaration permits general automated processing (e.g. indexing, or non-AI analytical uses) while explicitly disallowing AI training. Since `train-genai` is a subset of `train-ai`, it is also implicitly disallowed and does not need to be stated separately.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "all": "true",
  "train-ai": "false",
  "summary": "Content may be used for text and data mining but must not be used for AI training or generative AI training.",
"policy": "The use of this work to train AI models is not permitted. This includes training general-purpose AI systems or other models capable of performing a wide range of tasks such as labeling, classification, pattern recognition, decision-making, or semantic content understanding. Use of the work for training generative AI models is also prohibited. However, text and data mining (TDM) is permitted in accordance with Article 4 of Directive 2019/790 (CDSM Directive), provided it does not serve the purpose of model training."
}
```
{% endcode %}

### Example 3: Generative AI Training Reserved

This declaration allows general automated processing and AI training for non-generative purposes, while explicitly disallowing generative AI training by overriding the inherited permission.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE7UXMJCB6AVW4UHYMGYF6NNDPZKHQWQK5ZYPQJNPZAKGMYZQ",
  "all": "true",
  "train-genai": "false",
  "summary": "Content may be used for TDM and for training non-generative AI models, but not for generative AI training.",
  "policy": "The use of this work to train AI models that are either (a) general-purpose AI systems with the capacity to generate synthetic content such as text, images, audio, or video, or (b) other types of AI systems whose primary purpose is the generation of such content, is not permitted. Text and Data Mining (TDM) is allowed for non-generative purposes, including training AI systems that do not produce synthetic outputs, in accordance with Article 4 of Directive 2019/790 (CDSM Directive), and for scientific research or temporary reproduction under Article 5(1) of Directive 2001/29/EC."
}
```
{% endcode %}

### Example 4: Full Reservation Including Inference and Search

This declaration reserves all forms of automated processing, AI training, generative training, **and** downstream usage for inference and search.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE99XXF42U8AV4EAVFJ6CE2ZH6MPAKMVDKAP5WZRE7YZU2U4FC",
  "all": "false",
  "ai-use": "false",
  "search": "false",
  "summary": "Content must not be used for any form of automated processing, AI training, inference, or search."
}
```
{% endcode %}

In this example, `train-ai` and `train-genai` are implicitly restricted by `all: "false"`, and `ai-use` and `search` are explicitly disallowed.

### Example 5: Inference and Search Permitted, Generative Training Reserved

This declaration permits general processing, non-generative AI training, inference, and search—but disallows generative AI training.

{% code overflow="wrap" %}
```json
{
  "iscc": "ISCC:EXAMPLE1YVP4YBZPXVFXMBTBKXGPV5VF6A7JHYYK5R45MEJJSZZDRQU",
  "all": "true",
  "train-genai": "false",
  "ai-use": "true",
  "search": "true",
  "summary": "Content may be used for search, inference, and training of non-generative AI systems, but not for generative AI training."
}
```
{% endcode %}

In this case:

* `all: "true"` permits all uses by default.
* `train-genai: "false"` overrides the default for generative training.
* `ai-use` and `search` are explicitly permitted to ensure downstream use is clearly allowed.
