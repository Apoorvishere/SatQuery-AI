# SatQuery AI — Example Queries

SatQuery AI allows users to interact with remote-sensing imagery through natural-language queries, with the system routing each request to the appropriate analysis capability.

## 🧠 Visual Question Answering

Ask questions about objects, scenes, and visual content in satellite imagery.

Example:

> What is visible in this image?

> What are the main features of this scene?

> Is this area predominantly urban or rural?

> How many visible structures are present in the image?

> Describe the landscape shown in the image.

## 🌱 NDVI Analysis

Use multispectral imagery to calculate vegetation-related measurements and identify areas above a selected NDVI threshold.

Example:

> Calculate the NDVI for this image.

> What percentage of valid pixels have an NDVI greater than 0.50?

> How much area satisfies the selected NDVI threshold?

> Show the areas where NDVI exceeds 0.50.

> Generate an NDVI map for this scene.

## 🕒 Temporal Analysis

Compare imagery from different dates to identify and analyze visible changes over time.

Example:

> What changed between these two images?

> Identify the major changes between the two dates.

> Which areas show visible change over time?

> Has the area around this road changed between the two dates?

> Compare the two images and highlight the regions that changed.

## 📍 Spatial Grounding

Locate and highlight a requested object or region within satellite imagery.

Example:

> Where is the stadium in this image?

> Locate the requested object in the image.

> Outline the stadium.

> Identify the region associated with the query.

> Highlight the relevant object in the image.

## 🛰️ Optical + SAR Analysis

Combine optical and SAR imagery to analyze information that may not be apparent from a single modality.

Example:

> Compare the information visible in the optical and SAR imagery.

> What additional information does the SAR image provide?

> Analyze this scene using both optical and SAR imagery.

> Identify areas of water using the available optical and SAR imagery.

> What areas are identified as water by both modalities?

> Classify the scene using the optical and SAR inputs.

## ⚾ Specialized Visual Counting

Ask targeted counting questions about objects or structures visible in remote-sensing imagery.

Example:

> How many baseball or softball fields are visible in this image?

> How many visible fields are present in the scene?

> Count the identifiable objects in the image.

## 🔎 Evidence-Oriented Queries

Request the measurements, processing details, and visual evidence associated with an analysis.

Example:

> What evidence supports this result?

> What data and processing were used to produce this answer?

> Show the relevant region and analysis details.

> What measurements were used to generate this result?

> Show the analysis evidence for this result.

---

## Example Workflow

```text
Upload imagery
      ↓
Ask a question in natural language
      ↓
Agentic routing
      ↓
Appropriate specialist selected
      ↓
Analysis performed
      ↓
Evidence and measurements generated
      ↓
Result displayed to the user
