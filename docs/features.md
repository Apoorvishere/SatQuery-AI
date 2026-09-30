# SatQuery AI — Features

SatQuery AI combines vision-language understanding with specialized
remote-sensing analysis through an agentic workflow.

Instead of forcing every request through a single model, SatQuery routes
different tasks to specialized capabilities based on the user's question,
the supplied imagery, and the requirements of the analysis.

## Vision-Language Question Answering

SatQuery can interpret remote-sensing and aerial imagery and answer
natural-language questions about the scene.

The vision-language workflow supports tasks such as:

- Scene description
- Visual question answering
- Object and feature identification
- Natural-language scene interpretation
- Visual counting

The vision-language model is adapted for the remote-sensing domain using
parameter-efficient fine-tuning.

For numerical or geospatial measurements, SatQuery can route the request to
a deterministic specialist rather than relying on the VLM to estimate the
value visually.

## Agentic Routing

SatQuery uses an agentic routing layer to determine which capability should
handle a user's request.

The router considers the task being requested and the characteristics of
the supplied imagery before selecting an appropriate specialist.

This allows vision-language reasoning and deterministic remote-sensing
analysis to operate as separate components within the same workflow.

The architecture and routing flow are documented in
[`system-architecture.md`](../architecture/system-architecture.md).

## NDVI / Spectral Analysis

SatQuery performs deterministic NDVI analysis using calibrated Red and
Near-Infrared (NIR) bands.

NDVI is calculated using:

$$
NDVI = \frac{NIR - Red}{NIR + Red}
$$

Users can specify an NDVI threshold and calculate the proportion of valid
pixels meeting or exceeding that threshold.

The workflow can produce:

- NDVI calculations
- Threshold-based analysis
- Pixel statistics
- Selected-area measurements
- NDVI evidence overlays
- Binary threshold masks
- Geospatial metadata
- Processing-stage visualizations
- Downloadable outputs

The resulting coverage represents pixels meeting the selected NDVI
threshold. It should not be interpreted by itself as a vegetation-health
assessment or field-survey measurement.

See the [NDVI demonstration](../demo/ndvi/ndvi.md) for an example.

## 🛰️ Optical and SAR Analysis

SatQuery supports analysis involving both optical and Synthetic Aperture
Radar (SAR) imagery.

The two modalities provide complementary information that can be incorporated
into specialized remote-sensing workflows.

### Water Analysis

SatQuery can perform optical-only, SAR-only, and joint optical-SAR water
analysis.

Outputs can include:

- Water predictions
- Joint water masks
- Water overlays
- Predicted water-pixel counts
- Valid-pixel coverage
- Individual modality results
- Joint analysis results

### Land-Cover Analysis

The paired optical-SAR workflow can also produce scene-level land-cover
predictions using information from both modalities.

These classifications are model outputs and should be interpreted as
predictions rather than direct measurements of geographic area.

See the [SAR + Optical Fusion Demo](../demo/sar-optical-fusion/sar-optical-fusion.md).

## Temporal Analysis

SatQuery can analyze imagery acquired at different points in time to
identify and quantify changes within a geographic region.

Temporal analysis can provide:

- Before/after imagery
- Change visualizations
- Vegetation and NDVI change analysis
- Water-candidate change analysis
- Gained and lost pixel statistics
- Common valid-pixel statistics
- Acquisition-date information
- Quantitative change measurements

The temporal workflow allows a scene to be analyzed as a sequence of
observations rather than as isolated images.

The demonstrated Varanasi workflow analyzes changes along a riverbank across
different observations and provides visual and quantitative evidence of the
observed changes.

See the [Temporal Analysis demonstration](../demo/temporal/temporal-analysis.md)
for an example.

## Spatial Grounding

SatQuery supports spatial grounding, allowing a natural-language query to be
associated with a specific object or region within imagery.

The experimental grounding workflow can produce:

- Object proposals
- Proposed regions
- Predicted instances
- Spatial outlines
- Segmentation masks
- Detector scores
- Segmentation metrics

Grounding provides a visual representation of where the requested feature
was identified rather than returning only a textual response.

Grounding outputs are model predictions and are not automatically treated as
independently verified object identities.

See the [Grounding demonstration](../demo/grounding/grounding.md) for an
example.

## Specialized Visual Counting

SatQuery includes visual counting workflows for supported scenes.

For example, the VQA workflow can identify and count visible
baseball/softball diamonds within an aerial image and provide a corresponding
scene description.

The system communicates the result as a model estimate when objects may be
partially visible or obscured rather than presenting the count as
independently verified object detection.

See the [VQA demonstration](../demo/vqa/vqa.md) for an example.

## Evidence and Auditability

SatQuery is designed to preserve supporting information alongside analysis
results.

Depending on the capability, evidence can include:

- Visual overlays
- Before/after imagery
- Pixel-level statistics
- Thresholds and analysis parameters
- Geospatial metadata
- Acquisition information
- Processing stages
- Execution details
- Model outputs
- Downloadable artifacts
- Structured run records

This evidence-oriented approach allows users to inspect the inputs,
intermediate outputs, parameters, and results associated with an analysis
rather than relying only on a final textual answer.

## Modular Analysis Specialists

Each analysis capability is implemented as a specialist within the larger
SatQuery workflow.

This modular structure allows individual capabilities to be developed,
evaluated, and improved independently while maintaining a consistent
workflow across the system.

The current capability set combines vision-language reasoning with
specialized remote-sensing operations, including:

- Vision-Language Question Answering
- Agentic Routing
- NDVI / Spectral Analysis
- Optical and SAR Analysis
- Temporal Analysis
- Spatial Grounding
- Specialized Visual Counting
- Evidence and Auditability

The implementation status and limitations of individual capabilities may
differ. Experimental workflows are identified as such in their respective
documentation and demonstrations.
