# Pre-to-Post Prediction Refinement (P2PR)

**Efficient multimodal inference through sample-wise routing and prediction refinement**

Master's thesis research at National Cheng Kung University.

> Source code is currently private due to thesis embargo requirements and third-party code licensing considerations.

## Overview

Multimodal models often improve prediction quality by combining information from multiple modalities, but executing the full multimodal pipeline for every input can be computationally expensive.

This research proposes **Pre-to-Post Prediction Refinement (P2PR)**, a two-stage inference framework that:

1. Produces a lower-cost **pre-prediction**.
2. Uses a lightweight, sample-wise routing mechanism to determine whether additional computation is necessary.
3. Selectively upgrades difficult samples to a stronger **post-prediction** path.
4. Reuses information from the pre-prediction stage to assist the final prediction instead of discarding it after routing.

The goal is to improve the trade-off between predictive performance and inference cost.

## My Contributions

My work focuses on the design and evaluation of **Pre-to-Post Prediction Refinement (P2PR)** on top of established multimodal prediction components.

- **Proposed the P2PR inference framework**, where a low-cost pre-prediction is used both for sample-wise routing and for assisting the final prediction after an upgrade.

- **Designed and implemented a validation-controlled routing pipeline** that determines whether each sample should remain on the low-cost path or be upgraded to a stronger multimodal prediction path.

- **Developed dataset-specific pre-assisted post-prediction refinement**, using controlled refinement strategies for CMU-MOSEI and MM-IMDB.

- **Implemented and evaluated multiple routing strategies** under the same two-stage framework, including learned, confidence-based, random, MLP-based, and attention-based routing.

- **Built a controlled experimental evaluation pipeline** including aligned comparisons with DynMM, post-assist ablations, multi-seed statistical testing, cost-performance analysis, and GPU-synchronized latency measurements.

- **Analyzed the difference between theoretical computation cost and real inference latency**, identifying operating regions where selective routing is beneficial as well as cases where cascade overhead limits practical speedup.

## Evaluation

The framework was evaluated on two multimodal tasks:

- **CMU-MOSEI** — multimodal sentiment prediction using text, audio, and visual information.
- **MM-IMDB** — multi-label movie genre classification using text and image information.

Experiments compare P2PR with dynamic multimodal inference baselines and alternative routing strategies across different computation budgets.

The results demonstrate that selective routing and prediction refinement can provide useful cost-performance trade-offs, while also highlighting the difference between theoretical operation counts and real execution latency.

## Results

P2PR was evaluated on **CMU-MOSEI** and **MM-IMDB** across multiple computation budgets.

The experiments show that:

- P2PR provides competitive or improved prediction quality compared with the DynMM baseline across the evaluated cost regions.
- Statistical analyses confirm significant improvements on selected primary metrics.
- Post-assist ablation experiments show that prediction refinement contributes beyond routing alone.
- Alternative routing strategies were evaluated under the same two-stage inference framework.
- GPU-synchronized latency measurements demonstrate that theoretical computation cost (MAdds) does not always translate directly to lower wall-clock latency.

The experiments also identify practical limitations of cascaded inference at high-computation operating points, where routing and sequential execution overhead may reduce or eliminate real-time speed advantages.

Detailed numerical results, tables, and experimental configurations are currently withheld due to the thesis embargo.

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
