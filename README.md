# TDM·AI Protocol

## Simple Summary

TDM·AI is a protocol to inextricably bind machine-readable opt-out declarations for Text and Data Mining (TDM) to digital media content based on the DSM Directive on Copyright 2019/790, Article 4, leveraging the benefits of the International Standard Content Code ([ISCC](https://iscc.codes)) and [Creator Credentials](https://docs.creatorcredentials.com/).

## Abstract

The TDM·AI protocol aims to provide a standardised and machine-readable way for rightsholders to declare whether their content may or may not be used for AI training purposes. This permission or opt-out can be derived and respected by AI providers.&#x20;

This protocol utilises the International Standard Content Code (ISCC) and verifiable Creator Credentials to ensure verifiable and machine-readable declarations that come with proper attribution. The protocol also supports time-stamping of this statement.

## Motivation

With the evolving landscape of AI, there's a pressing need for an application that allows content creators and rightsholders to declare their permissions regarding TDM for AI providers. The TDM·AI protocol is motivated by the need to:

1. Provide clarity and ease for rightsholders to declare their TDM permissions.
2. Offer a decentralised, immutable, and verifiable system for these declarations.
3. Ensure that AI providers and other stakeholders can easily understand and respect these declarations.

## Specification

1. **Declarations**:
   * **Opt-Out**: A machine-readable declaration by the rightsholder prohibiting use of content for AI training.
   * **Permission**: A machine-readable declaration indicating the rightsholder's consent for TDM for AI, or their change of stance from a previous restriction.
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

The TDM·AI protocol is designed with the primary goal of clarity and ease of use for both rightsholders and AI providers. By leveraging the ISCC, the protocol ensures a decentralised and reliable way to identify content, making it resilient against common challenges like the loss of metadata or the modification of content. The integration of verifiable Creator Credentials adds another layer of trust and verifiability, ensuring that declarations are genuine and can be traced back to the original rightsholder.

The choice of JSON for machine-readable declarations offers a widely accepted, standardised, and easy-to-parse format.

The protocol also considers future adaptability, with potential complementary approaches like watermarking or other standards like C2PA.
