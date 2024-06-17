---
description: THIS IS A TEMPORARY DRAFT FOR DISCUSSION Last updated 2024-06-17
---

# Benefits

TDM·AI utilises the International Standard Content Code (ISCC), an new ISO standard for digital media content ([ISO 24138:2024)](https://www.iso.org/standard/77899.html) and verifiable Creator Credentials, based on[ W3C recommendation for cryptographically verifiable credentials](https://www.w3.org/TR/vc-data-model-2.0/), to ensure verifiable and machine-readable declarations that include proper attribution of claims.&#x20;

Let's get into the details of the advantages of this solution.&#x20;

## Benefits of the ISCC

* **Content-derived Identifier**: The ISCC serves as a content-derived identifier for the specific digital media asset, allowing various parties, including users and machines, to generate codes only by having access to the file.
* **Accessible and Open-Source**: ISCC codes can be generated using open source software or applications such as Liccium. It is open-sourced with a permissive licence, lightweight, dockerised, and effortlessly deployable.&#x20;
* **Versatility Across Media Types**: ISCC can be used with all media types (text, images, video, audio) and [supports a wide range of file formats](https://github.com/iscc/iscc-sdk/blob/872795b8fdcbb66a7c71dd9b5020589e2c8ad832/iscc\_sdk/mediatype.py#L204).
* **Resilience Amid Metadata Removal**: ISCC allows robust identification and matching of media assets even in cases where metadata was removed, a common occurrence when content is shared online or via social media.
* **Effective When Shared**: ISCC remains effective even when content is taken out of its original context and initial metadata or attribution becomes inaccessible due to content sharing on third-party domains outside the control of the rightsholders, potentially losing creator or rights information in robots.txt files or other metadata.
* **Robustness against content changes**: ISCC retains its reliability even if content is changed, modified or manipulated.

## Benefits of ISCC Declarations

* **Inseparably Binding Rights and Metadata**: ISCC declarations enable the secure and indissoluble binding of external metadata, rights, or other claims, along with verifiable credentials, to the content, offering substantial advantages to creators and rightsholders.
* **Machine-Readable Declarations**: ISCC declarations, in conjunction with verifiable credentials, can provide relevant and sufficient information regarding rights and restrictions in a machine-readable way.
* **Verifiable, Timestamped Data**: ISCC declarations are both timestamped and cryptographically verifiable, ensuring the integrity and temporal context of the associated information.

## Benefits of Creator Credentials

The Creator Credentials project will develop a user-centric digital identity management framework that is specifically designed to serve the unique needs of the cultural and creative industries.&#x20;

{% embed url="https://docs.creatorcredentials.com/" %}
Documentation of the Creator Credentials project
{% endembed %}

Creator Credentials offer a multitude of essential features and benefits that not only enhance security but also facilitate seamless interoperability across various systems and applications:

1. Creator Credentials are **self-sovereign**, which means that creators and rightsholders have primary ownership and control over their credentials. They can choose where to host, when to use, and how to share them, including controlling access levels and revoking access if needed.
2. Creator Credentials are **portable**, which means that once issued the holder can transfer credentials between different systems and platforms without loss of information or functionality. They can also be used with various applications or services as required.
3. Creator Credentials are **interoperable**, which means that credentials issued by one system can be recognised and accepted by other systems, even if they are built on different technologies or operated by different organisations. Third party applications can independently verify these credentials.
4. Creator Credentials  can also be **restricted in duration**. This means they support the ability to set expiration dates for verifiable credentials, defining a time limit on how long a verifiable credential is valid. Limited validity can be useful for credentials that expire, such as professional licence or certifications.
5. Creator Credentials  are **revocable**, which means that they can be revoked or cancelled in cases of expiration or other reasons. This is important for maintaining the integrity of the credential system and ensuring that only valid and accurate information is being shared. The revocation can be initiated by the issuer of the credential or by the individual or entity who holds the credential. It can be enforced by the systems that recognise and accept the credential.
6. Creator Credentials are **cryptographically verifiable**, which is essential for the proper attribution of rights and restrictions, ensuring transparency and accountability.
7. Creator Credentials are **resilient**. Using them in the context of ISCC declarations, even in cases of content alteration, manipulation, or removal of watermarks or metadata, Creator Credentials can still be derived from the content and its associated ISCC code.
8. Creator Credentials are **publicly accessible**, allowing for verification within the context of any public content declaration or claim.
9. Creator Credentials are **immutable and trustworthy**, meaning they cannot be altered without detection or notice.
10. Creator Credentials are **timestamped** to ensure cryptographic verifiability and transparency and to provide information about who made a declaration and when it was made, both for humans and machines.

{% hint style="info" %}
In 2023, the European Union funded a project called 'Creator Credentials' as one selected project of the NGI's Trustchain consortium under grant agreement Nr. 101093274.&#x20;

The Creator Credentials project will develop a user-centric digital identity management framework specifically designed for the cultural and creative communities. This includes a software application that can be used by media organisations to issue verifiable credentials to creators and other rightsholders. Creator Credentials will increase the trustworthiness of declarations and claims to digital media content online.

[https://trustchain.ngi.eu/creatorcredentials](https://trustchain.ngi.eu/creatorcredentials)
{% endhint %}

