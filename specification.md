# Specification

## Vocabulary

The following specification is a draft. It will be most likely enhanced by using a slightly more enhanced vocabulary that will distinguish between the following options:&#x20;

### 1) Opt-Out of TDM&#x20;

Opting out of all TDM activities (except for for the purposes of scientific research)

### 2) Opt-out of TDM for AI Training Purposes&#x20;

Opting out of TDM in the context of applications or use cases where AI technologies are applied

### 3) Opt-out of TDM for generative AI Training Purposes&#x20;

Opting out of TDM in the context of models and applications of generative AI or use within applications that include generative AI (Initial focus of TDM·AI)

## Opt-out Declaration

Example of a machine-readable declaration by the rightsholder prohibiting use of content for training models and applications of generative AI.

{% code title="Opt-out Declaration" overflow="wrap" lineNumbers="true" fullWidth="false" %}
```json
{
  "iscc": "ISCC:KEC7VSV5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "TDMAI": false,
  "TDMAI_summary": "Content must not be used for training generative AI.",
  "TDMAI_policy": "Automated analysis of the work to extract information from it, especially about patterns, trends, and correlations for the purpose of training models and applications of generative AI, is reserved. Text and Data Mining (TDM) is permitted for general purpose AI systems that do not generate synthetic audio, image, video, or text content and for scientific research purposes or for temporary acts of reproduction as provided for in Article 5(1) of Directive 2001/29/EC."
}
```
{% endcode %}

{% embed url="https://liccium.app/api/v1/cid/optout" %}
Expression of an opt-out declaration
{% endembed %}

When we speak of a "machine-readable opt-out", we mean an explicit reservation by the rightsholder that reproductions and extractions of lawfully accessible works and other protected subject matter are not permitted for the purposes of TDM for the purpose of training models and applications of generative AI. An opt-out is not possible for use for scientific research purposes.

## Opt-out Revocation

Example of a machine-readable statement indicating that the rightsholder has revoked a previously issued opt-out declaration for TDM for AI, thus changed its position on the previous restriction.

{% code title="Opt-out Revocation" overflow="wrap" lineNumbers="true" %}
```json
{
  "iscc": "ISCC:KEC7VSV5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "TDMAI": true,
  "TDMAI_summary": "Content may be used for training generative AI.",
  "TDMAI_policy": "A reservation against the automated analysis of the work in order to extract information from it, in particular about patterns, trends and correlations for the purpose of training models and applications of generative AI, is not declared."
}
```
{% endcode %}

{% embed url="https://liccium.app/api/v1/cid/optin" %}
Expression of an opt-out revocation
{% endembed %}

An “opt-out Revocation” indicates that the rightsholder has made a declaration that should be interpreted in a way that no opt-out applies (anymore). While one might argue that such a declaration is redundant because permission is the default assumption, there are scenarios where the rightsholder may have initially expressed a machine-readable reservation but subsequently changed their stance.
