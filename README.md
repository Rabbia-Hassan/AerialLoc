# AerialLoc: A Dataset and Benchmark for Language-Based 3D Position Localization in City-Scale Aerial Point Clouds

## Overview

AerialLoc introduces a dataset and benchmark for localizing 3D positions in city-scale aerial point clouds from natural-language descriptions of their surroundings. It pairs target positions with human-annotated descriptions that capture surrounding objects, landmarks, and spatial relationships. The benchmark supports global place recognition and fine localization, with a Benchmark Adaptation Pipeline that enables evaluation using existing coarse-to-fine localization models.

<p align="center">
  <img src="assets/overview.svg" width="85%">
</p>

<p align="center">
  <em>Conceptual overview of language-based 3D position localization in AerialLoc.</em>
</p>


## Dataset

AerialLoc is built on the aerial photogrammetric point-cloud scenes of SensatUrban through georeferencing and spatial target sampling. Point-centered overhead imagery is used to support annotation, while the final benchmark pairs the sampled 3D locations with human-refined descriptions validated against the corresponding point-cloud scenes. In total, AerialLoc spans 38 aerial scenes across Birmingham and Cambridge, covering approximately 6 km², with 44,730 textual descriptions and 2,157 landmarks.


### Representative Annotations

Representative final annotations from AerialLoc, showing point-centered aerial views and their corresponding human-refined descriptions.

<div align="center">
  <img src="assets/example_annotations.svg" width="80%">
</div>



## Dataset Download


The AerialLoc dataset can be downloaded from the given [download link](https://docs.google.com/forms/d/e/1FAIpQLScAu-up_UeIOYu0NTVjZVInO8PJTVkYu9q72pmJZFRdp52JRQ/viewform?usp=publish-editor).


## Benchmark Tasks and Baseline Results

AerialLoc evaluates language-based 3D position localization through two stages of a coarse-to-fine localization pipeline.

### Global Place Recognition
Given a natural-language query, the global place recognition stage retrieves the top-\(k\) candidate cells from the AerialLoc cell database. The objective is to identify the spatial cell associated with the target position among the retrieved candidates.

The Text2Loc baseline achieves the following Cell Retrieval Recall on the AerialLoc test split:

| **k** | **Cell Retrieval Recall@k (%) ↑** |
|---:|---:|
| 1  | 3.43 |
| 3  | 7.21 |
| 5  | 10.28 |
| 10 | 16.10 |





### Fine Localization

Given the retrieved candidate cells, the fine localization stage estimates the target position within each candidate cell using the textual query and the corresponding cell representation. These local predictions are mapped back to the scene-level coordinate frame to obtain the final position estimate.
