---
description: '2025-11-04'
---

# Usage Preferences Vocabulary

This section defines the controlled vocabulary used to express AI preferences under the **TDM·AI Protocol**. The vocabulary enables machine-readable communication of preferences regarding the use of digital content for automated processing activities, including AI training and generative AI training.

{% hint style="info" %}
**Note on Alignment with IETF Drafts and Current Status**

This specification on the Usage Preferences Vocabulary for the TDM·AI Protocol currently aligns with version 02 of the draft‑ietf‑aipref‑vocab‑02 published by the Internet Engineering Task Force (IETF) as of July 21 2025. [datatracker.ietf.org+2datatracker.ietf.org+2](https://datatracker.ietf.org/doc/html/draft-ietf-aipref-vocab-02?utm_source=chatgpt.com)\
\
It is important to note that the IETF work on the “AI Preferences” vocabulary remains a **work in progress**. The draft is still under discussion, subject to change, and does not yet constitute a finalized standard. [datatracker.ietf.org+1](https://datatracker.ietf.org/doc/draft-ietf-aipref-vocab/02/?utm_source=chatgpt.com)\
\
We have chosen to use this particular draft version as a **reference point** to illustrate how a domain-based attachment mechanism (as proposed by the IETF) can be **translated** into a registry-based system — that is, how preference declarations can be persistently and verifiably associated with individual digital assets via a registry rather than relying solely on domain- or location-based signaling.\
\
As the IETF draft evolves, we expect to revisit and update our alignment accordingly. Until then, this documentation should be regarded as **preliminary guidance**, not a definitive implementation.
{% endhint %}

| Category Name                         | Key           | Description                                                       |
| ------------------------------------- | ------------- | ----------------------------------------------------------------- |
| Automated Processing (formerly `tdm`) | `all`         | Top-level category covering all automated analysis and processing |
| AI Training                           | `train-ai`    | General-purpose or task-specific training of AI models            |
| Generative AI Training                | `train-genai` | Training models to produce synthetic content                      |
| AI Use (Inference)                    | `ai-use`      | Using assets as inputs to operate trained AI models               |
| Search                                | `search`      | Using assets in search engines or discovery applications          |

Each category may be declared independently. However, restrictions follow a strict hierarchy: opting out of a higher-level category (e.g., `all`) implies restriction of all its subordinate categories (`train-ai`, `train-genai`, `ai-use`, and `search`).

## Vocabulary Definition <a href="#name-vocabulary-definition" id="name-vocabulary-definition"></a>

This section defines the categories of use in the vocabulary, quoted from the IETF , [https://www.ietf.org/archive/id/draft-ietf-aipref-vocab-02.html#section-4](https://www.ietf.org/archive/id/draft-ietf-aipref-vocab-02.html#section-4).

### 1. Automated Processing Category <a href="#name-automated-processing-catego" id="name-automated-processing-catego"></a>

"The act of using one or more assets in the context of automated processing aimed at analysing text and data in order to generate information which includes but is not limited to patterns, trends and correlations.

The use of assets for automated processing encompasses all the subsequent categories."

### 2. AI Training Category <a href="#name-ai-training-category" id="name-ai-training-category"></a>

"The act of training machine learning models or artificial intelligence (AI).

The use of assets for AI Training is a proper subset of Automated Processing usage"

### 3. Generative AI Training Category <a href="#name-generative-ai-training-cate" id="name-generative-ai-training-cate"></a>

"The act of training general purpose AI models that have the capacity to generate text, images or other forms of synthetic content, or the act of training more specialised AI models that have the purpose of generating text, images or other forms of synthetic content.

The use of assets for Generative AI Training is a proper subset of AI Training usage."

### 4. AI Use Category

"The act of using one or more assets as input to a trained AI/ML model as part of the operation of that model (as opposed to the training of the model).

The use of assets for AI Use is a proper subset of Automated Processing usage."

### 5. Search Category

"Using one or more assets in a search application that directs users to the location from which the assets were retrieved."

The purpose of defining a distinct Search category is to allow preferences to be expressed about search applications, independent of other categories of use. A distinct Search category allows for preferences specific to search applications, even if the use of AI is involved in their implementation.

The use of assets for Search is a proper subset of Automated Processing usage."
