---
description: DRAFT 2024-02-28
---

# TDM·AI Protocol

<figure><img src=".gitbook/assets/TDM-AI-LINEAR_B_IDEOGRAM_B104_DEER-1280-640.png" alt=""><figcaption></figcaption></figure>

## Summary

TDM·AI is a protocol to inextricably bind machine-readable opt-out declarations for Text and Data Mining (TDM) to the digital media content. It is based on the DSM Directive on Copyright 2019/790, Article 4, making use of the benefits of the International Standard Content Code ([ISCC](https://iscc.codes)) and [Creator Credentials](https://docs.creatorcredentials.com/).

## Abstract

The TDM·AI protocol aims to provide rightsholders with a standardised way to make a machine-readable declaration as to whether or not their content may or may not be used for AI training purposes. This permission or opt-out declaration can be derived directly from the content, which means that it is easily accessible for AI providers.

This protocol utilises the International Standard Content Code (ISCC), an upcoming global ISO standard for digital media content ([ISO 24138](https://www.iso.org/standard/77899.html)) and verifiable Creator Credentials, based on[ W3C recommendation for cryptographically verifiable credentials](https://www.w3.org/TR/vc-data-model-2.0/), to ensure verifiable and machine-readable declarations that include proper attribution of claims. The protocol also supports time-stamping of this statement.

By using the ISCC, the protocol ensures a decentralised and reliable method of identifying content, making it impervious to common problems such as metadata loss or content modification. The integration of verifiable creator credentials adds another layer of trust and verifiability, ensuring that the declarations are genuine and can be traced back to the original rights holder.

## Motivation

Given the evolving AI landscape, there is an urgent need for an protocol that allows content creators and rightsholders to reliably declare their consent or reservation to TDM for AI providers. The TDM·AI protocol is motivated by the need to:

* Provide clarity and simplicity for rightsholders to declare their TDM reservations,
* Offer a decentralised, immutable, and verifiable system for these declarations,
* Ensure that AI providers and other stakeholders can easily understand and respect these declarations.

## Issues With Current Approaches

Existing approaches are not effective in cases where:

1. The content is modified or manipulated,
2. Embedded metadata is removed from the media file,
3. Watermarks or steganographic data are removed from the content of the media file,
4. Content is shared&#x20;
   * on websites over which the original rightsholders have no control
   * on social media
5. False claims are made&#x20;
6. Users do not have access to proprietary software or centralised services to verify content declarations

## Requirements For Opt-out Declarations

Opt-out declaration should (be):&#x20;

1. Machine-readable,
2. Based on international standards (ISO, W3C),
3. Inseparably bound to the content (media asset) to enable sharing and distribution of content online and on social media,
4. Resilient to the manipulation of content,&#x20;
5. Resilient to the removal of embedded metadata, watermarks and steganographic data from the media file,
6. Provide verifiable attribution through digital signatures and certificates (creator credentials),
7. Provide a verifiable timestamp.

## Compatibility with C2PA

The TDM·AI protocol is a compatible with the content credentials of the C2PA standard, offering a complementary solution in cases where content has been modified or manipulated, or embedded metadata have been removed from the media file ("soft-binding").
