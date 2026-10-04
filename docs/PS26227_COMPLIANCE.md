# ORBITAL EYE — PS 26227 COMPLIANCE MATRIX

This document maps the requirements of **Smart India Hackathon 2026 Problem Statement 26227** ("Semantic Retrieval and Multi-Temporal Change Analysis of Satellite Imagery") to the implemented architecture of **ORBITAL EYE**.

---

### Compliance Matrix Table

| Requirement | Implementation | Status | Evidence / File / Module | Limitation |
| :--- | :--- | :--- | :--- | :--- |
| **2.2.1 Semantic & Multimodal Retrieval** | Free-text search, embedding similarity, date/sensor/AOI filters over local archive catalog. | **VERIFIED** | `server/retrieval/semanticSearchService.ts`, `server/routes/search.ts` | Bounded by local catalog scene count and embedding coverage. |
| **2.2.2 Multi-Temporal Change Analysis** | Chronological sorting, multi-epoch differencing, appearance/disappearance/construction flags, earliest supporting observation estimation. | **VERIFIED** | `server/temporal/temporalEngine.ts`, `server/analysis/eoIntelligenceService.ts` | Requires two or more co-located observations. |
| **2.2.3 False-Alarm Suppression** | Data quality checks, registration stability, cloud/haze/shadow screening, seasonal/phenological checks. | **VERIFIED** | `server/temporal/falseAlarmDecisionEngine.ts`, `server/evidence/RemoteSensingEvidenceEngine.ts` | Heuristic and statistical radiometric screening. |
| **2.2.4 Discovery & Clustering** | "Find more like this", embedding similarity, K-Means clustering, cluster representatives. | **VERIFIED** | `server/discovery/similarSiteService.ts`, `server/routes/discovery.ts` | Similarity indicates feature correlation, not temporal causation. |
| **2.2.5 Analyst Workflow & Provenance** | Ranked analyst review queue with Confirm / Reject / Uncertain actions and SHA-256 audit logs. | **VERIFIED** | `server/review/reviewQueueService.ts`, `server/review/auditTrailService.ts` | Local persistence layer. |
| **2.2.6 Scale, Ingestion & Sovereignty** | GeoTIFF, TIFF, COG, PNG ingestion, spatial transform, CRS, bounds, incremental indexing. | **VERIFIED** | `server/archive/ingestionEngine.ts`, `server/archive/catalogService.ts` | Large multi-terabyte raster archives require clustered object storage. |
| **2.2.7 Offline Evaluation Constraint** | Local embedding models, local vector index, zero external runtime dependency in offline mode. | **VERIFIED** | `server/embedding/embeddingEngine.ts`, `server/server.ts` | Requires pre-staged local weights on air-gapped evaluation hardware. |
