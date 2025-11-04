# Registries for Training Preferences

## A Standards-Based Model for Declaring Usage Restrictions

Creators and rightsholders who wish to express preferences about the use of their works in AI training can do so through a registry-based model for rights declarations. This model enables preferences to be expressed once and made discoverable to all relevant parties — including platforms, dataset curators, and AI model developers — in a machine-readable, standardised format.

The registry model relies on **federated content registries**: publicly accessible, verifiable directories that record metadata about how digital works may or may not be used, particularly in contexts such as text and data mining (TDM) and the training of AI models.

The **TDM·AI** protocol supports declarations that follow a shared structure, including:

* **ISCC codes** for uniquely identifying digital content, regardless of format or storage location
* **Opt-out categories** (e.g. for general TDM, AI training, generative AI training)
* **Machine-readable data formats** (e.g. JSON-LD) for integration into platforms, crawlers, and compliance tools

## Why Registries Are Needed

In the current digital environment, content is often collected and processed without direct interaction between the person using the content and the person who created it. Rights or usage permissions — if they exist at all — are typically buried in licensing terms, typically not machine-readable, hard to resolve at scale, or platform-specific.

Registries offer a structural solution. By linking declarations to the content itself (via ISCC fingerprints) and publishing them in a publicly accessible and verifiable form, they allow preferences to be made visible and actionable across systems.

This model provides:

* **Transparency** – Anyone can check whether a content asset is subject to a declared restriction
* **Consistency** – A shared vocabulary and format ensure that declarations are interpreted uniformly
* **Scalability** – The registry architecture supports high-volume indexing and look-up across billions of assets
* **Independence** – Registries are technology-neutral and not tied to a specific vendor, platform, or jurisdiction

Because declarations are made independently of the content’s location (e.g. not limited to a specific website or platform), they remain valid and resolvable even as content circulates across the internet or is reused in other contexts.
