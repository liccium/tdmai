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

# Federated Registries Explained

## What Is a Federated Registry?

A federated registry is a network of independently operated directories that synchronise their entries to provide a **unified, globally searchable database** of content and metadata declarations. Rather than relying on a single central authority, multiple registries participate in a **shared protocol**, enabling:

* Distributed operation across sectors and jurisdictions
* Trust through digital signatures and public key infrastructure
* High-availability querying by AI developers, search engines, and compliance tools

Each registry publishes **minimal metadata** derived from the original declaration – just enough to confirm the rights status of a piece of content identified by an ISCC code.

## How It Works

Registries use a distributed data structure known as a **Distributed Hash Table (DHT)** to store and resolve declarations. Each registry entry is indexed using cryptographic identifiers, including:

* An **ISCC code** as a persistent fingerprint of the media asset
* A **Content ID (CID)** to verify the integrity of the full metadata record
* A **Decentralized Identifier (DID)** referencing the declaring party
* A **timestamp** with cryptographic signatures for authenticity and traceability
* A **Declaration ID** derived from metadata, hashes, and signer identity

This system ensures that anyone – whether an online platform, AI developer, or rights organization – can verify the declared rights associated with a specific work using public registry data. Verification does not require access to full metadata or private storage systems. The declaring party’s identity is referenced through a Decentralized Identifier (DID) and supported by verifiable credentials, enabling trust without disclosing personal information.

## Operated by Many, Working as One

Registries can be run by creator groups, collecting societies, standards bodies, or compliance platforms. Each operator:

* Maintains its own node in the registry network
* Publishes declarations relevant to its members or mandate
* Can mirror or subscribe to declarations from other nodes

Because all registries speak the same "language" – a common metadata schema and synchronisation protocol – they function as **parts of a shared infrastructure**, even if operated independently.

## Tailored Access, Public Discovery

The registry layer is **public by design**—anyone can query it to check whether a content asset has been declared for a particular use case. At the same time, access to the full declaration data (stored separately) can be governed by access policies, ensuring **flexibility in governance and compliance**.
