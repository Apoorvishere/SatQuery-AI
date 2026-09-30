# SatQuery AI — Methodology

## Overview

SatQuery AI combines vision-language understanding with specialized remote-sensing processing through an agentic workflow.

The system is designed to separate visual interpretation from task-specific computation. Instead of using a single model for every operation, SatQuery routes each request to the analysis method appropriate for the user's query and available imagery.

The overall workflow is:

**User Query + Input Imagery → Input Validation → Agentic Routing → Specialist Analysis → Evidence Generation → Result Delivery**

---

## 1. User Query

The workflow begins with a natural-language query from the user describing the analysis they want to perform.

The query provides the semantic intent that SatQuery uses to determine which capability should handle the request.

Examples include:

- Asking questions about objects or features visible in an image
- Requesting an NDVI calculation
- Comparing imagery acquired on different dates
- Asking for changes between two observations
- Identifying a particular object or region
- Requesting analysis using optical and SAR imagery
- Counting visible objects in a supported scene

The query is therefore not treated simply as text input to a single model. It acts as the task description for the routing and analysis pipeline.

---

## 2. Input

The user provides the imagery required for the requested analysis.

Different SatQuery capabilities require different types of input.

For example:

- VQA can operate on a supported image and natural-language question.
- NDVI requires calibrated multispectral imagery containing the required Red and Near-Infrared bands.
- Temporal analysis requires imagery from different dates representing the same region.
- Optical-SAR workflows require compatible optical and radar observations.
- Grounding operates on an image together with a supported object category.

Where applicable, SatQuery also uses information contained in the input data, including:

- Image dimensions
- Spectral bands
- Acquisition dates
- Coordinate Reference System
- Spatial resolution
- Geographic bounds
- Pixel validity
- Sensor-specific information

Input requirements are checked before the corresponding specialist is executed.

---

## 3. Input Validation

Before analysis begins, SatQuery verifies whether the supplied data is compatible with the requested operation.

Validation requirements depend on the selected workflow.

For geospatial workflows, this can include checking:

- Required bands
- Raster dimensions
- Geospatial metadata
- Coordinate Reference System
- Acquisition dates
- Image alignment
- Valid pixel information
- Required sensor inputs

If the supplied data cannot support the requested operation, the system can stop the workflow and explain the incompatibility instead of producing an unsupported result.

This validation step is particularly important for quantitative remote-sensing analysis, where incorrect inputs can directly affect the resulting measurements.

---

## 4. Agentic Routing

SatQuery uses a routing layer to determine which specialist should process the request.

The routing process considers the user's query together with the available input and selects the appropriate analysis path.

Supported analysis paths include:

- Vision-Language Question Answering
- NDVI / Spectral Analysis
- Temporal Analysis
- Optical-SAR Analysis
- Grounding
- Specialized Visual Counting

The purpose of routing is to avoid sending every request through the same model.

For example, a question requiring a numerical NDVI measurement is routed to the spectral-analysis pipeline rather than asking the vision-language model to estimate the value.

Similarly, a request involving compatible optical and SAR imagery can be routed to the corresponding multimodal workflow.

Grounding currently remains an experimental manual workflow rather than a general-purpose automatically routed capability.

---

## 5. Vision-Language Processing

For visual reasoning tasks, SatQuery uses a remote-sensing Vision-Language Model based on Qwen2-VL.

The current VQA workflow uses an AdaptLLM remote-sensing Qwen2-VL-2B-Instruct model, with parameter-efficient adaptation through LoRA / PEFT where applicable.

The VLM is used for tasks that require visual interpretation and natural-language reasoning over remote-sensing imagery.

These include:

- Visual Question Answering
- Scene description
- Object identification
- Visual interpretation
- Specialized visual counting

The model receives the supported image and user query and produces a natural-language response.

VLM outputs are treated as model-generated interpretations rather than calibrated measurements. Visual counts and descriptions can therefore contain errors, particularly when objects are partially visible, ambiguous, or outside the supported task domain.

---

## 6. Geospatial Processing

SatQuery uses dedicated geospatial and numerical processing for operations that require quantitative or spatial computation.

Raster data and associated metadata are processed using geospatial tooling such as Rasterio, while numerical array operations are performed using NumPy and other specialized processing components.

Depending on the workflow, the processing layer can use:

- Raster bands
- Coordinate Reference Systems
- Geographic bounds
- Spatial resolution
- Pixel validity
- NoData information
- Image alignment
- Acquisition dates
- Spatial-area calculations

This processing layer allows quantitative operations to be performed directly on the underlying imagery rather than being estimated by the vision-language model.

---

## 7. Specialized Analysis

### 7.1 NDVI / Spectral Analysis

NDVI is calculated directly from the Near-Infrared and Red spectral bands:

**NDVI = (NIR − Red) / (NIR + Red)**

The resulting NDVI values can then be evaluated against a user-selected threshold.

The workflow can produce:

- NDVI raster values
- Threshold masks
- Threshold coverage
- Valid-pixel statistics
- Evidence overlays
- Spatial-area calculations
- Geospatial metadata
- Structured output data

