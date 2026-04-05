# AISEHack Phase 2 – Pollution Forecasting (IITD)

## Team: Tamilrockers.tn

**Domain:** Pollution Prediction
---

## Problem Statement

Forecast PM2.5 concentrations over India using a 10-hour historical window and predict the next 16 hours. The challenge emphasizes both global accuracy and episodic (extreme pollution) performance.
---

## Approach

We model the task as a **spatio-temporal forecasting problem** using a **UNet-based CNN**.

### Key Techniques

* Residual learning (predict delta over last timestep)
* Custom SMAPE loss with peak weighting
* Sliding window sampling (26-hour sequences)
* Fully reproducible Kaggle pipeline
---

## Pipeline

```
Raw Data → Normalize → Windowing → UNet Training  
→ Prediction → Residual Add → Denormalize → preds.npy
```
---

## Performance

* Validation loss improved: **0.22 → 0.18**
* Stable convergence
* Successfully generated valid competition submission
---

## Limitations

* Slight smoothing of extreme pollution spikes
* No explicit physics-based modeling
* Implicit feature interactions
---

## Dataset

* Source: WRF-Chem simulation
* Grid: 140 × 124
* Temporal: Hourly
* Features: PM2.5 + meteorological variables
---

## Submission Format

* File: `preds.npy`
* Shape: `(218, 140, 124, 16)`
* Generated fully inside Kaggle notebook
---

## GenAI Usage

AI tools were used for:

* Architecture refinement (UNet tuning)
* Loss function design
* Debugging tensor issues
* Training optimization
---

##  Report

See full report:
`/report/AISEHack_Final_2Page_Report.pdf`
---

##  License

This project follows the **ANRF Open License**.
---

## Notebook

Kaggle Notebook / Colab: *(add your link here)*
---

## Future Work

* Hybrid models (FNO + CNN)
* Better episodic modeling
* Physics-informed learning

---
