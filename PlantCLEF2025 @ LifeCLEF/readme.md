# PlantCLEF 2025 - Vegetation Quadrat Species Identification Challenge

## Overview
This challenge focuses on identifying all plant species present in high-resolution images of vegetation plots defined by quadrats—rectangular frames marking a specific ground area for sampling. The task involves multi-label classification of species within each quadrat image, addressing challenges related to fine-grained plant classification and environmental variability.

## Background
Vegetation plot inventories are essential in ecological research for biodiversity assessment, long-term monitoring, and large-scale environmental surveys. Botanists identify all plant species within small quadrats (~0.5 m²) and measure species abundance through biomass, ecological scores, or area coverage.

Integrating AI into this process promises to enhance efficiency and enable broader ecological studies with less expert input. However, building robust models is challenging due to the multi-label nature and domain shift between training data (individual plant images) and test data (multi-species quadrat images).

## Challenge Description
- **Training data:** Single-label images of individual plant species.
- **Test data:** Multi-label, high-resolution quadrat images containing multiple species.
- **Goal:** Predict all plant species present in each quadrat image.
- **Main challenge:** Overcoming the domain shift between individual plant images and multi-species quadrat images.

  ![image](https://github.com/user-attachments/assets/f0802139-5ae6-4f3b-b4d9-68fe7459ccd5)


## Evaluation Metric
- The primary metric is the **macro-averaged F1 score per sample** (each quadrat image), balancing precision and recall.
- Scores are averaged first per transect (a linear sampling area composed of multiple quadrats) and then across all transects to reduce spatial bias.
- The F1 score is computed based on:
  - True Positives (correct species predicted)
  - False Positives (incorrect species predicted)
  - False Negatives (species missed)
  
For detailed formulas and methodology, see the [scikit-learn F1 score documentation](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html).

## Submission Format
- Submit a CSV file with two columns: `quadrat_id` and `species_ids`.
- `species_ids` must be a **list enclosed in double square brackets**, e.g., `"[1395806]"` or `"[1351284, 1494911, 1381367]"`.
- Use comma separators, quotes around all fields, and include a header row.



