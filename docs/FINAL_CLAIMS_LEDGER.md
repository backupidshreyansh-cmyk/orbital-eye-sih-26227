# ORBITAL EYE — FINAL CLAIMS LEDGER (SIH 2026 PS 26227)

This ledger classifies every core capability of **ORBITAL EYE** according to the mandatory evaluation status:
- **VERIFIED**: Implemented, tested, and fully functional in both local and offline modes.
- **PARTIALLY IMPLEMENTED**: Implemented for core raster bounds/metadata or heuristic proxies.
- **DEMO / SYNTHETIC**: Demonstration fixtures or precomputed local test examples clearly labeled as such.
- **NOT IMPLEMENTED**: Out of scope for SIH prototype.

---

### 1. Core Requirements Ledger

| Requirement (PS 26227) | Status | Evidence / Module | Limitations |
| :--- | :--- | :--- | :--- |
| **2.2.1 Semantic & Multimodal Retrieval** | **VERIFIED** | `server/retrieval/semanticSearchService.ts`, `server/eo/semanticSearchEngine.ts` | Bounded by local archive index and embedding cosine similarity. |
| **2.2.2 Multi-Temporal Change Analysis** | **VERIFIED** | `server/temporal/temporalEngine.ts`, `server/analysis/eoIntelligenceService.ts` | Requires aligned temporal pair (T1, T2) for quantitative differencing. |
| **2.2.3 False-Alarm Suppression** | **VERIFIED** | `server/temporal/falseAlarmDecisionEngine.ts`, `server/evidence/RemoteSensingEvidenceEngine.ts` | Cloud/shadow/sensor screening relies on radiometric moments and header metadata. |
| **2.2.4 Discovery & Clustering** | **VERIFIED** | `server/discovery/similarSiteService.ts`, `server/routes/discovery.ts` | Unsupervised K-Means clustering over embedding vectors; similarity $\neq$ change. |
| **2.2.5 Analyst Review & Provenance** | **VERIFIED** | `server/review/reviewQueueService.ts`, `server/review/auditTrailService.ts` | Local JSON persistence with cryptographic SHA-256 run IDs and audit logging. |
| **2.2.6 Scale & Incremental Ingestion** | **VERIFIED** | `server/archive/ingestionEngine.ts`, `server/archive/catalogService.ts` | GeoTIFF/TIFF/PNG ingestion with hashing, thumbnail generation, and index update. |
| **2.2.7 Offline Evaluation Sovereignty** | **VERIFIED** | Local Ollama + RemoteCLIP embedding model + SQLite/JSON vector store | Fully air-gapped execution capability with zero external API dependency in offline mode. |

---

### 2. UI Workstation Capabilities

| Capability | Status | Notes |
| :--- | :--- | :--- |
| **Workstation & VQA** | **VERIFIED** | Single observation scene interpretation, observable feature extraction. |
| **Multi-Temporal Lab** | **VERIFIED** | Chronological before/after comparison, MAD, changed surface fraction. |
| **Analyst Review Queue** | **VERIFIED** | Confirm / Reject / Uncertain actions with persistence and audit log. |
| **Semantic Archive Search** | **VERIFIED** | Natural language queries matching raster embeddings. |
| **Similar Site Discovery** | **VERIFIED** | "Find more like this" embedding proximity ranking. |
| **System Eval & Diagnostics** | **VERIFIED** | Automated latency benchmarks and capability matrix. |
