# Linkiir Interoperability Adapters

Standards-based exchange that is not FHIR: HL7 v2 tooling, C-CDA documents, IHE profiles, national and regional HIE networks, mandated public health reporting, and adapters that migrate off a legacy interface engine.

**Catalog id:** `lkintr` — every node template in this catalog carries a `LKINTR_` node type id.
**Published adapters:** 0 &nbsp;•&nbsp; **Published libraries:** 0

---

## Subscribe

In Grid, go to **Settings → Catalogs → Subscribe** and paste:

```
https://github.com/Linkiir/linkiir-interop-adapters
```

This is a public repository, so Grid clones it anonymously and no SSH key is needed. Leave **Ref** at `main` to track the latest published content.

Install it under the name **`linkiir-interop-adapters`**. The install name is recorded on every node built from this catalog, so keeping it consistent makes a node's origin readable in support.

Subscribing needs the **Manage catalogs** permission (Administration tier).

> **Note:** this catalog is registered but holds no adapters yet, so a subscribe will be refused until its first node or library is published. The roadmap below is what is coming.

## Published adapters

_None yet._

## Published libraries

_None yet._

## Roadmap

| Adapter | Node type | Connects to | Status |
|---|---|---|---|
| HL7 v2 Parser / Builder | transform | HL7 v2 segment grammar | Next |
| HL7 Code Set Mapper | transform | HL7 v2.5 to v2.3 vocabulary mapping | Next |
| C-CDA Reader / Writer | transform | C-CDA documents | Planned |
| IHE PIX / PDQ and XDS.b / XCA | source, destination | patient identity and document registry | Planned |
| Engine migration: Mirth, Rhapsody, Cloverleaf, Corepoint, Ensemble, BizTalk, Iguana, Summit | transform | incumbent engine config to Grid workflow | Planned |
| HIE: Carequality, CommonWell, TEFCA QHIN, eHealth Exchange, Direct | source, destination | HIE networks | Planned |
| Public health: ELR, eCR, IIS, syndromic, NHSN, NAACCR, PDMP | destination | mandated reporting | Planned |

Status meanings: **Next** is in active development, **Planned** is scoped but not started. See [the Integration Network](https://linkiir.com/network/) for the full adapter list and where each one stands.

## Configuration and credentials

Every adapter ships with its credential fields **empty**, and that is deliberate. Password fields are encrypted with each grid's own key, so a value shipped from here could not decrypt on your machine — it would fail with an error blaming your key. Fill them in on the node after you build it.

Two fields appear on most adapters and are worth knowing:

- **Live Mode** — when off, requests are prepared and logged but never sent. Use it to prove configuration before touching a real system.
- **Verify TLS** — leave on. Turn it off only against a local service with a self-signed certificate.

## Support and status

Adapters here are **Beta** unless the roadmap table says otherwise: they work and run somewhere, but the template is still being finished, so expect a Linkiir engineer alongside you on a first deployment. **GA** means the template is hardened and running across multiple customers.

Every adapter has a named owner at Linkiir who maintains it. For a problem with a specific adapter, quote its node type id.

## Versioning

- **Adapters** are versioned by the `version` field in `node_config.json`. A change that does not move the version forward is refused by the validator.
- **Library versions are immutable.** A published `libraries/<name>/<version>/` directory is never edited; a fix ships as a new version directory. Several versions sit side by side and each node pins the one it uses, so updating this catalog cannot disturb a node pinned to an older library.

Before applying an update, Grid shows you the incoming commit and diff. Read [CHANGELOG.md](CHANGELOG.md) for what changed and why.

## Repository layout

```
catalog.json                              the manifest Grid validates
nodes/<slug>/node_config.json             an adapter's definition
nodes/<slug>/*.lua                        its scripts
nodes/<slug>/samples/                     de-identified test messages
libraries/<name>/<version>/library.json   a published library version
libraries/<name>/<version>/<name>/*.lua   its modules
```

The layout is identical to Grid's own on-disk layout, so a pull needs no transform.

---

Published by Linkiir Inc. Part of the [Linkiir catalog set](https://github.com/Linkiir?q=adapters) — see [the Catalogs documentation](https://help.linkiir.com/docs/catalogs/) for how catalogs reach a grid.
