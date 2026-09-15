# Alamn Alawal — الأمن الأول

Sovereign intelligence platform. The entire backend ships as **one binary** —
no external services, no sidecars, no Docker stack. A single process owns the
database, the search index, the identity provider, and the HTTP surface.

Two constraints shape every decision:

1. **Sovereign deployment.** No external service dependencies. Embedded Rust
   equivalents replace Elasticsearch, TypeDB, Keycloak, MinIO, and OpenCTI.
2. **Permissive licenses only.** MIT, Apache-2.0, BSD/ISC. No GPL, LGPL, MPL,
   AGPL, or SSPL — enforced in CI.

## Repositories

| | |
|---|---|
| **[alamn-rust](../../alamn-rust)** | The platform. Cargo workspace: 30 domain crates, `alamn-server`, `alamn-cli`. |
| **[alamn-web](../../alamn-web)** | Separate incumbent analyst SPA. Bilingual en/ar with RTL. |
| **[alamn-reference-ui](../../alamn-reference-ui)** | Product frontend with Rust API and reference fixture modes. No shared frontend source. |
| **[alamn-docs](../../alamn-docs)** | Architecture, ADRs, and how the repos fit together. **Start here.** |
| **[alamn-cortex-legacy](../../alamn-cortex-legacy)** | The Python Cortex backend that `alamn-rust` replaces. Archived. |
| **[alamn-v1-preview](../../alamn-v1-preview)** | v1.0 product preview and wireframes. Archived. |

## Capability targets

Parity with Palantir Foundry, Gotham, and AIP, per the Product Capability Map.
Shipping today: embedded OIDC issuer with JWKS, Argon2id, tenant-scoped graph
store, BM25 full-text search, schema registry, optimistic-concurrency CRUD,
audit log on every write, classification and TLP markings, ABAC read-down /
no-write-up, and marking-aware graph traversal.

## Getting oriented

Read [`alamn-docs/docs/topology.md`](../../alamn-docs/blob/main/docs/topology.md)
first — it explains the repo boundaries and the one contract that crosses them.
