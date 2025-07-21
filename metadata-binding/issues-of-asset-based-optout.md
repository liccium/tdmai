# Issues of Asset-Based Optout

There are multiple standards to embed rights and metadata inside the media file itself, such as IPTC or C2PA.&#x20;

Content creators and publishers can use apps that support the C2PA method to create and embed cryptographically verifiable metadata containing information about the asset’s creation and edit actions, copyright, licences, capture device details, and software used. This manifest may include TDM assertions that enable "a human actor to provide a C2PA Manifest Consumer information about whether an asset with C2PA metadata may be used as part of a data mining or AI/ML training workflow." The assertions are designed to be hashed and gathered into a verifiable claim that is digitally signed, ensuring the integrity of the claim.

However, hard-binding of the embedded assertions and metadata within the content breaks in the following situations:&#x20;

* When embedded metadata (or the certificate) is removed from the media file;
* When content is altered or manipulated even to a small extend, as the method is based on cryptographic hashing;&#x20;
* When content is converted into a different file format, compressed or screenshotted.

However, these are very common problems when content is shared online or on social media platforms that resize or compress media files or remove embedded metadata for security and business reasons.
