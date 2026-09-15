# Pre-to-Post Prediction Refinement (P2PR)

A research project on efficient multimodal inference through sample-wise routing and prediction refinement.

This repository provides a public overview of my Master's thesis research:

**A Pre-to-Post Prediction Refinement Approach for Enhancing Multimodal Inference Efficiency**

> Source code is currently kept private due to thesis embargo requirements and third-party code licensing considerations.

## Overview

Multimodal models often improve prediction quality by combining information from multiple modalities, but executing the full multimodal pipeline for every input can be computationally expensive.

This research proposes **Pre-to-Post Prediction Refinement (P2PR)**, a two-stage inference framework that:

1. Produces a lower-cost **pre-prediction**.
2. Uses a lightweight, sample-wise routing mechanism to determine whether additional computation is necessary.
3. Selectively upgrades difficult samples to a stronger **post-prediction** path.
4. Reuses information from the pre-prediction stage to assist the final prediction instead of discarding it after routing.

The goal is to improve the trade-off between predictive performance and inference cost.

## Key Contributions

- Designed a two-stage multimodal inference framework based on pre-prediction and selective post-prediction.
- Developed a sample-wise routing mechanism using information available before the expensive prediction path is executed.
- Introduced pre-assisted post-prediction refinement, allowing information from the inexpensive stage to contribute to the final upgraded prediction.
- Evaluated multiple routing strategies under a common inference framework.
- Conducted cost-performance, ablation, statistical significance, and real GPU latency analyses.

## Evaluation

The framework was evaluated on two multimodal tasks:

- **CMU-MOSEI** — multimodal sentiment prediction using text, audio, and visual information.
- **MM-IMDB** — multi-label movie genre classification using text and image information.

Experiments compare P2PR with dynamic multimodal inference baselines and alternative routing strategies across different computation budgets.

The results demonstrate that selective routing and prediction refinement can provide useful cost-performance trade-offs, while also highlighting the difference between theoretical operation counts and real execution latency.

## Research Context

This work builds upon and extends prior research and implementations including:

- [DynMM](https://github.com/zihuixue/DynMM)
- [MultiBench](https://github.com/pliang279/MultiBench)

The proposed P2PR framework, routing experiments, prediction-refinement methods, evaluation pipelines, ablation studies, statistical analyses, and latency experiments were developed as part of my Master's thesis research.

## Code Availability

The research implementation is currently **not publicly available** due to:

- Thesis publication embargo requirements.
- Licensing considerations associated with upstream research code.

A cleaned implementation may be released after the embargo period and after confirming the redistribution requirements of the upstream projects.

## Thesis

**Master's Thesis**  
A Pre-to-Post Prediction Refinement Approach for Enhancing Multimodal Inference Efficiency

National Cheng Kung University  
Institute of Computer Science and Information Engineering  
2026

## Status

Research completed. Public documentation may be expanded as additional materials become eligible for release.
