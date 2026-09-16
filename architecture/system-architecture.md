# SatQuery AI — System Architecture

SatQuery AI uses an **agentic multimodal architecture** that combines a vision-language model with specialized remote-sensing analysis tools.

## Architecture Overview

The system follows a pipeline from natural-language user queries to specialized analysis and evidence-backed results:

**User Input → Input Processing → Agentic Router → Specialized Tools → Evidence Layer → User Interface**

### 1. User Input

Users upload satellite imagery and ask questions in natural language. SatQuery supports optical, multispectral, and SAR imagery, including multi-date inputs where required by the analysis.

### 2. Input Processing & Context Extraction

The system validates and preprocesses the supplied imagery, extracts relevant metadata and determines the available data type, temporal context, and task requirements.

### 3. Agentic Router

The **agentic router** interprets the user's request and determines which specialized capability should handle it.

Depending on the query, the system can route requests to:

- **VQA** — visual question answering and scene understanding
- **NDVI Analysis** — vegetation and spectral analysis using calibrated imagery
- **SAR Fusion / Analysis** — analysis involving radar imagery alongside optical data
- **Temporal Analysis** — comparison and change analysis across multiple dates
- **Grounding** — locating and referencing relevant regions or objects in imagery
- **Baseball Counting** — specialized counting workflow with validation checks

This routing layer allows SatQuery to use the appropriate tool instead of relying on a single model for every task.

### 4. Models & Tools

The system combines:

- **Remote-sensing Vision-Language Model**
- **LoRA / PEFT adaptation**
- **PyTorch & Hugging Face Transformers**
- **Geospatial / raster processing**
- **FastAPI backend**
- **Specialized analysis tools**

The architecture separates semantic visual reasoning from task-specific computational processing.

### 5. Evidence Layer

Results are passed through an evidence layer that collects and presents supporting information such as:

- Model-generated answers
- Visual overlays and highlighted regions
- Quantitative measurements
- Geospatial metadata
- Downloadable outputs
- Execution and tool-selection records

This makes the output more interpretable and auditable.

### 6. User Interface

The final result is presented through the SatQuery web application, allowing users to inspect the answer, supporting visual evidence, measurements, and execution details.

## Design Principle

> **Use the right specialist for the right remote-sensing task, while keeping the reasoning and resulting evidence inspectable.**

The architecture is modular, allowing additional analysis capabilities to be integrated without redesigning the complete system.
