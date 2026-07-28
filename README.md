# Interpretable Machine Learning & Survival Analysis for Alzheimer's Diagnosis

An end-to-end clinical data science pipeline evaluating risk factors, feature importance, and diagnostic timing for Alzheimer's disease using interpretable machine learning and survival modeling techniques.

---

## 📌 Project Overview

Clinical decision-making requires models that are not only accurate but also **explainable**. This project analyzes a cohort of 2,149 patient records across 35 clinical, cognitive, and lifestyle features to:
1. Identify key drivers of an Alzheimer's diagnosis using **Random Forest** and **SHAP (SHapley Additive exPlanations)**.
2. Model disease onset and progression probability using **Kaplan-Meier Survival Analysis**.
3. Quantify feature hazard ratios over time using a **Cox Proportional Hazards Model**.
4. Predict non-linear, patient-specific survival curves using a tuned **Random Survival Forest (RSF)** evaluated with 5-fold cross-validation.

---

## 🛠️ Tech Stack & Dependencies

* **Language:** Python 3.x
* **Environment:** Google Colab / Jupyter Notebook
* **Key Libraries:**
  * `pandas`, `numpy` – Data manipulation & preprocessing
  * `scikit-learn` – Cross-validation (`GridSearchCV`, `KFold`) & evaluation
  * `shap` – Model interpretability & feature attributions
  * `lifelines` – Kaplan-Meier & Cox Proportional Hazards modeling
  * `scikit-survival` – Non-linear Random Survival Forests (RSF)
  * `matplotlib`, `seaborn` – Data visualization & comparison plots

---

## 📊 Key Findings & Methodology

### 1. Interpretable Machine Learning (SHAP)
* **Top Clinical Predictors:** `FunctionalAssessment`, `ADL` (Activities of Daily Living), and `MMSE` (Mini-Mental State Examination) demonstrated the strongest overall impact on model output.
* **Directionality:** Lower scores on cognitive and functional assessments (`MMSE`, `ADL`) strongly increased the probability of an Alzheimer's diagnosis.
* **Complaints vs. Biomarkers:** Active memory complaints and behavioral symptoms provided sharper diagnostic signals than general cardiovascular or metabolic lifestyle markers (`BMI`, `Cholesterol`).

### 2. Survival Analysis & Model Performance Benchmark

| Model Architecture | Validation Strategy | Concordance Index (C-Index) | Key Findings |
| :--- | :--- | :---: | :--- |
| **Cox Proportional Hazards** | Baseline Split | **0.600** | Linear baseline; `MMSE` statistically significant ($p < 0.005$, $\text{HR} = 0.96$ per point). |
| **Tuned Random Survival Forest** | 5-Fold Cross-Validation | **0.793** | Captures non-linear feature interactions; optimal hyperparameter configuration via `GridSearchCV`. |

* **Hyperparameter Tuning (`GridSearchCV`):** Tested 36 combinations across 5 folds (180 total fits). Optimal parameters identified: `max_depth: 8`, `min_samples_leaf: 15`, `n_estimators: 100`.
* **Accuracy Improvement:** Moving from a linear Cox model ($0.600$) to the tuned Random Survival Forest ($0.793$) demonstrated that non-linear ensemble approaches significantly improve risk stratification in cognitive decline cohorts.

---

## 🚀 How to Run

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git](https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git)
   cd YOUR_REPOSITORY_NAME
