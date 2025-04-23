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

# Options for Metadata Binding

When it comes to managing opt-out declarations for TDM in a machine-readable way, in principle, two different approaches are discussed:&#x20;

1. **Location or domain-based metadata binding**: rightsholder preferences for web-published content are included in robots.txt-file or in HTML/HTTP metadata of the domain, e.g. Robots.txt, TDMrep;
2. **Asset-Based metadata binding**: metadata is embedded directly into the media file, e.g. C2PA.org (**Hard-Binding**).

<div align="center" data-full-width="false"><figure><img src="../.gitbook/assets/Opt-out Triangle.jpg" alt=""><figcaption></figcaption></figure></div>

## Why Do We Need Opt-Out Registries?

* Embedded metadata is removed from the media file.
* Content is altered or manipulated, compressed or converted into a different file format – and the method is based on cryptographic hashing.
* When content is already distributed, shared and part of training sets, metadata cannot be embedded.
* Content is shared on websites beyond the rightsholder's control,\
  e.g. on social media, so a domain-based approach cannot be applied.
* A lot of content is not publicly accessible on web domains.
* Watermarks or steganographic data can be removed from media files.
