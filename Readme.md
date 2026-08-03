# Longitudinal Biomarkers & Multi-Modal ML for Alzheimer's Progression

An end-to-end longitudinal health data science pipeline evaluating genetic risk ($APOE\ \epsilon4$), baseline neuroimaging biomarkers (MRI), and 24-month cognitive trajectories ($MMSE$) using Cox Proportional Hazards and Random Survival Forests.

---

## 📌 Project Overview

Longitudinal cohort studies (such as MAS and ADNI) require models that account for both static baseline risk factors and dynamic, time-varying cognitive decline trajectories. This project analyzes a cohort of 500 patient profiles across 24-month follow-up waves to:

1. **Map Longitudinal Trajectories:** Track MMSE cognitive trajectories across study waves stratified by $APOE\ \epsilon4$ genetic carrier status.
2. **Feature Engineering:** Derive rate-of-decline slopes ($\Delta \text{MMSE} / \Delta t$) alongside baseline structural MRI volumes (hippocampus and ventricles).
3. **Statistical Survival Modeling:** Derive multivariable hazard ratios ($\text{HR}$) for genetic and imaging biomarkers.
4. **Ensemble ML & SHAP Interpretability:** Train a tuned Random Survival Forest evaluated via 5-fold cross-validation to isolate multi-modal risk drivers.

---

## 🛠️ Tech Stack & Dependencies

* **Language:** Python 3.x
* **Environment:** Google Colab / Jupyter Notebook
* **Key Libraries:**
  * `pandas`, `numpy` – Longitudinal data manipulation & feature engineering
  * `lifelines` – Cox Proportional Hazards modeling & statistical inference
  * `scikit-survival` – Non-linear Random Survival Forests (RSF)
  * `scikit-learn` – Hyperparameter optimization (`GridSearchCV`, 5-fold CV)
  * `shap` – Model explainability & feature attributions
  * `matplotlib`, `seaborn` – Longitudinal trajectory plots

---

## 📊 Key Findings & Model Performance

### Model Comparison Benchmark

| Model Architecture | Validation Strategy | Concordance Index (C-Index) | Key Findings |
| :--- | :--- | :---: | :--- |
| **Cox Proportional Hazards** | Baseline Cohort | **0.728** | Identifies significant hazard ratios for $APOE\ \epsilon4$ and Hippocampal Volume ($p < 0.01$). |
| **Tuned Random Survival Forest** | 5-Fold Cross-Validation | **0.755** | Captures non-linear interaction between $APOE\ \epsilon4$ and 24-month cognitive decline rate. |

* **Optimal RSF Parameters:** `max_depth: 8`, `min_samples_leaf: 10`, `n_estimators: 50`.
* **SHAP Risk Ranking:** $APOE\ \epsilon4$ allele count demonstrated the highest overall feature attribution, followed by baseline hippocampal volume and the 24-month MMSE decline slope.

---

## 🚀 How to Run

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/Longitudinal_Biomarkers_ADNI_ML.git](https://github.com/YOUR_USERNAME/Longitudinal_Biomarkers_ADNI_ML.git)
   cd Longitudinal_Biomarkers_ADNI_ML
