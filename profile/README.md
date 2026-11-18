# DisputeIQ Platform (`disputeiq-platform`)

An AI-native, multi-tenant dispute and chargeback resolution platform for card issuers and acquirers.

## Architecture Highlights

- **Zero-Trust Mesh**: Kubernetes + Istio ambient mode (`ztunnel` strict mTLS + L7 waypoint `AuthorizationPolicy` by SPIFFE ID).
- **Concurrency & Reliability**: Java 21+ Virtual Threads (`ScopedValue` carrier-safe tenancy, zero `ThreadLocal`), transactional outbox/inbox on Apache Kafka (KRaft + Apicurio), layered idempotency (`Idempotency-Key` + Postgres unique constraint + inbox dedupe).
- **GenAI & RAG**: Hybrid retrieval (`pgvector` HNSW + Postgres FTS + cross-encoder rerank), LangGraph4j triage & drafting state graph, PAN/PII redaction before every LLM call, CI evaluation gates.
- **GitOps Delivery**: Argo CD `ApplicationSets` + per-service OCI Helm charts (`diq-helm-library`) + Kargo promotion + Argo Rollouts canaries.

## Repository Index

| Category | Repositories |
|---|---|
| **Standards & Governance** | `diq-standards`, `.github` (`diq-org-github`), `diq-architecture` |
| **Templates & Shared Libs** | `diq-template-java`, `diq-template-web`, `diq-platform-libs`, `diq-event-schemas`, `diq-helm-library` |
| **Core Services** | `diq-gateway`, `diq-tenant-service`, `diq-dispute-service`, `diq-document-service`, `diq-knowledge-service`, `diq-agent-service`, `diq-notification-service`, `diq-network-simulator` |
| **Frontend & Delivery** | `diq-web`, `diq-gitops`, `diq-infra`, `diq-e2e` |

See `diq-architecture` for C4 diagrams and Architecture Decision Records (ADRs).
