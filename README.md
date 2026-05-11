# Bow Echo Movement Nowcasting: A STEPS Model & X-Band Radar Approach

This repository contains the analysis scripts and workflows for predicting the movement of **Bow Echoes** (Mesoscale Convective Systems) within the Bandung Basin. This project leverages the **STEPS (Short-Term Ensemble Prediction System)** model and high-resolution **X-Band Radar** data.

## Project Overview
The complex topography of the Bandung Basin makes it highly susceptible to extreme weather triggered by bow echo phenomena. This research establishes a **Python-based** workflow to evaluate short-term prediction (nowcasting) systems using historical radar data (2020-2022).

Key methodologies include:
1. **Morphological Identification:** Utilizing **Skeletonization** techniques to extract and identify the structural patterns of bow echoes from radar imagery.
2. **Motion Vectoring:** Implementing the **Lucas-Kanade Algorithm** (within the STEPS framework) to capture the direction and velocity of convective systems with high precision.

## Key Findings & Model Performance
- **Detection Accuracy:** The system achieved a high identification rate with a **Probability of Detection (POD) of 0.685**.
- **Optimal Lead Time:** Nowcast performance is most effective at a **10–30 minute lead time**, maintaining a Critical Success Index (CSI) > 0.5 and an average position deviation of only **4.45 km** in the first 10 minutes.
- **Case Study Performance:** Evaluation of the November 9, 2022 case (optimal conditions without attenuation) showed that the STEPS model maintains high accuracy for up to **+30 to 40 minutes**.
- **Model Decay:** Performance degradation typically occurs after the 40-minute mark due to the complex dynamics of storm cell growth and decay.

## Tech Stack & Libraries
- **Python:** Primary programming language.
- **STEPS / Pysteps:** For ensemble and deterministic nowcasting.
- **Computer Vision:** Image processing for skeletonization and feature extraction.
- **Data Science Suite:** `Pandas`, `NumPy`, and `Matplotlib` for data manipulation and visualization.

## Repository Structure
```text
├── data/           # (Contains sample_data.csv; raw radar data is restricted)
├── scripts/        # Python scripts for pre-processing, skeletonization, and STEPS modeling
├── outputs/        # Visualizations, radar plots, and movement analysis
├── docs/           # Final Thesis Paper/Publication
├── requirements.txt# List of Python dependencies
└── README.md       # Project documentation
```

## Getting Started
(Note: Due to privacy agreements, raw radar datasets are not public. However, the scripts can be tested using the provided sample_data.csv.)
