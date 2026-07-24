# Interpretable Machine Learning & Survival Analysis for Alzheimer's Diagnosis

An end-to-end clinical data science pipeline evaluating risk factors, feature importance, and diagnostic timing for Alzheimer's disease using interpretable machine learning and survival modeling techniques.

---

## 📌 Project Overview

Clinical decision-making requires models that are not only accurate but also **explainable**. This project analyzes a cohort of 2,149 patient records across 35 clinical, cognitive, and lifestyle features to:
1. Identify key drivers of an Alzheimer's diagnosis using **Random Forest** and **SHAP (SHapley Additive exPlanations)**.
2. Model disease onset and progression probability using **Kaplan-Meier Survival Analysis**.
3. Quantify feature hazard ratios over time using a **Cox Proportional Hazards Model**.

---

## 🛠️ Tech Stack & Dependencies

* **Language:** Python 3.x
* **Environment:** Google Colab / Jupyter Notebook
* **Key Libraries:**
  * `pandas`, `numpy` – Data manipulation & preprocessing
  * `scikit-learn` – Baseline modeling & train/test splitting
  * `shap` – Model interpretability & feature attributions
  * `lifelines` – Survival analysis & hazard estimation
  * `matplotlib`, `seaborn` – Data visualization

---

## 📊 Key Findings & Methodology

### 1. Interpretable Machine Learning (SHAP)
* **Top Clinical Predictors:** `FunctionalAssessment`, `ADL` (Activities of Daily Living), and `MMSE` (Mini-Mental State Examination) demonstrated the strongest overall impact on model output.
* **Directionality:** Lower scores on cognitive and functional assessments (`MMSE`, `ADL`) strongly increased the probability of an Alzheimer's diagnosis.
* **Complaints vs. Biomarkers:** Active memory complaints and behavioral symptoms provided sharper diagnostic signals than general cardiovascular or metabolic lifestyle markers (`BMI`, `Cholesterol`).

### 2. Non-Parametric Survival Analysis (Kaplan-Meier)
* Examined the cumulative probability of remaining diagnosis-free as a function of age.
* Observed a stable $1.0$ ($100\%$) probability prior to age 60, followed by a steady drop reflecting late-onset risk trajectories.

### 3. Cox Proportional Hazards Model
* **Cognitive Impact:** `MMSE` score emerged as a statistically significant predictor ($p < 0.005$, $z = -8.70$).
* **Hazard Ratio:** Every 1-point increase in `MMSE` reduced the relative hazard of an Alzheimer's diagnosis by **4%** ($\text{HR} = 0.96$).

---
