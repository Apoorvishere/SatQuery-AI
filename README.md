# 🛰️ SatQuery AI

### An Agentic Vision-Language Assistant for Multimodal Remote Sensing Image Analysis

SatQuery AI is an **Agentic Vision-Language Model (VLM) assistant** designed to analyze and reason over multimodal remote-sensing imagery.

It combines **optical and SAR imagery, temporal analysis, spatial grounding, NDVI analysis, specialized visual counting, and agentic tool selection** to provide contextual and evidence-oriented insights from satellite data.

---

## 🚀 Key Features

- 🧠 **Vision-Language Question Answering** — Natural-language interaction with remote-sensing imagery
- 🤖 **Agentic Routing** — Selects the appropriate analysis capability based on the user's query and available imagery
- 🌱 **NDVI Analysis** — Calculates NDVI, generates vegetation masks, and provides quantitative threshold-based measurements
- 🛰️ **Optical + SAR Analysis** — Combines complementary optical and SAR information for multimodal scene analysis
- 🕒 **Temporal Analysis** — Compares imagery from different dates to identify visible changes over time
- 📍 **Spatial Grounding** — Locates and outlines requested objects or regions within imagery
- ⚾ **Specialized Visual Counting** — Performs targeted counting of identifiable objects in remote-sensing scenes
- 🔎 **Evidence-Oriented Analysis** — Provides supporting visual evidence, measurements, and processing details alongside results
- 🧩 **Modular Analysis Specialists** — Dedicated processing paths for different remote-sensing tasks

---

## 🏗️ System Architecture

[View the full system architecture →](architecture/system-architecture.md)

SatQuery AI follows an agentic workflow in which a natural-language query and remote-sensing input are interpreted, the appropriate analysis capability is selected, specialized processing is performed, and the resulting evidence and measurements are presented to the user.

**Workflow:**

`User Query + Imagery → Input Validation → Agentic Routing → Specialized Analysis → Evidence & Measurements → Result`

---

## 🎯 Problem

Traditional remote-sensing analysis often requires specialized knowledge and separate tools for different types of imagery and analysis tasks.

SatQuery AI aims to provide a unified interface where users can interact with remote-sensing data using natural language while combining multiple sources of visual and geospatial information.

---

## 💡 What Makes SatQuery Different?

SatQuery is designed around the combination of:

**Multimodal Analysis + Agentic Reasoning + Temporal Understanding + Spatial Grounding + Quantitative Evidence**

Rather than treating satellite images as isolated inputs, the system can route different queries to specialized analysis paths depending on the task and available imagery.

This allows the same interface to support tasks ranging from visual question answering and object counting to NDVI measurement, temporal comparison, spatial grounding, and optical-SAR analysis.

---

## 🛠️ Technology Stack

### 🤖 AI / Machine Learning

- Vision-Language Models
- Qwen2-VL
- AdaptLLM Remote-Sensing VLM
- LoRA / PEFT
- Agentic Routing
- Multimodal Reasoning

### 🛰️ Remote Sensing & Geospatial

- Optical Satellite Imagery
- SAR Imagery
- Multispectral Analysis
- NDVI
- Temporal Change Analysis
- Spatial Grounding
- GeoTIFF / Raster Data

### ⚙️ Analysis & Computer Vision

- Python
- Rasterio
- NumPy
- DINO
- SAM
- Image Segmentation
- Object Detection
- Geospatial Processing

### 🌐 Application & Infrastructure

- FastAPI
- Uvicorn
- Local CPU / GPU Inference
- REST APIs
- Git
- GitHub

---

## 📚 Documentation

| Resource | Description |
|---|---|
| [System Architecture](architecture/system-architecture.md) | Overall SatQuery AI architecture and component relationships |
| [Features](docs/features.md) | Detailed overview of supported capabilities |
| [Methodology](docs/methodology.md) | End-to-end processing and analysis methodology |
| [Example Queries](examples/README.md) | Example natural-language queries supported by SatQuery |

---

## 📸 Demonstrations

The repository contains demonstrations of the major SatQuery AI analysis capabilities.

| Demo | Description |
|---|---|
| [VQA](demo/vqa/vqa.md) | Vision-language question answering over satellite imagery |
| [NDVI](demo/ndvi/ndvi.md) | Multispectral NDVI calculation and threshold analysis |
| [Temporal Analysis](demo/temporal-analysis/temporal-analysis.md) | Comparison of imagery across different dates |
| [Spatial Grounding](demo/grounding/grounding.md) | Object localization and segmentation |
| [Optical + SAR Fusion](demo/sar-optical-fusion/sar-optical-fusion.md) | Joint analysis of optical and SAR imagery |

---

## 📄 Technical Documentation

Additional technical documentation and project material is available in the [`documentation/`](documentation/) directory.

### Technical

- [SatQuery AI — System Use Flows](documentation/technical/SatQuery_AI_System_Use_Flows.pdf)
- [SatQuery — Vertical Workflows](documentation/technical/SatQuery-vertical-workflows.pdf)

### Presentation

- [SatQuery AI — TeamSN Presentation](documentation/presentation/SATQueryAI%20-%20TeamSN.pdf)
- [SatQuery AI — TeamSN Presentation Source](documentation/presentation/SATQueryAI%20-%20TeamSN.pptx)

---

## 🏆 Hackathon

SatQuery AI was developed as a solution for the **Smart India Hackathon (SIH)**.

**Team:** TeamSN  
**Problem Statement:** SIH26167

---

## 👥 Team

**Team SatQuery / TeamSN**

1. **Ritik Kumar Sharma** — Team Lead
2. **Saishreek Singh** — Lead Developer
3. **Apoorv Jha** — Co-Developer
4. **Pratham Sengar** — Lead Researcher
5. **Jiya Yadav** — Researcher
6. **Noel David** — Presenter

---
## Repository Structure

SatQuery is maintained across two repositories:

Public Research & Showcase Repository
Architecture, methodology, demonstrations, evaluation summaries, technical documentation and project materials.

Development Repository
Internal implementation containing the application stack, model experiments, grounding pipeline, geospatial processing, routing, evaluation, tests and research artifacts.

---

## 📌 Project Status

✅ **Developed**

SatQuery AI has been developed with functional analysis workflows covering visual question answering, NDVI analysis, temporal analysis, spatial grounding, optical-SAR analysis, and specialized visual counting.

The repository contains the project's architecture, methodology, demonstrations, example queries, and technical documentation.

---

## 📄 Usage

This repository contains project documentation, architecture diagrams, demonstrations, example queries, and technical showcase material for SatQuery AI.

© 2026 TeamSN. All rights reserved.

The materials in this repository may not be reproduced, modified, redistributed, or used commercially without prior permission from TeamSN.

## 📄 License

License information will be added when the project's distribution terms are finalized.
