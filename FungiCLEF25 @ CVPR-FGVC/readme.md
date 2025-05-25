![image](https://github.com/user-attachments/assets/aef02ca9-ed24-425e-b27e-1ed5e489a9d4)

## Overview
The FungiCLEF Challenge focuses on few-shot recognition of fungi species using real-world observational data. Each observation includes multiple photographs of the same specimen, along with metadata (e.g., location, timestamp, substrate, habitat, toxicity), satellite imagery, and meteorological variables.

The goal is to develop a classification model that returns a ranked list of predicted species for each observation. A key challenge lies in handling a large number of species consisting of rare and under-recorded taxa with very few training examples.

## Challenge Details
- **Input:** List of fungi observations with images and metadata.
- **Output:** Top-k ranked predicted fungi species per observation.
- **Evaluation Metric:** Recall@5 (proportion of true labels in top 5 predictions).
- **Submission:** Top 10 species predictions required per observation.

## Motivation
Automatic fungi recognition helps mycologists, citizen scientists, and nature enthusiasts identify species in the wild and supports biodiversity data collection. Rare species and limited examples make this task particularly challenging.

## Evaluation Metric
Recall@k is defined as:
Recall@k = (1/N) * sum_{i=1}^N 1{y_i ∈ Ŷ_{i,k}}

Where:
- N = total samples,
- y_i = true label of sample i,
- Ŷ_{i,k} = top-k predicted labels for sample i,
- 1{} is indicator function.

We use k=5 for evaluation; however, submissions require top 10 predictions.

## Submission Format
- CSV with columns: observationId, predictions
- observationId: integer
- predictions: space-separated list of 10 species IDs