The threshold coverage represents the proportion of valid pixels satisfying the selected threshold.

It should not by itself be interpreted as a direct measurement of vegetation health.

---

### 7.2 Temporal Analysis

Temporal analysis compares observations of the same region acquired at different dates.

The workflow first verifies the available temporal inputs and performs the required preparation before running the change-analysis model.

The resulting analysis can include:

- Before imagery
- After imagery
- Change masks
- Change overlays
- Vegetation / NDVI changes
- Water-candidate changes
- Gained pixels
- Lost pixels
- Common pixels
- Model scores
- Acquisition-date information

The resulting change masks and statistics provide evidence of differences between the observations.

The interpretation produced by the system should be treated as model-based analysis rather than automatically assuming that every detected difference represents a specific real-world event.

---

### 7.3 Optical-SAR Analysis

Optical and Synthetic Aperture Radar (SAR) imagery provide complementary information about the same geographic region.

SatQuery supports paired optical-SAR workflows for specific remote-sensing analysis tasks.

The current workflows include:

- Water analysis
- Scene-level land-cover classification

For water analysis, the system can generate and compare:

- SAR-only predictions
- Optical-only predictions
- Joint optical-SAR predictions
- Probability outputs
- Water masks
- Pixel counts
- Visual overlays

For land-cover analysis, the system produces scene-level classification scores and labels from:

- SAR input
- Optical input
- Joint optical-SAR input

These outputs are intended for supported analytical workflows and should not automatically be interpreted as guaranteed physical measurements or universally validated sensor improvements.

---

### 7.4 Spatial Grounding

Grounding connects a natural-language target to a spatial region within an image.

The experimental SatQuery grounding workflow uses a detection and segmentation pipeline based on Grounding DINO and Segment Anything.

The process consists of:

1. Generating candidate object proposals.
2. Filtering the detected proposals.
3. Selecting the relevant region.
4. Passing the selected region to the segmentation stage.
5. Producing a spatial mask.
6. Generating visual evidence for the detected region.

The resulting outputs can include:

- Bounding boxes
- Detection scores
- Segmentation masks
- Mask coverage
- Spatial outlines
- Processing-stage information

Grounding is currently considered an experimental capability with more limited remote-sensing validation than the core VQA and deterministic analytical workflows.

---

### 7.5 Specialized Visual Counting

SatQuery can perform visual counting for supported imagery and object types through its vision-language workflow.

The system interprets the scene and estimates the number of visible instances matching the user's question.

The result can be accompanied by a scene description and model information.

Because this capability relies on visual interpretation, the resulting count should be treated as a model-generated estimate rather than a surveyed or independently verified measurement.

---

## 8. Evidence Generation

A core part of the SatQuery methodology is generating evidence alongside the final result.

Rather than returning only a textual answer, the system can preserve intermediate and supporting information from the selected workflow.

Depending on the analysis type, evidence may include:

- Original input imagery
- Before-and-after imagery
- RGB visualizations
- False-colour visualizations
- Analysis overlays
- Binary masks
- Prediction masks
- Pixel statistics
- Threshold values
- Model outputs
- Processing stages
- Geospatial metadata
- Acquisition information
- Execution information
- Structured JSON results
- Downloadable raster artifacts

This creates a progressive evidence trail through which users can inspect how the result was produced.

---

## 9. Result Delivery

Once the selected specialist completes its analysis, SatQuery presents the result through the user interface.

The final output depends on the selected workflow and may contain:

- Natural-language answers
- Quantitative measurements
- Classification results
- Spatial masks
- Visual overlays
- Change visualizations
- Pixel statistics
- Geospatial information
- Model and processing details
- Downloadable analytical artifacts

The objective is to provide both the result and the information required to understand the basis of that result.

---

## 10. Separation of Reasoning and Measurement

A central methodological principle of SatQuery is the separation of semantic reasoning from deterministic measurement.

The vision-language model is used where the task requires interpretation of imagery and natural-language reasoning.

Specialized processing is used where the requested result can be calculated directly from the underlying data.

For example, when a user asks for a visual description, the VLM is appropriate.

When a user asks for NDVI threshold coverage, the system performs the calculation directly from the relevant spectral bands rather than asking the VLM to estimate the answer.

This separation helps ensure that quantitative operations are performed through explicit computational procedures while language-based interpretation remains handled by the vision-language workflow.

---

## 11. Local Execution

The current SatQuery prototype is designed for local execution.

The system consists of a browser-based interface connected to local Python services.

The application uses components including:

- HTML / CSS / JavaScript for the interface
- FastAPI for backend services
- Uvicorn for application serving
- PyTorch for model inference
- Rasterio for raster and geospatial processing
- NumPy for numerical computation

Depending on the workflow, processing can use local CPU or NVIDIA GPU resources.

The main application operates locally, while specialist workflows use the hardware resources required by their respective models and processing pipelines.

The active inference paths are designed to operate without relying on third-party inference APIs.

This local architecture allows imagery, processing, model inference, intermediate outputs, and analytical evidence to remain within the local SatQuery execution environment.
