# Fitrax: Supplementary Evaluation & Research Artifacts

[![Conference: ICBME 2026](https://img.shields.io/badge/Conference-ICBME%202026-blue.svg)](https://icbme.iut.ac.ir/)
[![License: CC BY 4.0](https://img.shields.io/badge/Data_License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Status: Available](https://img.shields.io/badge/Artifacts-Available-brightgreen.svg)]()

This repository contains the official supplementary research artifacts, anonymized empirical evaluation datasets, server telemetry logs, and algorithmic prompt blueprints for the paper:

> **"Fitrax: A Context-Aware AI Fitness Application for Decision Support in Resistance Training"**  
> **Paper ID:** #1624  
> **Conference:** **The 33rd National and 11th International Iranian Conference on Biomedical Engineering (ICBME 2026)**  
> **Dates & Venue:** November 18–19, 2026 — Isfahan University of Technology (IUT), Isfahan, Iran  
> **Organizer & Support:** Supported by the Iranian Society of Biomedical Engineering (ISBME)  
> **Conference Website:** [https://icbme.iut.ac.ir/](https://icbme.iut.ac.ir/)  
> **Repository:** [https://github.com/shayanfp/Fitrax-Evaluation-Research](https://github.com/shayanfp/Fitrax-Evaluation-Research)

---

## 👥 Authors & Affiliations

* **Shayan Farhang Pazhooh**  
  *Department of Industrial and Systems Engineering, Isfahan University of Technology, Isfahan 84156-83111, Iran*  
  📧 [shayanfp2006mail@gmail.com](mailto:shayanfp2006mail@gmail.com) | 🆔 ORCID: [0009-0001-1366-7942](https://orcid.org/0009-0001-1366-7942)

* **Prof. Morteza Rasti-Barzoki** *(Full Professor)*  
  *Department of Industrial and Systems Engineering, Isfahan University of Technology, Isfahan 84156-83111, Iran*  
  📧 [rasti@cc.iut.ac.ir](mailto:rasti@cc.iut.ac.ir) | 🆔 ORCID: [0000-0002-6979-4123](https://orcid.org/0000-0002-6979-4123)

---

## 📂 Repository Structure

```
Fitrax-Evaluation-Research/
├── README.md                          # Repository overview and replication guide (this file)
├── data/
│   ├── survey_data_anonymized.csv     # Anonymized Likert & qualitative usability survey (N=11)
│   ├── README_DATASET.md              # Complete survey codebook, anchors, and statistical tables
│   └── telemetry_summary.csv          # Real-world server telemetry & performance metrics
├── samples/
│   └── sample_ai_outputs.json         # Sample input and output payloads across core system features
└── docs/
    └── prompt_blueprints.md           # Systematic 4-tier prompt engineering & safety architecture
```

---

## 📑 Artifact Descriptions

### 1. Empirical Evaluation Dataset (`data/`)
* **`survey_data_anonymized.csv`**: Contains complete, anonymized responses from 11 active resistance-training participants ($N = 11$). Spans 5-point Likert usability metrics covering Workout Logging Usability ($4.09 \pm 0.70$), Rest Timer Utility ($3.73 \pm 1.27$), AI Decision Support ($3.64 \pm 1.29$), Gamification/Motivation ($4.36 \pm 0.50$), and Behavioral Adoption Intention ($4.09 \pm 0.70$), alongside qualitative feedback in Persian with English translations.
* **`README_DATASET.md`**: In-depth data dictionary, exact Likert anchors, screening criteria, and demographic distribution breakdown.
* **`telemetry_summary.csv`**: Aggregated performance summary extracted from actual production logs:
  * **Multimodal Vision Importer Latency:** Mean $31.67\text{ s}$ across production runs ($\le 2$ images).
  * **Intra-Workout Session Assistant Latency:** Mean $8.76\text{ s}$ for live in-session decision support queries.
  * **Post-Workout Feedback Latency:** Mean $6.52\text{ s}$ for end-of-session performance analysis (median: $2.96\text{ s}$).
  * **Workout Routine Volume:** Mean of $10.33$ exercises and $26.58$ completed sets per session across external users.
  * **Structural Compliance:** $100\%$ JSON schema validity maintained via two-layer regex sanitization.
  * **Completed Set Preservation:** $100\%$ immutability compliance for active completed sets during plan restructuring.

### 2. Sample System Outputs (`samples/`)
* **`sample_ai_outputs.json`**: Provides four production-grade input/output JSON schemas demonstrating:
  1. *Multimodal Vision Transcription:* Transformation of coach handwriting into partitioned Warmup/Main/Cooldown arrays.
  2. *Intra-Workout Q&A:* Safe substitution for crowded equipment considering pre-existing shoulder impingement.
  3. *Dynamic Plan Restructuring:* Mid-session time-constrained reorganization into antagonist supersets with completed sets strictly locked.
  4. *Post-Workout Performance Feedback:* Authentic coaching analysis highlighting performance wins, contextualizing user return from a 1-month break, and providing an actionable biomechanical cue.

### 3. Systematic Prompt Architecture (`docs/`)
* **`prompt_blueprints.md`**: Formulates the four-tier prompt engineering stack without exposing proprietary production code:
  * **Tier 1:** Persona & ACSM Evidence-Based Resistance Training Rules.
  * **Tier 2:** Orthopedic Guardrails across distinct physiological pathologies (`scoliosis`, `back_pain`, `shoulder_impingement`, etc.).
  * **Tier 3:** Dynamic Context Injection and Strict Completed Sets Immutability.
  * **Tier 4:** Five-Branch Structured Workout JSON Schema and Server-Side Sanitization.

---

## 🌐 Live Platform Access
* The web application interface is accessible at: **[https://fitrax.ir](https://fitrax.ir)**
* In-app automated synchronization operates via offline-first IndexedDB, localStorage state machines, and RESTful API endpoints.

---

## ⚖️ Ethical Considerations & Anonymization
All user evaluation records have been de-identified in strict adherence to human participant research standards. Personal identifiable information (PII) including phone numbers, device IDs, and direct gym sheet images have been excluded to safeguard subject confidentiality while ensuring full empirical reproducibility.
