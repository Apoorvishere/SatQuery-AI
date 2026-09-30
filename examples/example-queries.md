# SatQuery AI — Example Queries

SatQuery AI allows users to interact with remote-sensing imagery through natural-language queries. The system routes each request to the appropriate analysis capability.

## 🧠 Visual Question Answering

Ask questions about objects, scenes, and visual content in satellite imagery.

### Scene Understanding

> What is visible in this image?

> What are the main features of this scene?

> Is this area predominantly urban or rural?

> Describe the landscape shown in the image.

### Object Questions

> How many visible structures are present in the image?

> Is there a stadium in this scene?

> What type of facilities are visible in this area?

---

## 🌱 NDVI Analysis

Use multispectral imagery to calculate NDVI and identify areas that satisfy a selected vegetation threshold.

### NDVI Calculation

> Calculate the NDVI for this image.

> Generate an NDVI map for this scene.

> Show the areas where NDVI exceeds 0.50.

### Quantitative Analysis

> What percentage of valid pixels have an NDVI greater than 0.50?

> How much area satisfies the selected NDVI threshold?

> How many hectares of the image satisfy the selected NDVI threshold?

---

## 🕒 Temporal Analysis

Compare imagery from different dates to identify visible changes over time.

### Change Detection

> What changed between these two images?

> Identify the major changes between the two dates.

> Which areas show visible change over time?

> Compare the two images and highlight the regions that changed.

### Targeted Change Questions

> Has the area around this road changed between the two dates?

> Which regions show the most visible change?

> Are there visible changes around the buildings between these dates?

---

## 📍 Spatial Grounding

Locate and highlight a requested object or region within satellite imagery.

### Object Localization

> Where is the stadium in this image?

> Locate the requested object in the image.

> Identify the relevant region in the image.

### Grounding and Segmentation

> Outline the stadium.

> Highlight the area associated with the query.

> Show the region corresponding to the requested object.

---

## 🛰️ Optical + SAR Analysis

Analyze optical and SAR imagery together to extract information from both modalities.

### Multimodal Analysis

> Compare the information visible in the optical and SAR imagery.

> What additional information does the SAR image provide?

> Analyze this scene using both optical and SAR imagery.

### Water Analysis

> Identify areas of water using the available optical and SAR imagery.

> What areas are identified as water by both modalities?

> Compare the water detected in the optical and SAR imagery.

### Scene Analysis

> Classify the scene using the optical and SAR inputs.

> What does the combined optical and SAR analysis indicate?

---

## ⚾ Specialized Visual Counting

Ask targeted counting questions about objects or structures visible in remote-sensing imagery.

### Examples

> How many baseball or softball fields are visible in this image?

> How many visible fields are present in the scene?

> How many identifiable objects are visible in the image?

> Count the visible objects matching the requested category.

---

## 🔎 Evidence-Oriented Queries

Ask for the evidence, measurements, and processing details associated with an analysis.

### Evidence

> What evidence supports this result?

> Show the relevant region and analysis details.

> Show the visual evidence supporting this answer.

### Measurements and Processing

> What measurements were used to generate this result?

> What data and processing were used to produce this answer?

> Show the analysis details for this result.

> What processing steps were performed on the imagery?

---

## 🔄 Example Workflow

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
