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

## Dataset

AerialLoc is built on the aerial photogrammetric point-cloud scenes of SensatUrban through georeferencing and spatial target sampling. Point-centered overhead imagery is used to support annotation, while the final benchmark pairs the sampled 3D locations with human-refined descriptions validated against the corresponding point-cloud scenes. In total, AerialLoc spans 38 aerial scenes across Birmingham and Cambridge, covering approximately 6 km², with 44,730 textual descriptions and 2,157 landmarks.
