# Federated Registries vs. Centralised Approaches

As AI systems rely on public digital content for training, creators and rightsholders are looking for ways to express reservations about such uses. In response, a range of opt-out mechanisms have emerged – yet many raise concerns about their efficiency, accessibility, and robustness. Among these methods, centralised registries have been proposed to collect and store declarations, but such approaches have drawn criticism from rightsholders for imposing unnecessary burdens, overlooking sectoral diversity, and centralising control.

The Liccium registry infrastructure offers an alternative: a federated model of expressing AI-related preferences. It avoids central, monopolistic and expensive control, supports a wide range of sector-specific metadata, workflows and license models, and ensures declarations are verifiable, scalable, and accessible – without placing new burdens on creators.

This page explains the difference between centralised and federated registry models, how the Liccium system works, and why this approach addresses creator concerns.

## Concerns About Centralised Registries

From creators and publishers, several recurring concerns have been identified:

* Central control and governance risks: Who owns, controls and operates the registry?&#x20;
* Intervention in the authority of Member States: Central registries are rarely compatible with EU administrative competencies.&#x20;
* Lack of sectoral alignment: Different sectors (books, press, photos) have their own specific metadata, workflows, and service providers.
* Duplicate effort: Centralised systems may require creators to manually register works that are already distributed via sectoral channels.
* Copyright re-affirmation: Creators fear being forced to re-prove or re-claim rights they hold by default.
* Language and region: Multilingual or jurisdiction-specific support is often lacking.
* Single point of failure: If a central database is taken offline or corrupted, access is lost.

## The Liccium Approach: Federated Registries

The Liccium registry infrastructure is designed to overcome these challenges through a federated, API-based, and peer-to-peer (p2p) model.

### **Core Principles**

* No central authority: Liccium registries operate on a p2p network – no single server, owner, or gatekeeper.
* Declaration = rights + signature: Each declaration includes cryptographic proof of identity and intent.
* Open API standard: All declarations follow a common specification (see [dev.liccium.com](https://dev.liccium.com/)).
* Sector integration: Any service provider (publisher, distributor, CMS, DAM, etc.) can implement the API and submit declarations on behalf of creators.
* Verifiable identity: Each declaring party is authenticated — via certificates or Verifiable Credentials.
* Scalable access: Declarations are synchronised across the network and accessible via a public registry index, not a centralised database.

### **What This Means in Practice**

* Creators are not burdened: Declarations can be made automatically via existing software (e.g. publishing tools, DAM systems, standard user apps and platforms). No need for creators to fill out separate registry forms.
* Avoidance of administration costs: Using a federated opt-out system avoids costs for redundant, duplicate data transmission where only the expression of a rights reservation is intended.
* Rightsholders maintain data sovereignty: Databases remain closer to the respective data sovereigns (such as publishers, public authorities, museums, libraries and CMOs).
* No need to re-affirm copyright: The Liccium model is not about establishing or proving ownership or copyright – it's about enabling the easy, secure and effective expression of preferences with regards to the exception (TDM), verifiably and at scale.
* Regional and sector-specific support: Any organisation – including creator or membership organisations, CMOs, or commercial service providers – can run a registry node or integrate the API into their tools. This also allows development of licensing models and effective bundling of licensing offers.
* Extensible metadata: Sector-specific metadata (e.g. IPTC for photos, ONIX for books) can be included or referenced. The common opt-out vocabulary (as defined here on [tdmai.org](https://tdmai.org/), based in the IETF vocabulary) is minimal and non-intrusive. Redefinition of established industry standards is unnecessary.
* Public auditability and resilience: All declarations are publicly resolvable, tamper-evident, and can be update over time – even if one registry node goes offline.

## Comparison Table

<table><thead><tr><th width="184.55859375">Feature</th><th width="182.66796875">Centralised Registry</th><th>Liccium Federated Registry</th></tr></thead><tbody><tr><td>Control model</td><td>Single operator</td><td>Decentralised, p2p</td></tr><tr><td>Governance</td><td>Central authority</td><td>Open protocol, sector participation</td></tr><tr><td>Authentication</td><td>Varies</td><td>Cryptographic identity (VCs, certificates)</td></tr><tr><td>Creator interaction</td><td>Direct submission required</td><td>Direct or indirect via trusted tools/providers</td></tr><tr><td>Metadata standards</td><td>Prescribed or inflexible</td><td>Flexible, sector-specific</td></tr><tr><td>Regional / language support</td><td>Limited</td><td>Local providers, multilingual</td></tr><tr><td>Copyright affirmation</td><td>Often required</td><td>Not required</td></tr><tr><td>Redundancy</td><td>Single point of failure</td><td>Distributed, resilient</td></tr><tr><td>Public discoverability</td><td>Controlled access</td><td>Open, verifiable index</td></tr><tr><td>Compliance support<br>(AI Act)</td><td>Varies</td><td>Full alignment with opt-out vocab</td></tr></tbody></table>

## Benefits of the Federated Model

In addition to solving the core concerns, the Liccium model provides:

* Interoperability across sectors, tools, and jurisdictions
* Compliance readiness for the EU AI Act and other frameworks
* Future-proof design for evolving vocabularies and metadata information (e.g. AI inference use cases)
* Trust infrastructure built on cryptographic signatures and DID/VC standards
* Integration with discovery: registry entries are publicly resolvable, inseparably bound to the content.

## Conclusion

The notion of a “registry” need not imply central control or burden on creators. The Liccium federated registry infrastructure enables decentralised, verifiable, and scalable declarations that are easy to perform and respect the diversity of content sectors – while providing reliable compliance signals for AI developers, platforms, and regulators.

By shifting from centralised control to distributed trust, Liccium offers a new foundation for rights reservation, creator agency, and cross-sector transparency in the AI age.

\
\
