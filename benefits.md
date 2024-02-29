---
description: DRAFT 2024-02-29
---

# Benefits

## Benefits of the ISCC

* **Decentralised Identifier**: The ISCC serves as a decentralised identifier for the specific digital media asset, allowing various parties, including users and machines, to generate codes only by having access to the file.
* **Accessible and Open-Source**: The [ISCC generator service](https://github.com/iscc/iscc-web) is an easy and accessible way to generate ISCC codes. It is open-sourced with a permissive licence, lightweight, dockerised, and effortlessly deployable.&#x20;
* **Versatility Across Media Types**: ISCC can be used with all media types (text, images, video, audio) and [supports a wide range of file formats](https://github.com/iscc/iscc-sdk/blob/872795b8fdcbb66a7c71dd9b5020589e2c8ad832/iscc\_sdk/mediatype.py#L204).
* **Resilience Amid Metadata Removal**: ISCC allows robust identification and matching of media assets even in cases where metadata was removed, a common occurrence when content is shared online or via social media.
* **Out-of-context consistency**: ISCC remains effective even when content is taken out of its original context and initial metadata or attribution becomes inaccessible due to content sharing on third-party domains outside the control of the rightsholder, potentially losing creator or rights information in robots.txt files or other metadata.
* **Robustness against content changes**: ISCC retains its reliability even if content is changed, modified or manipulated.

### Benefits of ISCC declarations

* **Inseparably binding rights and metadata**: ISCC declarations enable the secure and indissoluble binding of external metadata, rights, or other claims, along with verifiable credentials, to the content, offering substantial advantages to creators and rightsholders.
* **Machine-readable Declarations**: ISCC declarations, in conjunction with verifiable credentials, can provide relevant and sufficient information regarding rights, permissions, and restrictions in a machine-readable way.
* **Verifiable, timestamped data**: ISCC declarations are both timestamped and cryptographically verifiable, ensuring the integrity and temporal context of the associated information.

### Benefits of Creator Credentials

The Creator Credentials project will develop a user-centric digital identity management framework that is specifically designed to serve the unique needs of the cultural and creative industries.&#x20;

[https://docs.creatorcredentials.com/](https://docs.creatorcredentials.com/)

1. **Attribution and Verification**: Creator credentials are essential for the proper and verifiable attribution of rights, permissions, and restrictions, ensuring transparency and accountability.
2. **Resilience**: Using Creator Credentials in the context of ISCC declarations, even in cases of content alteration, manipulation, or removal of watermarks or metadata, creator credentials can still be derived from the content and its associated ISCC code.
3. **Public Accessibility**: Creator Credentials are publicly accessible, allowing for verification within the context of any public content declaration or claim.
4. **Immutable and Trustworthy**: These credentials are immutable and trustworthy, meaning they cannot be altered without detection or notice.
5. **Timestamped Integrity**: In the context of ISCC declarations, Creator Credentials are timestamped to ensure cryptographic verifiability and transparency and to provide information about who made a declaration and when it was made, both for humans and machines.
6. **Self-Sovereign Control**: Creators and rightsholders have primary ownership and control over their credentials. They can choose where to host, when to use, and how to share them, including controlling access levels and revoking access if needed.
7. **Portability**: Creator Credentials are portable, allowing holders to transfer them between different systems and platforms without loss of information or functionality. They can also be used with various applications or services as required.
8. **Interoperability**: Creator Credentials are interoperable, meaning they can be recognised and accepted by different systems, even if they use different technologies or are operated by different organisations. Third-party applications can independently verify these credentials.
9. **Time-Limited**: Creator Credentials can be restricted in duration, supporting the ability to set expiration dates for verifiable credentials. This feature is valuable for credentials like professional licences or certifications that have defined expiry dates.
10. **Revocable**: In cases of expiration or other reasons, Creator Credentials can be revoked or cancelled. This maintains the integrity of the credential system and ensures that only accurate and valid information is shared. Revocation can be initiated by the issuer or the individual holding the credential and can be enforced by systems that recognize and accept the credential.



{% hint style="info" %}
In 2023, the European Union funded a project called 'Creator Credentials' as one selected project of the NGI's Trustchain consortium under grant agreement Nr. 101093274.&#x20;

The Creator Credentials project will develop a user-centric digital identity management framework specifically designed for the cultural and creative communities. This includes a software application that can be used by media organisations to issue verifiable credentials to creators and other rightsholders. Creator Credentials will increase the trustworthiness of declarations and claims to digital media content online.

[https://trustchain.ngi.eu/creatorcredentials](https://trustchain.ngi.eu/creatorcredentials)
{% endhint %}

