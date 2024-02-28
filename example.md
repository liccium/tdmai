---
description: DRAFT 2024-02-28
---

# Example

## Declaration app

in this example [Liccium.app](https://liccium.app) is used.&#x20;

<figure><img src=".gitbook/assets/Liccium TDM·AI@2x.png" alt=""><figcaption><p>TDM·AI opt-out using Liccium.app</p></figcaption></figure>

A public declaration will package all declaration metadata in a JSON file, including the TDM·AI opt-out.&#x20;

{% code title="" overflow="wrap" lineNumbers="true" %}
```json
"liccium_plugins": {
    "tdmai": {
      "TDMAI": false,
      "TDMAI_policy_URL": "https://olive-labour-unicorn-913.mypinata.cloud/ipfs/QmX8qUyi2iXRT7BEX6D2SSJUqngQBN1hWkA1TFbQ9Zisad"
    },
    "iptc": {
      "digitalsourcetype": "minorHumanEdits",
      "keywords": "Washinton,1120",
      "acquireLicensePage": "https://posth.me",
      "webstatementRights": "https://creativecommons.org/licenses/by-sa/4.0/"
    }
  }
```
{% endcode %}

Source: Declaration metadata

{% embed url="https://olive-labour-unicorn-913.mypinata.cloud/ipfs/Qmd8sb5uPEVggGRBvb7TXZmhqqEqJ6MdTCqcUZhh2bNNNN" %}
URL to the JSON declaration metadata file
{% endembed %}

This JSON file is persistently bound to the ISCC code.
