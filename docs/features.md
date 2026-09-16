# SatQuery AI — Features

SatQuery AI combines vision-language understanding with specialized remote-sensing capabilities through an agentic workflow.

## 🧠 Vision-Language Question Answering

SatQuery can interpret remote-sensing imagery and answer natural-language questions about the scene.

The VLM is adapted for the remote-sensing domain using parameter-efficient fine-tuning.

## 🤖 Agentic Routing

SatQuery uses an agentic routing layer to determine which capability should handle a user's query.

Instead of forcing every request through the same model, the router selects the appropriate specialist based on the task.

## 🌱 NDVI Analysis

SatQuery performs deterministic NDVI analysis using calibrated satellite bands rather than asking the VLM to estimate numerical values.

The workflow can produce:

- NDVI calculations
- Threshold-based analysis
- Pixel statistics
- Area measurements
- Visual overlays
- Geospatial metadata
- Downloadable outputs

## 🛰️ Optical & SAR Analysis

SatQuery supports analysis involving optical and SAR imagery, allowing information from different remote-sensing modalities to be incorporated into the workflow.

## 🕒 Temporal Analysis

SatQuery can work with imagery from different dates to support temporal analysis and identify changes across observations.

## 📍 Grounding

SatQuery supports spatial grounding, allowing relevant regions or objects in imagery to be referenced rather than relying only on a text description.

## ⚾ Specialized Counting

SatQuery includes a specialized counting workflow for supported scenes and uses validation checks before returning a result.

## 🔎 Evidence & Auditability

SatQuery is designed to preserve supporting information alongside results.

Depending on the task, this can include:

- Visual overlays
- Pixel-level statistics
- Thresholds and parameters
- Geospatial metadata
- Execution details
- Downloadable artifacts
- Structured run records

## 🧩 Modular Architecture

Each analysis capability is implemented as a specialist within the larger SatQuery workflow.

This makes it possible to add or improve capabilities independently while keeping the overall architecture consistent.
