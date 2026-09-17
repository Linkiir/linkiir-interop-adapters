# Linkiir Interoperability Adapters

Standards-based exchange adapters that are not FHIR: HL7 v2 tooling, C-CDA documents, IHE profiles, HIE networks, public health reporting, and migration off a legacy interface engine.

A **catalog** is a package of adapter content that one Linkiir Grid publishes and other grids subscribe to. Subscribing adds these adapters to your grid without a product upgrade.

| | |
|---|---|
| **Catalog id** | `lkintr` |
| **Publisher** | Linkiir Inc |
| **Adapters** | 0 |
| **Libraries** | 0 |
| **Documentation** | [https://help.linkiir.com/docs/catalogs/](https://help.linkiir.com/docs/catalogs/) |

---

## Subscribe

In Grid, open **Settings → Catalogs → Subscribe** and paste this URL:

```
https://github.com/Linkiir/linkiir-interop-adapters
```

| Field | Value |
|---|---|
| **URL** | the address above |
| **Ref** | `main` |
| **SSH private key** | leave blank — this is a public repository, cloned anonymously |
| **Install name** | `linkiir-interop-adapters` |

Use the install name exactly as given. Grid records it on every node built from this catalog, so a consistent name keeps a node's origin readable when you contact support.

Subscribing requires the **Manage catalogs** permission (Administration tier). Full instructions, including how to review an update before applying it, are in [the Catalogs documentation](https://help.linkiir.com/docs/catalogs/).

## Contents

This catalog is registered and reserved, but **no adapters have been published to it yet**. Grid will refuse a subscribe until it holds at least one adapter or library, so there is nothing to add to your grid from here today.

Watch this repository to be notified when its first adapters ship, or talk to your Linkiir contact about adapter coverage for this domain.

## Repository layout

```
catalog.json                              catalog manifest
nodes/<slug>/node_config.json             an adapter definition
nodes/<slug>/*.lua                        its scripts
nodes/<slug>/samples/                     de-identified test messages
libraries/<name>/<version>/library.json   a published library version
libraries/<name>/<version>/<name>/*.lua   its modules
```

The layout matches Grid's own on-disk layout, so a pull applies no transform.

## Other Linkiir catalogs

| Catalog | Covers |
|---|---|
| [linkiir-fhir-adapters](https://github.com/Linkiir/linkiir-fhir-adapters) | FHIR adapters and FHIR tooling |
| [linkiir-ehr-adapters](https://github.com/Linkiir/linkiir-ehr-adapters) | EHR and practice management over proprietary APIs, openEHR |
| **linkiir-interop-adapters** _(this one)_ | HL7 v2, C-CDA, IHE, HIE, public health, engine migration |
| [linkiir-payer-adapters](https://github.com/Linkiir/linkiir-payer-adapters) | X12 EDI, clearinghouses, payer APIs, pharmacy |
| [linkiir-diagnostics-adapters](https://github.com/Linkiir/linkiir-diagnostics-adapters) | labs and LIS, imaging and PACS, devices |
| [linkiir-data-adapters](https://github.com/Linkiir/linkiir-data-adapters) | relational and NoSQL databases, warehouses, BI |
| [linkiir-transport-adapters](https://github.com/Linkiir/linkiir-transport-adapters) | object storage, file transport, message brokers |
| [linkiir-ai-adapters](https://github.com/Linkiir/linkiir-ai-adapters) | AI and LLM services |
| [linkiir-notification-adapters](https://github.com/Linkiir/linkiir-notification-adapters) | chat, SMS, voice, email, paging |
| [linkiir-business-adapters](https://github.com/Linkiir/linkiir-business-adapters) | CRM, ERP, ITSM, HR, identity, scheduling |

## Documentation and support

Product documentation lives at **[help.linkiir.com](https://help.linkiir.com/docs/catalogs/)** — how catalogs work, subscribing and reviewing updates, building nodes from catalog adapters, and offline delivery. This repository holds the adapter content itself; it is not the documentation site.

For a question about a specific adapter, quote its node type id.

## License

Copyright © Linkiir Inc. All rights reserved.

This source is published so Linkiir Grid customers can read, audit and run it. It is **not** open source, and no open-source licence is granted. Use of this content is governed by your agreement with Linkiir Inc covering Linkiir Grid. For licensing enquiries, contact Linkiir.

