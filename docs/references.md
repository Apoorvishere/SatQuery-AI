# SatQuery AI — References

SatQuery AI builds on existing research in remote-sensing vision-language models, multimodal reasoning, agentic tool use, parameter-efficient adaptation, and temporal Earth-observation analysis.

## Remote-Sensing Vision-Language Models

### GeoChat
**Kuckreja et al. — GeoChat: Grounded Large Vision-Language Model for Remote Sensing**

GeoChat provides a foundation for conversational interaction with remote-sensing imagery and demonstrates region-specific dialogue and visual grounding.

- CVPR 2024
- https://openaccess.thecvf.com/content/CVPR2024/html/Kuckreja_Grounded_Large_Vision-Language_Model_for_Remote_Sensing_CVPR_2024_paper.html
- https://github.com/mbzuai-oryx/GeoChat

### RemoteCLIP

A vision-language foundation model specifically developed for remote-sensing imagery.

- https://arxiv.org/abs/2306.11029

### EarthVQA

A remote-sensing VQA benchmark focused on relational reasoning, counting, and Earth-scene analysis.

- AAAI 2024
- https://ojs.aaai.org/index.php/AAAI/article/view/28357

## Agentic Remote-Sensing Systems

### RS-Agent

**Automating Remote Sensing Tasks through Intelligent Agent**

RS-Agent uses an LLM controller to interpret a natural-language query and select appropriate remote-sensing tools and workflows.

- https://arxiv.org/abs/2406.07089

### REMSA

**An LLM Agent for Foundation Model Selection in Remote Sensing**

REMSA investigates agentic selection of suitable remote-sensing foundation models based on natural-language task requirements.

- https://arxiv.org/abs/2511.17442

### GeoPilot

**A Cross-Domain Tool-Augmented Vision-Language Framework for Remote Sensing Image Understanding**

GeoPilot explores tool-augmented multimodal remote-sensing analysis, including optical and SAR imagery and autonomous tool invocation.

- Remote Sensing, 2026
- https://doi.org/10.3390/rs18101613

## Temporal Earth Observation

### TEOChat

**A Large Vision-Language Assistant for Temporal Earth Observation Data**

TEOChat explores conversational reasoning over multi-date Earth-observation imagery, including change and temporal scene analysis.

- ICLR 2025
- https://arxiv.org/abs/2410.06234

## Parameter-Efficient Adaptation

### LoRA

**Hu et al. — LoRA: Low-Rank Adaptation of Large Language Models**

SatQuery's parameter-efficient adaptation approach follows the LoRA principle of training lightweight low-rank parameters while keeping most pretrained model parameters frozen.

- https://arxiv.org/abs/2106.09685

## AdaptLLM

SatQuery uses **AdaptLLM Remote-Sensing Qwen2-VL-2B-Instruct** as its remote-sensing VLM starting point.

- Model: https://huggingface.co/AdaptLLM/remote-sensing-Qwen2-VL-2B-Instruct
- Remote-sensing visual-instruction dataset: https://huggingface.co/datasets/AdaptLLM/remote-sensing-visual-instructions
- Research: https://arxiv.org/abs/2411.19930

## Related Research

Additional research relevant to SatQuery includes:

- Change-Agent — https://arxiv.org/abs/2403.19646
- Decoding the Delta — https://arxiv.org/abs/2604.14044
- RingMo-Agent — https://arxiv.org/abs/2507.20776
- Prior-guided Fusion of Multimodal Features for Change Detection from Optical-SAR Images — https://arxiv.org/abs/2604.05527
- Visual Reasoning Agent (VRA) — https://arxiv.org/abs/2509.16343
- VICoT-Agent — https://arxiv.org/abs/2511.20085
- GeoEyes — https://arxiv.org/abs/2602.14201
- Agentic AI in Remote Sensing: Foundations, Taxonomy, and Emerging Systems — https://arxiv.org/abs/2601.01891

---

## Acknowledgement

SatQuery AI builds on the broader research community's work in remote sensing, vision-language models, agentic systems, and parameter-efficient model adaptation.

This repository does not claim ownership of the underlying research models or methods referenced above.
