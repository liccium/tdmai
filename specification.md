---
description: DRAFT 2024-02-28
---

# Specification

## Opt-out

A machine-readable declaration by the rightsholder prohibiting use of content for AI training.

{% code title="TDM·AI Opt-out" overflow="wrap" lineNumbers="true" fullWidth="true" %}
```json
{
  "TDMAI": false,
  "TDMAI_summary": "Content must not be used for AI training purposes.",
  "TDMAI_policy": "Automated analysis of the work to extract information from it, especially about patterns, trends and correlations, is reserved - Text and Data Mining for other than scientific research purposes or for temporary acts of reproduction provided for in Article 5(1) of Directive 2001/29/EC is not permitted."
}
```
{% endcode %}

## Permission

A machine-readable declaration indicating the rightsholder's consent for TDM for AI, or their change of stance from a previous restriction.

{% code title="TDM·AI Permission" overflow="wrap" lineNumbers="true" %}
```json
{
  "TDMAI": true,
  "TDMAI_summary": "Content may be used for AI training purposes.",
  "TDMAI_policy": "A reservation against the automated analysis of the work in order to extract information from it, in particular about patterns, trends and correlations, is not declared - Text and Data Mining is also permitted for other than scientific research purposes or for temporary acts of reproduction provided for in Article 5(1) of Directive 2001/29/EC."
}
```
{% endcode %}

## **ISCC Declarations**

Creators and rightsholders can generate ISCC codes from their content. It is suggested to publicly declare the codes on open and verifiable content registries.&#x20;

With this declaration, they can persistently and inextricably bind product information, rights and licenses, provenance and other metadata or claims to the unique identifier of the media asset – and ‘persistently’ means: the data cannot be removed!&#x20;

But how does this work? Instead of embedding information, watermarks and steganographic data in the file itself, the selected metadata is externalized, i.e. hashed, published and bound as a sidecar file to an ISCC code of the file derived from the content.

Once declared, federated, verifiable content registries can serve as platforms to discover ISCC codes and resolve associated declaration metadata. Through these registries, creators and rightsholders can publicly disclose their intellectual property rights and content metadata, ensuring that this information is accessible and verifiable.

## **Creator Credentials**

Since anyone can make a public declaration, it is important to ensure proper authentication of the source of each declaration. To further increase their trustworthiness, it is suggested that declaration metadata will include publicly accessible and verifiable creator credentials, which are based on the W3C standards for Verifiable Credentials, supported by advanced and qualified certificates that properly identify creators and rightsholders. Creator credentials serve as a means for attribution and authentication of creators and rightsholders based on social or institutional authentication, thereby trust in claims and attribution.

## **Timestamp**

Every declaration to a content registry will contain a verifiable timestamp to provide clear information about when the claim was published.
