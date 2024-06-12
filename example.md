---
description: DRAFT 2024-02-28
---

# Example

## Declaration App

For this example the [Liccium.app](https://liccium.app) is used. Feel free to sign-up on [Liccium.com](https://liccium.com) to receive an invite and test the applicaition.

<figure><img src=".gitbook/assets/Liccium TDM·AI@2x.png" alt=""><figcaption><p>TDM·AI opt-out using Liccium.app</p></figcaption></figure>

## Declaration Metadata

With a public declaration, all metadata of the declaration is compiled in a JSON file, including the TDM·AI opt-out (see code example below). This JSON file is persistently bound to the ISCC code.

{% code title="" lineNumbers="true" %}
```json
    "tdmai": {
      "TDMAI": false,
      "TDMAI_policy_URL": "https://olive-labour-unicorn-913.mypinata.cloud/ipfs/QmX8qUyi2iXRT7BEX6D2SSJUqngQBN1hWkA1TFbQ9Zisad"
    }
```
{% endcode %}

{% embed url="https://b2c-api-main-e5886ec.d2.zuplo.dev/v1/cid/dj7Wifs12k34TDAnred7RTcEjmU8FY9m8E86DL5ZYgtktyjh" %}
URL to the declaration metadata JSON file
{% endembed %}

## TDM·AI Opt-out

The declaration metadata JSON file links to the opt-out declaration.

{% embed url="https://liccium.app/api/v1/cid/optout" %}
URL to the opt-out declaration JSON file
{% endembed %}
