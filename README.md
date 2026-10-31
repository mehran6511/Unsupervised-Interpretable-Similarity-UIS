# [Unsupervised Interpretable Similarity (UIS): A zero-shot framework and benchmark for patent landscaping and technology mapping](https://doi.org/10.1016/j.wpi.2026.102514)

This repository provides the evaluation framework and comparative benchmarking tools for assessing AI patent classification pipelines. It benchmarks our **UIS Pipeline** against the baseline **AIPD 2023** dataset using clean LLM-annotated patent ground truths.

---

## 📌 Overview

The benchmark evaluates how accurately different models estimate patent AI relevance across overall patent ratings and 8 targeted AI subdomains:
- **ML** (Machine Learning)
- **Vision** (Computer Vision)
- **NLP** (Natural Language Processing)
- **Speech** (Speech Recognition & Audio Processing)
- **EVO** (Evolutionary Computation)
- **Hardware** (AI Hardware & Acceleration)
- **KR** (Knowledge Representation & Reasoning)
- **Planning** (Planning & Control)

### Key Metrics
- **Brier Calibration Score**: Assesses the reliability and probabilistic calibration of continuous score predictions against ground truth labels (lower values denote superior calibration).
- **Threshold-Dependent Metrics**: Precision, Recall, and $F_1$-score evaluated across varying decision boundaries ($\tau \in [0.2, 0.8]$).

---

### Dependencies
Install the required analytical and plotting libraries:

```text
numpy>=1.22.0
pandas>=1.4.0
matplotlib>=3.5.0
scipy>=1.8.0
scikit-learn>=1.0.0
```

## 📊 Summary of Benchmark Results

| Model / Subdomain | Mean Brier Score (↓) | F1 @ $\tau=0.4$ (Overall) | Hardware F1 | Planning F1 | NLP F1 |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **AIPD 2023** | 0.102 | 0.704 | 0.663 | 0.613 | 0.513 |
| **UIS Pipeline (Ours)** | **0.036** | **0.747** | **0.680** | 0.399 | **0.531** |

*Key takeaway:* The UIS pipeline reduces overall calibration error by **over 60%** while significantly suppressing false positives at higher decision thresholds relative to AIPD 2023.

```
Distributed under the MIT License.
