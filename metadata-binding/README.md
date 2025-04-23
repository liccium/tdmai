---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Metadata Binding

## Options for Binding Rightsholders' Preferences

When it comes to managing rightsholders' preferences for TDM in a machine-readable way, in principle, three different approaches are discussed:&#x20;

1. **Location or domain-based metadata binding**: rightsholders' preferences for web-published content are included in robots.txt-file or in HTML/HTTP metadata of the domain, e.g. Robots.txt;
2. **Asset-based metadata binding**: provenance metadata – including rightsholders' preferences – is embedded directly into the media file, e.g. C2PA.org.
3. **Registry-based metadata binding**: ISCC fingerprints and metadata is submitted to publicly accessible registries.&#x20;

<figure><img src="../.gitbook/assets/Opt-out Triangle.jpg" alt=""><figcaption></figcaption></figure>

## Why Do We Need Opt-Out Registries?

* Embedded metadata is removed from the media file.
* Content is altered or manipulated, compressed or converted into a different file format – and the method is based on cryptographic hashing.
* When content is already distributed, shared and part of training sets, metadata cannot be embedded.
* Content is shared on websites beyond the rightsholder's control,\
  e.g. on social media, so a domain-based approach cannot be applied.
* A lot of content is not publicly accessible on web domains.
* Watermarks or steganographic data can be removed from media files.
