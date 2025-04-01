---
description: '2025-03-26'
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Opt-out Vocabulary

​​This section defines the controlled vocabulary used to express rights reservations (in the following termed: “opt-out declarations”) under the TDM·AI Protocol. The vocabulary enables machine-readable communication of rights reservations regarding the use of digital content for text and data mining (TDM), AI training, and generative AI training.

The vocabulary is based on the proposal by the Open Future Foundation: "A Vocabulary for Opting Out of AI Training and Other Forms of TDM" (07 March 2025) Available at: [https://openfuture.eu/publication/a-vocabulary-for-opting-out-of-ai-training-and-other-forms-of-tdm](https://openfuture.eu/publication/a-vocabulary-for-opting-out-of-ai-training-and-other-forms-of-tdm)

The vocabulary is structured hierarchically to reflect legal and technical relationships between different types of uses. Each category can be declared independently, but opt-outs at a higher level also cause restrictions on subordinate categories, as described below.

## Disclaimer on Legal Applicability

This vocabulary is designed to provide a standardised, machine-readable means for rightsholders to communicate reservations of rights concerning the use of protected content for text and data mining (TDM), artificial intelligence (AI) training, and generative AI training.

This vocabulary operates in the context of ongoing legal debate regarding the scope and applicability of statutory TDM exceptions – particularly whether such exceptions, as provided for in EU and national copyright laws, extend to the training of generative AI systems. Current academic and legal discourse, including the work of Dornis and Stober (2024), indicates divergent interpretations and unresolved questions in this area (Dornis, T.W. & Stober, S. (2024). Urheberrecht und Training generativer KI-Modelle – Technologische und juristische Grundlagen, Recht und Digitalisierung, Nomos Verlag.[ Open Access version](https://www.nomos-elibrary.de/10.5771/9783748949558/urheberrecht-und-training-generativer-ki-modelle?page=1); also available at SSRN:[ https://ssrn.com/abstract=4946214](https://ssrn.com/abstract=4946214)).

The inclusion of terms and categories in this vocabulary does not constitute a legal determination of whether any given use is permitted or prohibited under applicable law. Rather, it reflects the intention of rightsholders to reserve rights to the fullest extent permitted by law and to provide clear signals to users and AI developers in light of legal uncertainty.

Implementers and users of this vocabulary are advised to seek legal counsel regarding the specific application of copyright exceptions and limitations in their jurisdiction. The use of this vocabulary does not substitute for legal advice nor does it imply endorsement of any particular legal interpretation.

### 1. TDM (Text and Data Mining)&#x20;

**Definition**:&#x20;

The act of using assets in the context of any automated analytical technique aimed at analysing text and data in digital form in order to generate information, including but not limited to patterns, trends, and correlations.

**Implications**:&#x20;

Opting out of TDM automatically includes opting out of AI training and generative AI training.

### 2. AI Training&#x20;

**Definition**:&#x20;

The act of training AI models.

{% hint style="info" %}
AI models can be training general-purpose AI models or other types of AI models capable of performing a wide range of tasks, including labeling, classifying, recognizing patterns, making decisions, and semantically understanding content.
{% endhint %}

**Implications**:&#x20;

Opting out of AI training automatically includes opting out of generative AI training but does not opt out of TDM as a whole.

### 3. TDM for generative AI Training Purposes&#x20;

**Definition**:&#x20;

The act of training general-purpose AI models, improving their capacity to generate text, images, or other forms of synthetic content, or training other types of AI models that have the purpose of generating text, images, or other forms of synthetic content.

**Implications**:&#x20;

Opting out of generative AI training does not automatically include opting out of AI training or TDM unless explicitly stated.
