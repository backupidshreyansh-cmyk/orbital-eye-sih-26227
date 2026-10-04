# ORBITAL EYE — FINAL DEMO RUNBOOK (SIH 2026 PS 26227)

This runbook outlines the exact procedure for demonstrating **ORBITAL EYE** to evaluators for Smart India Hackathon 2026 Problem Statement 26227.

---

### Core Product Story

$$\text{SEARCH} \longrightarrow \text{COMPARE} \longrightarrow \text{VERIFY} \longrightarrow \text{DISCOVER} \longrightarrow \text{REVIEW}$$

---

### Recommended Demo Scenarios

#### Scenario 1: Semantic Discovery
- **Query**: `"Find areas with newly developed structures near a river."`
- **Workflow**: Enter query in the Semantic panel or mission bar $\rightarrow$ Semantic retrieval searches archive $\rightarrow$ Ranked candidate scenes returned with relevance scores, sensor tags, acquisition dates, and retrieval rationale.

#### Scenario 2: Temporal Change
- **Scenario**: Multi-temporal observation pair (Krishna River / Amaravati development).
- **Workflow**: Load co-temporal pair into Multi-Temporal Lab $\rightarrow$ View Before & After observations $\rightarrow$ Examine detected pixel differences (MAD, changed surface area) $\rightarrow$ Review false-alarm checks $\rightarrow$ Observe earliest supporting observation (e.g. 2023).

#### Scenario 3: Similar-Site Discovery
- **Workflow**: Select reference site $\rightarrow$ Click "Find more like this" $\rightarrow$ System groups similar archive locations into embedding clusters $\rightarrow$ Inspect cluster representatives and similarity scores (emphasizing: *Similarity $\neq$ Change*).

#### Scenario 4: False-Alarm / Uncertainty
- **Scenario**: Seasonally varying vegetation or water level variation.
- **Workflow**: Query scene with seasonal shift $\rightarrow$ System evaluates radiometric distribution $\rightarrow$ Reaches `LIKELY_SEASONAL_VARIATION` or `REGISTRATION_UNCERTAIN` instead of false positive change $\rightarrow$ Demonstrates professional restraint and reliability.
