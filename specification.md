---
description: THIS IS A TEMPORARY DRAFT FOR DISCUSSION Last updated 2024-06-17
---

# Specification

## Opt-out Declaration

A machine-readable declaration by the rightsholder prohibiting use of content for training models and applications of generative AI.

{% code title="Opt-out Declaration" overflow="wrap" lineNumbers="true" fullWidth="false" %}
```json
{
  "iscc": "ISCC:KEC7VSV5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "TDMAI": false,
  "TDMAI_summary": "Content must not be used for AI training purposes.",
  "TDMAI_policy": "Automated analysis of the work to extract information from it, especially about patterns, trends, and correlations for the purpose of training models and applications of generative AI, is reserved. Text and Data Mining (TDM) is permitted for general purpose AI systems that do not generate synthetic audio, image, video, or text content and for scientific research purposes or for temporary acts of reproduction as provided for in Article 5(1) of Directive 2001/29/EC."
}
```
{% endcode %}

{% embed url="https://liccium.app/api/v1/cid/optout" %}
Expression of an opt-out declaration
{% endembed %}

## Opt-out Revocation

A machine-readable statement indicating that the rightsholder has revoked a previously issued opt-out declaration for TDM for AI, thus changed its position on the previous restriction.

{% code title="Opt-out Revocation" overflow="wrap" lineNumbers="true" %}
```json
{
  "iscc": "ISCC:KEC7VSV5QH7FTV7N5YVD5UMF4TUKFFGDGCOI4UDFKE4FNPW6C3L7J2Y",
  "TDMAI": true,
  "TDMAI_summary": "Content may be used for AI training purposes.",
  "TDMAI_policy": "A reservation against the automated analysis of the work in order to extract information from it, in particular about patterns, trends and correlations for the purpose of training models and applications of generative AI, is not declared."
}
```
{% endcode %}

{% embed url="https://liccium.app/api/v1/cid/optin" %}
Expression of an opt-out revocation
{% endembed %}

## **ISCC Declarations**

Creators and rightsholders can generate ISCC codes from their content. It is proposed that the codes be publicly declared in open and verifiable content registers.

With this declaration, they can persistently and inextricably bind product information, rights and licenses, provenance and other metadata or claims to the unique identifier of the media asset – and ‘persistently’ means: the data cannot be removed!&#x20;

But how does this work? Instead of embedding information, watermarks and steganographic data in the file itself, the selected metadata is externalized, i.e. hashed, published and bound as a sidecar file to an ISCC code of the file derived from the content.

Once declared, federated and verifiable content registries can serve as platforms to discover ISCC codes and resolve associated declaration metadata. Through these registries, creators and rightsholders can publicly disclose their intellectual property rights and content metadata, ensuring that this information is accessible and verifiable.

## **Creator Credentials**

Since anyone can make a public declaration, it is important to ensure proper authentication of the source of each declaration. To further increase their trustworthiness, it is suggested that declaration metadata will include publicly accessible and verifiable creator credentials, which are based on the W3C standards for Verifiable Credentials, supported by advanced and qualified certificates that properly identify creators and rightsholders. Creator credentials serve as a means for attribution and authentication of creators and rightsholders based on social or institutional authentication, thereby trust in claims and attribution.

## **Timestamp**

Every declaration to a content registry will contain a verifiable timestamp to provide clear information about when the claim was published.
