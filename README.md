# Bow Echo Movement Nowcasting: A STEPS Model & X-Band Radar Approach

This repository provides a comprehensive Python framework for tracking and predicting the movement of **Bow Echoes** (Mesoscale Convective Systems) in the Bandung Basin. By utilizing high-resolution **X-Band Radar** data and the **STEPS (Short-Term Ensemble Prediction System)** library, this project achieves high-precision short-term weather forecasting.

## Project Overview
The Bandung Basin's complex topography often leads to localized extreme weather. This project implements a nowcasting pipeline to mitigate risks by identifying and predicting the trajectory of convective systems using a structured 5-step methodology, from raw data ingestion to performance verification.

## Key Results & Performance
- **Detection Accuracy:** High identification reliability with a **POD of 0.685**.
- **Model Reliability:** Maintains a **Critical Success Index (CSI) > 0.5** for lead times up to 30 minutes.
- **Optimal Lead Time:** Proven effectiveness in the 10–30 minute window, with a mean position error of only **4.45 km** at the 10-minute mark.
- **Error Analysis:** Robust verification pipeline calculating RMSE to ensure forecast skill against actual observations.

## Execution Flow (Pipeline)
The analysis is divided into a sequential 5-step pipeline:

1. **Observation Plotting:** Ingesting and plotting the raw X-Band radar data to visualize the actual meteorological conditions.
2. **Skeletonization:** Applying morphological skeletonization directly to the raw data to extract the structural "backbone" of the bow echo.
3. **Nowcasting:** Utilizing the STEPS framework on the raw data to generate predictive forecast fields (nowcasts) for future time steps.
4. **Shape Matching:** Aligning and comparing the structural geometries extracted from the observation plots against the nowcast predictions.
5. **Verification:** Calculating the forecast accuracy (e.g., RMSE) based on the matched shapes to rigorously evaluate the model's performance.

## Repository Structure
To match the execution flow, the scripts are organized as follows:

```text
├── data/           # Sample radar datasets 
├── scripts/        # Core pipeline scripts
│   ├── 01_plot_obs.py
│   ├── 02_skeletonization.py
│   ├── 03_nowcast_steps.py
│   ├── 04_shape_match.py
│   └── 05_verification.py
├── outputs/        # Generated plots (Observations, Nowcasts, and Matched Shapes)
├── docs/           # Research paper & Methodology documentation
├── requirements.txt# Project dependencies
└── README.md       # Project documentation
```

## Technical Implementation
The implementation is built on a robust Python stack:
- pysteps: Core engine for motion field estimation and extrapolation forecasting.
- OpenCV / Scikit-Image: For morphological skeletonization and shape matching.
- NumPy & Pandas: Multi-dimensional array manipulation of radar reflectivity.
- Matplotlib: Custom visualization workflows.

## Getting Started
1. Clone the repository:
```DAX
git clone [https://github.com/your-username/repository-name.git](https://github.com/your-username/repository-name.git)
```
2. Install dependencies:
```DAX
pip install -r requirements.txt
```
3. Run the scripts sequentially as numbered in the scripts/ directory.

## Developed as part of a Meteorology research project.
