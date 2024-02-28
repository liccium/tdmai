# TDM·AI Protocol

## Simple Summary

A protocol to facilitate machine-readable opt-out declarations for Text and Data Mining (TDM) for AI providers based on the DSM Directive on Copyright 2019/790, Article 4, leveraging the benefits of the International Standard Content Code ([ISCC](https://iscc.codes)) and [Creator Credentials](https://docs.creatorcredentials.com/).

## Abstract[^1]

The TDM·AI protocol aims to provide a standardized and machine way for rightsholders to declare their stance on TDM usage by AI providers, whether they opt-out or give permission. This protocol utilises the International Standard Content Code (ISCC) and creator credentials to ensure immutable, verifiable, and machine-readable declarations. The protocol also supports timestamping for clear issuance information and offers a decentralised approach to content identification and rights declaration.

## Motivation

With the evolving landscape of AI, there's a pressing need for an application that allows content creators and rightsholders to declare their permissions regarding TDM.&#x20;

The EU's DSM Directive on Copyright provides a default condition for TDM, but there's ambiguity when rightsholders want to opt-out or explicitly give permission. The TDM·AI protocol is motivated by the need to:

1. Provide clarity and ease for rightsholders to declare their TDM permissions.
2. Offer a decentralised, immutable, and verifiable system for these declarations.
3. Ensure that AI providers and other stakeholders can easily understand and respect these declarations.

## Specification

1. **Declarations**:
   * **Opt-Out**: A machine-readable declaration by the rightsholder limiting commercial TDM usage.
   * **Permission**: A machine-readable declaration indicating the rightsholder's consent for TDM, or their change of stance from a previous restriction.
2. **ISCC Integration**:
   * Utilise ISCC as a decentralised identifier for content.
   * ISCC remains effective even with content alterations, metadata loss, or when taken out of context.
3. **Creator Credentials**:
   * Ensure proper and verifiable attribution of rights, permissions, and restrictions.
   * Publicly accessible and immutable credentials with timestamping for verifiability.
   * Allow for self-sovereign control, portability, and interoperability of credentials.
4. **Timestamp**:
   * Every declaration should be timestamped to provide clear information about when it was issued.
5. **Machine-Readable Declarations**:
   * JSON format indicating the TDM·AI stance (`true` for permission, `false` for opt-out) along with a summary and detailed policy description.
6. **Content Links**:
   * IPFS links provided for each declaration, ensuring decentralized access and storage.

## Rationale

The TDM·AI protocol is designed with the primary goal of clarity and ease of use for both rightsholders and AI providers. By leveraging the ISCC, the protocol ensures a decentralised and reliable way to identify content, making it resilient against common challenges like metadata loss or content alterations. The integration of creator credentials adds another layer of trust and verifiability, ensuring that declarations are genuine and can be traced back to the original rightsholder.

The choice of JSON for machine-readable declarations offers a widely accepted, standardized, and easy-to-parse format. The use of IPFS links ensures that the content associated with declarations is stored in a decentralized manner, reducing the risk of data loss or tampering.

The protocol also considers future adaptability, with potential complementary approaches like watermarking or other standards like TDMrep and C2PA.

[^1]: 
