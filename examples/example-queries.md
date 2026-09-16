# SatQuery AI — Example Queries

SatQuery AI is designed to let users interact with remote-sensing imagery using natural-language questions.

## 🧠 Visual Question Answering

Example:

> What is visible in this image?

> Is this area predominantly urban or rural?

> Describe the main features of this scene.

## 🌱 NDVI Analysis

Example:

> Calculate the NDVI for this image.

> What percentage of the area has NDVI greater than 0.50?

> How much area satisfies the selected NDVI threshold?

## 🕒 Temporal Analysis

Example:

> What changed between these two images?

> Identify the major changes between the two dates.

> Which areas show visible change over time?

## 📍 Grounding

Example:

> Where is the requested object or region located?

> Identify the relevant region in the image.

> Highlight the area associated with the query.

## 🛰️ Optical + SAR Analysis

Example:

> Compare the information visible in the optical and SAR imagery.

> What additional information does the SAR image provide?

> Analyze this scene using both modalities.

## ⚾ Specialized Counting

Example:

> How many baseball fields are visible in this image?

## 🔎 Evidence-Oriented Queries

Example:

> Show the evidence supporting this result.

> What data and processing were used to produce this answer?

> Show the relevant region and analysis details.

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
Evidence generated
      ↓
Result displayed to the user
