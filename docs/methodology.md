# SatQuery AI — Methodology

## Overview

SatQuery AI combines a vision-language model with specialized remote-sensing processing and an agentic workflow.

The system is designed to separate visual interpretation from task-specific computation and analysis.

## 1. User Query

The user provides a natural-language question along with the relevant remote-sensing imagery.

The query and available imagery are used to determine the appropriate analysis path.

## 2. Agentic Routing

SatQuery evaluates the user's request and selects the relevant specialist capability.

The routing layer determines whether the request should be handled through capabilities such as:

- Vision-Language Question Answering
- NDVI / Spectral Analysis
- Temporal Analysis
- Grounding
- Optical–SAR Fusion
- Specialized Counting

## 3. Vision-Language Processing

For visual reasoning tasks, SatQuery uses a remote-sensing Vision-Language Model.

The model is adapted for the target workflow using LoRA / PEFT rather than retraining the underlying model from scratch.

## 4. Geospatial Processing

For quantitative and geospatial tasks, SatQuery uses dedicated processing rather than relying on the VLM to estimate numerical results.

The system works with remote-sensing imagery and associated geographic metadata where required by the analysis.

## 5. Specialized Analysis

Different analysis paths perform different operations depending on the query.

### Spectral Analysis

NDVI is calculated from the relevant satellite bands using deterministic computation.

### Temporal Analysis

Imagery from different dates can be compared to analyze temporal differences and changes.

### Optical–SAR Analysis

Optical and SAR information can be incorporated for multimodal remote-sensing analysis.

### Grounding

Grounding provides spatial references to relevant regions or objects within imagery.

## 6. Evidence Generation

The analysis produces supporting information alongside the final result.

Depending on the selected workflow, this may include visual overlays, measurements, metadata, execution information, and downloadable outputs.

## 7. Result Delivery

The final response is presented through the SatQuery interface together with the relevant supporting evidence.

This allows users to inspect not only the answer, but also the analysis performed to produce it.
